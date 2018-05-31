---
layout: post
---

If you want to add Bootstrap to your brand new Rails 5 application, you have to do following steps.

Generate new Rails 5 application

```
rails new ruddit
```

Go to newly created directory

```
cd ruddit
```

Generate scaffold for our first model.

```
rails generate scaffold Link name:string url:string
```

```

Perform pending migrations.


```
rails db:migrate
```

Now we have working application with one model. Let's add a bit of authentication using Devise gem.

Add to Gemfile:

```
gem 'devise'
```

Then run:

```
bundle install
```

Install Devise:

```
rails generate devise:install 
```

Complete prerequisites for usind devise in our application. Then generate User model:

```
rails generate devise User
```

and perform migrations:

```
rails db:migrate
```

Next, we create some infrastructure to log in and log out our users. After that, we are ready to add Bootstrap.

To do this, simply go to github repository of gem [Bootstrap](https://github.com/twbs/bootstrap-rubygem) and follow the instructions.
