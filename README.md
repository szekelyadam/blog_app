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

## Testing features in RSpec

Create a *features* directory under *app/spec*, then create a spec file for the feature (for example *creating_article_spec.rb*
which will test the article creating feature of the app).

First of all, require the *rails_helper.rb*, which you generated with the RSpec install.

```ruby
require 'rails_helper'
```

Then name the feature this file is aimed to test, and write the scenarios inside it:
```ruby
RSpec.feature 'Creating articles' do
  scenario 'A user creates a new article' do
    # Scenario actions
  end
end
```

Actions are specifying the scenarios. These actions are very easy readable, almost plain english.
I already know the following ones:

```ruby
visit '/' # Visit the URL given in the parameter
click_link 'New Article' # Simulates clicking the given link 
fill_in 'Title', with: 'Creating a blog' # Fills the given input with the given text
click_button 'Create Article' # Simulates clicking a button
expect(page).to have_content('Article has been created') # Expects the given page to have the given content
expect(page.current_path).to eq(articles_path) # Expects the given variable to have the given value
```

## Running RSpec tests

Running the tests are easy, just run
```
rspec
```
to run all the tests, or call it with a parameter, to run only one test such like
```
rspec spec/features/creating_article_spec.rb
```
