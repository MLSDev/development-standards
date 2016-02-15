# Front-end

1. [Technologies](#technologies)
1. [Development OS](#development-os)
1. [IDE](#ide)
1. [Coding Conventions](#coding-conventions)
1. [Test-Driven Development](#test-driven-development)
1. [Preferred Libraries](#preferred-libraries)
1. [Best Practices](#best-practices)
1. [Design And Markup](#design-and-markup)
1. [Search Engine Optimization](#search-engine-optimization)
1. [Google Analytics & other third-party services](#google-analytics--other-third-party-services)
1. [Useful Links](#useful-links)


## Technologies

* [Node.js](https://nodejs.org/en) v4.x.x (Last LTS version)
* [npm](https://www.npmjs.com) package manager for Node.js
* [bower](http://bower.io) package manager for web development
* [AngularJS](https://angularjs.org) 1.5.х as main framework
* [Yeoman](http://yeoman.io) - scaffolding tool
* [Jade](http://jade-lang.com) - HTML template engine
* [Stylus](http://learnboost.github.io/stylus) - CSS preprocessor
* [CoffeeScript](http://coffeescript.org) - pretty JavaScript
* [Gulp](http://gulpjs.com) - streaming build system


## Development OS

We don’t use Windows as OS for development machines. We use latest Mac OS X or Ubuntu/Debian (long-term support releases are preferred).


## IDE

* [WebStorm 9](https://www.jetbrains.com/webstorm) (not required)


## Coding Conventions
* [CoffeScript Style Guide](https://github.com/polarmobile/coffeescript-style-guide/blob/master/README.md)


## Test-Driven Development

Use these frameworks:
* [Karma](http://karma-runner.github.io)
* [Jasmine](http://jasmine.github.io)
* [Protractor](http://angular.github.io/protractor)


## Preferred Libraries

* [Async](https://github.com/caolan/async)
* [EventEmitter](https://github.com/Olical/EventEmitter)
* [Underscore](http://underscorejs.org) / [lodash](https://lodash.com)


## Best Practices

* Keep in mind that desktop web site is not a mobile app
* Keep in mind [300 milliseconds `onClick` delay](http://www.sitepoint.com/5-ways-prevent-300ms-click-delay-mobile-devices) in mobile devices' browsers


## Design And Markup

Web site that we develop should be **responsive and adaptive** by default

Screen sizes:
* Desktop min size: 1024x768
* Mobile min size: 320x480

We support these web browsers:
* Internet Explorer 10+
* Latest Google Chrome
* Latest Apple Safari
* Latest Mozilla Firefox


## Search Engine Optimization

_This section is not finished yet._

* Properly setup `robots.txt` file. See [robotstxt.org](http://www.robotstxt.org)
* Use [prerender.io](https://prerender.io)
* Use tags: `h1...h6`, `p` etc.
* Use `meta` and `title` tags

## Google Analytics & other third-party services

Write ID for each server (development, staging, production) as a constant. Move the script of outside servers to run and use these constants there.

Google Analytics:
* Test account - dev@mlsdev.com (see on articles - accounts) - create app google analytics for staging and development servers.
* Production account provided/created by/for client

Yandex Metrika:
* To access Yandex Metrika via Google Account (dev@mlsdev.com)

## Useful links
* [Frontend Dev Bookmarks](https://github.com/dypsilon/frontend-dev-bookmarks) - a _LOT_ of useful links
* [Material Design Icons](https://materialdesignicons.com)
* [AngularJS API Reference](https://docs.angularjs.org/api)
* [W3C](http://w3.org)

