---
title: 'Dependency management'
taxonomy:
    category:
        - docs
visible: true
---

### BUNDLER GEMFILE DEPENDENCY MANAGEMENT

Enscale's Ruby runtime nodes come pre-loaded with the most common Ruby gems for the [supported Ruby versions](/servers-and-technologies#ruby) to give you the fastest and easiest deployment experience.

Each application is unique, so you're likely to need something we didn't include too. We use the Bundler dependency management tool to handle this for you. Simply include a Gemfile within your deploy files, and Enscale will pass it to Bundler to resolve the missing gems for you.

### Gemfile

Your Gemfile will contain all the Ruby gem dependencies that are required to execute your Ruby code. This is entirely standard Bundler, so you can refer to [Bundler Gemfile documentation](https://bundler.io/v2.0/man/gemfile.5.html) for full details.

In the Gemfile, you will need to specify a Rubygem repository as a source.
```ruby
source "https://rubygems.org"
```

If you use a Rubygem repository, which requires credentials, you can include the username and password in your source command:
```ruby
source "https://username:password@gems.example.com"
```

Given that your Ruby version is set within Enscale, there is no need to include it inside your Gemfile.

A Gemfile is unique to your project, but just for example a Gemfile may look like this:

```ruby
source 'https://rubygems.org'

gem 'rails', '~> 4.1.1'
gem 'pg'

# Asset Pipeline
gem "coffee-rails"
gem "jquery-rails"
gem "jquery-ui-rails"
gem "mapbox-rails"
gem "sass-rails"
gem 'uglifier', '>= 1.3.0'
gem "wysihtml5-rails"
gem "active_model_serializers"
gem "active_record_union"
gem "acts_as_geocodable"
gem "audited-activerecord"
gem "awesome_nested_set"
gem "color"
gem "countries"
gem "csv_builder"
gem "dalli"
gem "delayed_job"

group :development, :test do
	gem "guard-rspec"
	gem "launchy"
	gem "pry-rails"
	gem "rspec-rails"

end
```

Your finished Gemfile should be placed into the root of your project, and Enscale will pass it to Bundler for processing during application deployment.

Bundler performs dependency resolving when you

* Deploy your application via the Enscale dashboard 
* Switch Ruby versions