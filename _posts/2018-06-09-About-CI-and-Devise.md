---
layout: post
---

If I want to use [Travis CI](https://travis-ci.org) with Rails application using [Device](https://github.com/plataformatec/devise), I have to do following.

1. Add to my Devise initializer `config/initializers/devise.rb`

  ``` ruby
  config.secret_key = ENV['SECRET_KEY_BASE']
  ```

2. Ensure that there is Heroku environment variable named `SECRET_KEY_BASE`

3. In TravisCI web-interface set environment variable named `SECRET_KEY_BASE` with value from Step 2.

After that changes [TravisCI](https://travis-ci.org) works correctly and all builds are passed. 
