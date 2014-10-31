source 'http://rubygems.org'

gemspec

if ENV['RAILS_VERSION']
  if ENV['RAILS_VERSION'] =~ /^4\.2/
    # This fixes https://github.com/rails/rails/pull/17453
    gem 'rails', github: 'huoxito/rails', branch: 'url_for-fallback-to-use_route'
  else
    gem 'rails', "~> #{ENV['RAILS_VERSION']}"
  end
end

# Code coverage plattform
gem 'coveralls', require: false

gem 'database_cleaner'

group :test do
  gem 'sqlite3'               if ENV['DB'].nil? || ENV['DB'] == 'sqlite'
  gem 'mysql2'                if ENV['DB'] == 'mysql'
  gem 'pg'                    if ENV['DB'] == 'postgresql'
  gem 'poltergeist'
  gem 'rspec-activemodel-mocks'
  unless ENV['CI']
    gem 'launchy'
  end
end

group :development, :test do
  unless ENV['CI']
    gem 'annotate'
    gem 'bumpy'
    gem 'yard'
    gem 'redcarpet'
    gem 'pry-byebug'
    gem 'spring'
    gem 'spring-commands-rspec'
  end
  gem 'jasmine-rails', github: 'searls/jasmine-rails'
  gem 'jasmine-jquery-rails', github: 'travisjeffery/jasmine-jquery-rails'
end
