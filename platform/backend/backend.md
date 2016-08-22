# Back-end

1. [Technologies](#technologies)
    * [Development OS](#development-os)
    * [IDE](#ide)
    * [HTTP Server](#http-server)
    * [Database Server](#database-server)
    * [Cloud Hosting Platform](#cloud-hosting-platform)
1. [Preferred Gems](#preferred-gems)
1. [Coding Conventions](#coding-conventions)
1. [Test-Driven Development](#test-driven-development)
1. [.gitignore](#gitignore)
1. [Best Practices](#best-practices)
    * [Databases](#databases)
    * [Security](#security)
    * [Code Analysis And Metrics](#code-analysis-and-metrics)
1. [Deployment](#deployment)
1. [Load Balancing](#load-balancing)
1. [Load Testing](#load-testing)
1. [Useful Links](#useful-links)
1. [Recommended Books](#recommended-books)


## Technologies

* Ruby 2.3.x (latest stable)
* Ruby On Rails 4.2.x (latest stable)
* Ruby environment management: [rvm](http://rvm.io)


### Development OS

We don’t use Windows as OS for development machines. We use latest Mac OS X or Ubuntu/Debian (long-term support releases are preferred).


### IDE

* [RubyMine](https://www.jetbrains.com/ruby) (not required)


### HTTP Server

* Use latest stable [nginx](http://nginx.org)


### Database Server

* Prefer latest stable [PostgreSQL](http://www.postgresql.org)


### Cloud Hosting Platform

* Prefer [Amazon Web Services](http://aws.amazon.com)


## Preferred Gems

* [Puma](http://puma.io) as Ruby web server
* [Capistrano](http://capistranorb.com) for deployment
* [Kaminari](https://github.com/amatsuda/kaminari) for pagination
* [Draper](https://github.com/drapergem/draper) Decorators/View-Models for Rails Applications
* [pundit](https://github.com/elabs/pundit) Minimal authorization through OO design and pure Ruby classes
* [has_scope](https://github.com/plataformatec/has_scope) Map incoming controller parameters to named scopes in your resources
* [dotenv](https://github.com/bkeepers/dotenv) for setting shell environment variables
* [exception_notification](https://github.com/smartinez87/exception_notification) for error/exception notifications from server
* [AppSignal](https://appsignal.com) better errors notification server with full debug information about each error
* [swagger-blocks](https://github.com/fotinakis/swagger-blocks) for generating API documentation in [Swagger](http://swagger.io/specification/) format
* [rack-timeout](https://github.com/heroku/rack-timeout) add timeouts to rack applications.
* [rack-cors](https://github.com/cyu/rack-cors) for configuring CORS headers.
* [lograge](https://github.com/roidrage/lograge) for production logs squshing.


## Coding Conventions

* [Ruby Style Guide](https://github.com/bbatsov/ruby-style-guide)
* [Rails Style Guide](https://github.com/bbatsov/rails-style-guide)
* [RSpec Best Practices](https://github.com/andreareginato/betterspecs)
* [The Ultimate Guide to Ruby Timeouts](https://github.com/ankane/the-ultimate-guide-to-ruby-timeouts)


## Test-Driven Development

* Use latest versions of [rspec](https://github.com/rspec/rspec) and [rspec_rails](https://github.com/rspec/rspec-rails)
* [shoulda-matchers](https://github.com/thoughtbot/shoulda-matchers)
* [shoulda-callback-matchers](https://github.com/jdliss/shoulda-callback-matchers)
* [rspec-its](https://github.com/rspec/rspec-its)
* [rspec-activemodel-mocks](https://github.com/rspec/rspec-activemodel-mocks)
* [simplecov](https://github.com/colszowka/simplecov)

Useful gems: 
* [database_cleaner](https://github.com/DatabaseCleaner/database_cleaner)
* [factory_girl_rails](https://github.com/thoughtbot/factory_girl_rails)


## .gitignore

Add the following lines to default Rails-generated `.gitignore` file:

```
.DS_Store
database.yml
secrets.yml
.idea
```


## Best practices

### Databases

* Use ActiveRecord ORM (scopes, enums, where with conditions, order etc) instead of raw SQL queries 
* Design the database schema with [Vertabelo](http://www.vertabelo.com)
* Keep your schema up-to-date with [Rails ERD](https://github.com/voormedia/rails-erd)


### Security

* Avoid common security problems following [Ruby on Rails Security Guide](http://guides.rubyonrails.org/security.html)
* Never store production data (logins, passwords etc) in source code repository
* Keep `config/database.yml` and `config/secrets.yml` outside of the source code repository. Use shell environment variables instead. More info [here](http://www.gotealeaf.com/blog/managing-environment-configuration-variables-in-rails)


### Code Analysis And Metrics

Here is a list of must-have gems:
* [Brakeman](https://github.com/presidentbeef/brakeman) - A static analysis security vulnerability scanner for Ruby on Rails applications.
* [SimpleCov](https://github.com/colszowka/simplecov) - Code Coverage tool for Ruby
* [RuboCop](https://github.com/bbatsov/rubocop) - A static code analyzer, based on the community Ruby style guide
* [rails_best_practices](https://github.com/railsbp/rails_best_practices) - Code metric tool for Rails projects
* [RailsRoady](https://github.com/preston/railroady) - UML diagram generation on models and controllers
* [lol_dba](https://github.com/plentz/lol_dba) - small package of rake tasks that scan your application models and displays a list of columns that probably should be indexed
* [bullet](https://github.com/flyerhzm/bullet) - help to kill N+1 queries and unused eager loading

_These tools are to be run at the end of each development cycle (Iteration, Sprint, Milestone, Release)_


## Deployment

_TBD_


## Load Testing

* Use [Loader.io](https://loader.io)


## Load Balancing

* Use [AWS Elastic Load Balancing](http://aws.amazon.com/elasticloadbalancing)


## Useful Links

* [Ruby Weekly](http://rubyweekly.com) - _subscribe to it!_
* [Green Ruby News](http://greenruby.org/)
* [This week in Rails](https://rails-weekly.ongoodbits.com/)
* [Awesome Rails](https://github.com/ekremkaraca/awesome-rails)
* [Awesome Ruby](https://github.com/markets/awesome-ruby)
* [Ruby Toolbox](https://www.ruby-toolbox.com)
* [The 12-factor app](http://12factor.net/) - a methodology for building SaaS apps


## Recommended Books

* [Practical Object-Oriented Design in Ruby (by Sandi Metz)](https://www.amazon.co.uk/Practical-Object-Oriented-Design-Ruby-Addison-Wesley/dp/0321721330)
* [Eloquent Ruby (by Russ Olsen)](https://www.amazon.co.uk/Eloquent-Ruby-Addison-Wesley-Professional/dp/0321584104/ref=pd_bxgy_14_img_2?ie=UTF8&refRID=HQ47S5P3BSG69ASDJH9A)
