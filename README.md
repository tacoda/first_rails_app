# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...


# Notes

```sh
rails new first_rails_app
cd first_rails_app
rails generate scaffold car make:string model:string year:integer
rails db:migrate
rails server
^C
git init
git add .
git commit -m "Initial commit"
git remote add origin git@github.com:tacoda/first_rails_app.git
git push -u origin master
heroku keys:add
heroku create
git remote
```

Replace sqlite with postgres in production

```ruby
group :development, :test do
 gem 'sqlite3'
end

group :production do
  gem 'pg'
end
```

```sh
bundle install --without production
```

Configure root route

```ruby
Rails.application.routes.draw do
  root 'cars#index'
  resources :cars
end
```

```sh
git add .
git commit -m "Updates for heroku deployment"
git push origin master
git push heroku master
heroku run rails db:migrate
heroku open
```