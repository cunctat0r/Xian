---
layout: post
---

## Setting up some CI for simple node.js project

This tutorial is my "memory card" how to set up some CI/CD features for simple node.js project. When I push changes to Github repository, automated tests on TravisCI are running, after successful tests TravisCI deploys the project on Heroku. 

### First we create and set up our project.

1. Create repository on github and initialize it with readme

2. Clone repository

    ```
    git clone git@github.com:cunctat0r/sw_stations_api.git
    ```

3. Go to the project's folder:

  ```
  cd sw_stations_api
  ```

4. Initialize the project:

  ```
  npm init
  ```

5. Install project dependencies:

  ```
  npm install body-parser express mongodb mongoose --save
  ```

6. Install development dependencies:

  ```
  npm install expect mocha nodemon supertest --save-dev
  ```

7. Add some code to create minimal working sample

8. Push on github

### Next, we create Heroku application. We assume that heroku CLI is installed.

1. Create Heroku application

  ```
  heroku create
  ```

2. Add mongolab addon to use Mongodb:

  ```
  heroku addons:create mongolab:sandbox
  ```

3. Push our repository to Heroku:

  ```
  git push heroku master
  ```

It Works!

### Integration with TravisCI

1. Create file .travis.yml in root directory

2. On travis-ci.org add repository, enable "Build only if .travis.yml is present" and "Build pull request updates"

3. Push our project with .travis.yml

  ```
  git push
  ```

4. If we want, we can add TravisCI badge to readme.md

5. To add Slack notifications, we need to have our own Slack team. We create channel for our project, add to this channel TravisCI integration and follow the instructions.

6. It's strongly recommended to encript the API keys. We need travis gem to do it.

  ```
  gem install travis
  ```

7. Add encrypted key to .travis.yml:

  ```
  travis encrypt "OUR_KEY_FROM_CHANNEL_SETTINGS" --add notifications.slack
  ```

8. After key is encrpted and added to .travis.yml, we do git push and enjoy!

### Enable Heroku notification

1. In Slack, add Heroku integration. Following the instruction, run the command in project directory:

  ```
  heroku addons:create deployhooks:http --url https://hooks.slack.com/services/XXXXXXXXXXX
  ```

Automatic deploy to Heroku using TravisCI after successfull build:

2. Execute command in project directory:

  ```
  travis encrypt $(heroku auth:token) --add deploy.api_key
  ```

3. Add to .travis.yml lines (before encrypted Heroku token):

  ```
  provider: heroku
  app: heroku_app_name
  ```

4. Push our project to Github only:

  ```
  git push
  ```

All work for us will be done by Github and TravisCI, we will receive notifications in our Slack channel.

