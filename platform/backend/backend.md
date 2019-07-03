# Back-end

1. [Technologies](#technologies)
    * [Development OS](#development-os)
    * [IDE](#ide)
    * [HTTP Server](#http-server)
    * [Database Server](#database-server)
    * [Cloud Hosting Platform](#cloud-hosting-platform)
1. [Preferred Gems](#preferred-gems)
    * [Authentication](#authentication)
    * [Authorization](#authorization)
    * [Active Record](#active-record)
    * [Abstraction](#abstraction)
    * [Pagination](#pagination)
    * [API](#api)
    * [Email](#email)
    * [Decorators](#decorators)
    * [File Uploading](#file-uploading)
    * [HTTP Clients](#http-clients)
    * [Searching](#searching)
    * [Scheduled/Recurrence Jobs](#scheduledrecurrence-jobs)
    * [Environment Variables](#environment-variables)
    * [Admin Panel](#admin-panel)
    * [Logging](#logging)
    * [Debug](#debug)
    * [Data Visualization](#data-visualization)
    * [Database Tools](#database-tools)
    * [Code Analysis and Metrics](#code-analysis-and-metrics)
    * [Testing](#testing)
    * [Security](#security)
    * [Production](#production)
    * [Error Handling](#error-handling)
    * [Mobile Development](#mobile-development)
    * [Other](#other)
1. [Coding Conventions](#coding-conventions)
1. [.gitignore](#gitignore)
1. [Best Practices](#best-practices)
    * [Databases](#databases)
    * [Security](#security)
    * [Code Analysis And Metrics](#code-analysis-and-metrics)
1. [Load Balancing](#load-balancing)
1. [Load Testing](#load-testing)
1. [Useful Links](#useful-links)
1. [Recommended Books](#recommended-books)


## Technologies

* Ruby 2.6.x (latest stable)
* Ruby on Rails 5.x (latest stable)
* Ruby environment management: [rvm](http://rvm.io)


### Development OS

We don’t use Windows as OS for development machines. We use latest macOS or Ubuntu/Debian (long-term support releases are preferred).


### IDE

* [RubyMine](https://www.jetbrains.com/ruby) (not required)


### HTTP Server

* Use latest stable [nginx](http://nginx.org)


### Database Server

* Prefer latest stable [PostgreSQL](http://www.postgresql.org)


### Cloud Hosting Platform

* Prefer [Amazon Web Services](http://aws.amazon.com)


## Preferred Gems


### Authentication

* [api_authentication](https://github.com/MLSDev/api_authentication)
* [api_session_recovering](https://github.com/MLSDev/api_session_recovering)

### Authorization

* [pundit](https://github.com/elabs/pundit) - Minimal authorization through OO design and pure Ruby classes.
* [rolify](https://github.com/RolifyCommunity/rolify) - Role management library with resource scoping.

### Active Record

* [AASM](https://github.com/aasm/aasm) - State machines for Ruby classes.
* [active_record_union](https://github.com/brianhempel/active_record_union) - UNIONs in ActiveRecord! Adds proper union and union_all methods to ActiveRecord::Relation.
* [PaperTrail](https://github.com/paper-trail-gem/paper_trail) - PaperTrail lets you track changes to your models' data. It's good for auditing or versioning.
* [globalize](https://github.com/globalize/globalize) - Rails I18n de-facto standard library for ActiveRecord model/data translation.

### Abstraction

* [interactor](https://github.com/collectiveidea/interactor) - Interactor provides a common interface for performing complex user interactions.
* [wisper](https://github.com/krisleech/wisper) - A micro library providing objects with Publish-Subscribe capabilities.

### Pagination

* [Pagy](https://github.com/ddnexus/pagy) - Pagy is the ultimate pagination gem that outperforms the others in each and every benchmark and comparison.
* [Kaminari](https://github.com/amatsuda/kaminari) - A Scope & Engine based, clean, powerful, customizable and sophisticated paginator for modern web app frameworks and ORMs.

### API

* [rspec-rails-swagger](https://github.com/drewish/rspec-rails-swagger) - This gem helps you generate Swagger docs by using RSpec to document the paths. 
* [swagger-blocks](https://github.com/fotinakis/swagger-blocks) - For generating API documentation in [Swagger](http://swagger.io/specification/) format.

## Email

* [letter_opener](https://github.com/ryanb/letter_opener) - Preview mail in the browser instead of sending.

## Caching

* [Dalli](https://github.com/petergoldstein/dalli) - A high performance pure Ruby client for accessing memcached servers.

## Decorators

* [Draper](https://github.com/drapergem/draper) - Draper adds an object-oriented layer of presentation logic to your Rails application.

## File Uploading

* [shrine](https://github.com/janko-m/shrine) - File Attachment toolkit for Ruby applications.
    * [image_processing](https://github.com/janko/image_processing) - High-level image processing helper methods with libvips and ImageMagick/GraphicsMagick.
    * [shrine-url](https://github.com/shrinerb/shrine-url) - Custom URL storage for Shrine.

## HTTP Clients

* [Faraday](https://github.com/lostisland/faraday) - HTTP client lib that provides a common interface over many adapters (such as Net::HTTP) and embraces the concept of Rack middleware when processing the request/response cycle.

## Searching

* [elasticsearch-rails](https://github.com/elastic/elasticsearch-rails)
* [searchkick](https://github.com/ankane/searchkick) - Intelligent search made easy with Rails and Elasticsearch.
* [pg_search](https://github.com/Casecommons/pg_search) - pg_search builds ActiveRecord named scopes that take advantage of PostgreSQL's full text search.

## Scheduled/Recurrence Jobs
* [Whenever](https://github.com/javan/whenever) - whenever is a Ruby gem that provides a clear syntax for writing and deploying cron jobs.
* [Sidekiq](https://github.com/mperham/sidekiq) - Simple, efficient background processing for Ruby.
  * [sidekiq-scheduler](https://github.com/Moove-it/sidekiq-scheduler) - Lightweight job scheduler extension for Sidekiq.
  * [sidekiq-unique-jobs](https://github.com/platanus/activeadmin_addons) - Ensure uniqueness of your Sidekiq jobs.
  * [sidekiq-batch](https://github.com/breamware/sidekiq-batch) - Simple Sidekiq Batch Job implementation.

## Environment Variables
* [dotenv](https://github.com/bkeepers/dotenv) - For setting shell environment variables.


## Admin Panel
* [ActiveAdmin](http://activeadmin.info) - ActiveAdmin is a administration framework for Ruby on Rails applications.
  - [active_skin](https://github.com/rstgroup/active_skin) - Flat skin for active admin.
  - [activeadmin_addons](https://github.com/rstgroup/active_skin) - Extends ActiveAdmin to enable a set of great optional UX improving add-ons.


  
## Logging

* [Ahoy](https://github.com/ankane/ahoy) - Ahoy provides a solid foundation to track visits and events in Ruby, JavaScript, and native apps.
* [Lograge](https://github.com/roidrage/lograge) - An attempt to tame Rails' default policy to log everything.


## Debug

* [pry-rails](https://github.com/rweng/pry-rails) - Avoid repeating yourself, use pry-rails instead of copying the initializer to every rails project. This is a small gem which causes rails console to open pry. It therefore depends on pry.
* [awesome_print](https://github.com/awesome-print/awesome_print) - Awesome Print is a Ruby library that pretty prints Ruby objects in full color exposing their internal structure with proper indentation.

## Data Visualization

* [RailsRoady](https://github.com/preston/railroady) - UML diagram generation on models and controllers.

## Database Tools

* [lol_dba](https://github.com/plentz/lol_dba) - Small package of rake tasks that scan your application models and displays a list of columns that probably should be indexed.

## Code Analysis and Metrics

* [RuboCop](https://github.com/bbatsov/rubocop) - Rubocop is a Ruby static code analyzer.
    * [rubocop-performance](https://github.com/rubocop-hq/rubocop-performance) - An extension of RuboCop focused on code performance checks.
* [Reek](https://github.com/troessner/reek) - Code smell detector for Ruby.
* [rails_best_practices](https://github.com/railsbp/rails_best_practices) - Code metric tool for Rails projects.
* [Fasterer](https://github.com/DamirSvrtan/fasterer) - Make your Rubies go faster with this command line tool highly inspired by fast-ruby and Sferik's talk at Baruco Conf.
* [Rubycritic](https://github.com/whitesmith/rubycritic) - A Ruby code quality reporter.

## Testing

* [rspec](https://github.com/rspec/rspec) - Use latest versions.
* [rspec_rails](https://github.com/rspec/rspec-rails)
* [shoulda-matchers](https://github.com/thoughtbot/shoulda-matchers)
* [shoulda-callback-matchers](https://github.com/jdliss/shoulda-callback-matchers)
* [rspec-its](https://github.com/rspec/rspec-its)
* [rspec-activemodel-mocks](https://github.com/rspec/rspec-activemodel-mocks)
* [simplecov](https://github.com/colszowka/simplecov)
* [database_cleaner](https://github.com/DatabaseCleaner/database_cleaner)
* [database_rewinder](https://github.com/amatsuda/database_rewinder)
* [factory_bot_rails](https://github.com/thoughtbot/factory_bot_rails)
* [ffaker](https://github.com/ffaker/ffaker)
* [VCR](https://github.com/vcr/vcr) - Record your test suite's HTTP interactions and replay them during future test runs for fast, deterministic, accurate tests.
* [shrine-memory](https://github.com/shrinerb/shrine-memory) - Provides in-memory storage for Shrine.

### Security

* [brakeman](https://github.com/presidentbeef/brakeman) - Brakeman is a static analysis tool which checks Ruby on Rails applications for security vulnerabilities.
* [bundler-audit](https://github.com/rubysec/bundler-audit) - bundler-audit is a patch-level verification tool for Bundler which checks for vulnerable versions of gems and insecure gem sources.

## Production

* [Puma](http://puma.io) as a Ruby web server
* [Capistrano](https://github.com/capistrano/capistrano) - Remote multi-server automation tool.
* [rack-timeout](https://github.com/heroku/rack-timeout) - Add timeouts to rack applications.
* [Rack Attack](https://github.com/kickstarter/rack-attack) - Rack middleware to blocking & throttling.
* [newrelic_rpm](https://github.com/newrelic/rpm) - New Relic RPM Ruby Agent.

## Error Handling

* [exception_notification](https://github.com/smartinez87/exception_notification) - For error/exception notifications from server.
* [Raven Ruby](https://github.com/getsentry/raven-ruby) - Raven is a Ruby client for Sentry.

## Mobile Development

* [rpush](https://github.com/rpush/rpush)
* [venice](https://github.com/nomad/venice) - Venice is a simple gem for verifying Apple In-App Purchase receipts, and retrieving the information associated with receipt data.

## Other

* [money-rails](https://github.com/RubyMoney/money-rails) - Integration of RubyMoney - Money with Rails.
* [eu_central_bank](https://github.com/RubyMoney/eu_central_bank) - This gem downloads the exchange rates from the European Central Bank. You can calculate exchange rates with it. It is compatible with the money gem.
* [rails-settings-cached](https://github.com/huacnlee/rails-settings-cached) - Manage settings with Ruby on Rails.
* [squasher](https://github.com/jalkoby/squasher)
* [health_check](https://github.com/ianheggie/health_check)

## Coding Conventions

* [Ruby Style Guide](https://github.com/bbatsov/ruby-style-guide)
* [Rails Style Guide](https://github.com/bbatsov/rails-style-guide)

## Best Practices
* [RSpec Best Practices](https://github.com/andreareginato/betterspecs)
* [The Ultimate Guide to Ruby Timeouts](https://github.com/ankane/the-ultimate-guide-to-ruby-timeouts)
* [Best practices for running Rails in production](https://github.com/ankane/production_rails)



## .gitignore

Add the following lines to default Rails-generated `.gitignore` file:

```
.DS_Store
database.yml
secrets.yml
.idea
coverage/
.env.development.local
.env.test.local
.env.production.local
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



## Load Testing

* We use Apache JMeter in strong collaboration with our QA Department.


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
