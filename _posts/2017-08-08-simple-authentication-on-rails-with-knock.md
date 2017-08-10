---
layout: post
title: JWT Authentication On Rails Using Knock
tags: Programming RubyOnRails 
---

It's been a while since I last made a post, almost a year in fact. A lot has happened since then and now I feel like it's time to finally get back into this. 

I recently got the opportunity to work on an API-only rails project at work. The interesting bit came when I learned while trying to maintain sessions for a user that sessions in an API simply don't exist. REST is meant to be Stateless (I mean I should've guessed so because it's literally in the name), and that means there aren't supposed to be any states being maintained in any session or cookie hashes. 

I later learned that we typically substitute sessions for this thing i'd never heard of before called JWT (JSON Web Token) which is basically a unique identifier for each user who wishes to be logged in to the server/service. It's a pretty interesting idea and I found the perfect gem to implement this feature as well. 

### Introducing Knock
Knock is an authentication solution for Rails API-only application based on JSON Web Tokens.

##### What are JSON Web Tokens?
JSON Web Tokens are an open, industry standard RFC 7519 method for representing claims securely between two parties.

### Installation
Add knock to your Gemfile:
```
gem 'knock'
```

Bundle it up:
```
bundle install
```

Run the install generator:
```
rails generate knock:install
```

It will create the following initializer `config/initializers/knock.rb`. This file contains all the informations about the existing configuration options.


### Prerequisites for Knock
Knock assumes you already have a User model defined before you introduce knock.

Knock needs a method provided by the `bcrypt` gem (or other gems that provide similar functionality), the `authenticate` method (provided by `has_secure_password`)

```
class User < ActiveRecord::Base
  has_secure_password
end
``` 

Include the Knock::Authenticable module in your ApplicationController

```
class ApplicationController < ActionController::API
  include Knock::Authenticable
end
```

You can now protect your resources by calling authenticate_user as a before_action inside your controllers:

```
class SecuredController < ApplicationController
  before_action :authenticate_user

  def index
    # etc...
  end

  # etc...
end
```

**Note: ** Now you have access to a `current_user` method in your controllers which can provide you the current user logged in or authenticated. 

Knock provides us a route to `/user_token` which goes to the `user_token_controller.rb` controller and does the auth logic. 

To test how the request and response work try the following:

##### Example Request:
```
POST /user_token
{"auth": {"email": "foo@bar.com", "password": "secret"}}
```

##### Example Response:
```
201 Created
{"jwt": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9"}
```
Once you have the jwt for the user, append it to your header in the Authorization field as such: 
```
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9
```

and now you can make authorized requests from the server hosting the api, and the server can see who the authorized user is through the `current_user` method. 

##### Allowing CORS
You will have to allow Cross Origin Requests (requests coming from elsewhere from your app such as a client-side app) in your rails app. 