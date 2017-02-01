# README

This README would document the important steps made throughout the course.

## Installing RSpec and Capybara

This on is simple. Add these ones to your Gemfile:

```ruby
gem 'rspec-rails', '3.1.0'
gem 'capybara', '2.7.1'
```

These gems aren't necessary for production, so they can be in test and development groups in the Gemfile.
The course didn't explained, why we have to use these specific versions.
 
Then install RSpec for the application with

```
rails g rspec:install
```

and create a stub for RSpec running

```
bundle binstubs rspec-core
```

