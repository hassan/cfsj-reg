source 'https://rubygems.org'

ruby '2.2.2'

gem 'rails', '4.2.1'
gem 'pg'
gem 'puma'
group :production do
  gem 'rails_12factor'  # for Heroku
end

gem 'devise'
gem 'exception_notification'

gem 'sass-rails', '~> 5.0'
gem 'uglifier', '>= 1.3.0'
gem 'jquery-rails'

gem 'jbuilder', '~> 2.0'

group :test do
  gem 'simplecov'
end

group :development do
  gem 'rvm-capistrano'

  gem 'better_errors'
  gem 'binding_of_caller', platforms: [:mri]
  gem 'brakeman'
  gem 'sandi_meter'
  gem 'railroady'
end

group :development, :test do
  gem 'pry-rails'
  gem 'awesome_print'

  gem 'rspec-rails'
  gem 'fabrication'
  gem 'faker'

  gem 'byebug'
  gem 'web-console', '~> 2.0'
  # gem 'spring'
end

gem 'sdoc', '~> 0.4.0', group: :doc
