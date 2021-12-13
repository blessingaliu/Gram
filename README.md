# gram

## Create App with specific params
```ruby 
rails new gram -T -d postgresql
```

## Install Rspec 
```ruby 
#in Gemfile group :development, :test add 
 gem 'rspec-rails', '~> 5.0.0'
#in command line
bundle install
rails generate rspec:install
```

## Setup database
```ruby 
rails db:setup
bin/rails db:migrate
```

## Setup devise 
```ruby 
# In Gemfile 
gem 'devise'

bundle install 
rails generate devise:install
```

## Configure devise 
```ruby
# Ensure you have defined default url options in your environments files. Open up config/environments/development.rb and add this line:

config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }

# Open up app/views/layouts/application.html.erb and add:

<% if notice %>
  <p class="alert alert-success"><%= notice %></p>
<% end %>
<% if alert %>
  <p class="alert alert-danger"><%= alert %></p>
<% end %>

# right above

 <%= yield %>

# Open up app/views/ideas/show.html.erb and remove the line that says:

<p id="notice"><%= notice %></p>

# Do the same for app/views/comments/show.html.erb. These lines are not necessary as we’ve put the notice in the app/views/layouts/application.html.erb file.

set the root route in config/routes.rb
rails g devise:views
```

## Setting up the user(Accounts) model
```ruby 
rails g devise Account
rails db:migrate
```

## Setting up the public controller 
```ruby 
rails g controller public
```