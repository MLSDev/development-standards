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

* [Node.js](https://nodejs.org/en) v12.x.x (LTS)
* [npm](https://www.npmjs.com) package manager for Node.js _(deprecated; using in support projects)_
* [yarn](https://yarnpkg.com/) package manager for Node.js
* [bower](http://bower.io) package manager for web development _(deprecated; using in support projects)_
* [AngularJS](https://angularjs.org) 1.7.х framework _(deprecated; using in support projects)_
* [Angular](https://angular.io/) 8.0.0 as main framework
* [Pug](https://pugjs.org) - HTML template engine
* [Stylus](http://stylus-lang.com/) - CSS preprocessor
* [Gulp](http://gulpjs.com) - streaming build system _(deprecated; using in support projects)_
* [Webpack](https://webpack.js.org/) 4.x.x - JavaScript module bundler
* [Babel](https://babeljs.io/) - JavaScript compiler
* [TypeScript](https://www.typescriptlang.org/) 3.x.x - optional types, classes, and modules to JavaScript


## Development OS

We don’t recommend use Windows as OS for development machines. We use latest Mac OS X or Ubuntu/Debian (long-term support releases are preferred).


## IDE

* [WebStorm](https://www.jetbrains.com/webstorm) (not required)


## Coding Conventions

* [JavaScript Style Guide](https://github.com/airbnb/javascript)
* [Angular 1.x style guide](https://github.com/rwwagner90/angular-styleguide-es6) (good [article](https://www.sitepoint.com/writing-angularjs-apps-using-es6/))
* [Angular 8.x style guide](https://angular.io/docs/ts/latest/guide/style-guide.html)
* [CSS and SASS style guide](https://github.com/airbnb/css)
* [Stylus style guide](https://github.com/skyout/stylus-styleguide)


## Unit testing

Use these frameworks:
* [Karma](http://karma-runner.github.io)
* [Jasmine](http://jasmine.github.io)


## Preferred Libraries

* [EventEmitter](https://github.com/Olical/EventEmitter)
* [Underscore](http://underscorejs.org) / [lodash](https://lodash.com)
* [ui-router](https://ui-router.github.io/ng1/) 1.x - routing in AngularJS
* [ng-file-upload](https://github.com/danialfarid/ng-file-upload) 12.x.x - Angular directive to upload files
* [ngx-translate](http://www.ngx-translate.com) - The internationalization (i18n) library for Angular


## Best Practices

* Keep in mind that desktop web site is not a mobile app
* Keep in mind [300 milliseconds `onClick` delay](http://www.sitepoint.com/5-ways-prevent-300ms-click-delay-mobile-devices) in mobile devices' browsers
* Be careful with finding npm packages for you project and follow these rules:
  1. Check license.
  2. Evaluate indicators of quality, popularity and maintenance (good [resource](https://npms.io)).
  4. Check size of package for project bundle (good [resource](https://bundlephobia.com/)).
  3. Save dependencies without automatic a major version bump.
  4. Periodically check for outdated dependencies (command `npm outdated`).


## Design And Markup

__Web sites that we develop should be *responsive and adaptive* by default.__

#### Screen sizes:
* Desktop min size: 1024x768
* Mobile min size: 320x480

#### We support these browsers:
Desktop:
* Internet Explorer 11
* Edge - last 2 major versions
* Firefox - last 2 major versions, ESR
* Chrome - last 2 major versions
* Safari 12.0 and latest
* Opera - last 2 major versions

Mobile:
* Chrome - last 2 major versions
* Mobile Safari 12.0 and latest
* Android - last 2 major versions
* Samsung Internet 11.1 and latest
* UC Browser for Android 12.3 and latest


## Search Engine Optimization

_This section is not finished yet._

* Properly setup `robots.txt` file. See [robotstxt.org](http://www.robotstxt.org)
* Generate `sitemap.xml` file. See [sitemaps.org](https://www.sitemaps.org)
* Use [prerender.io](https://prerender.io)
* Use tags: `h1...h6`, `p`, `meta`, `title` etc.


## Google Analytics & other third-party services

Create separate third-party service ID constant for each environment (development, staging, production).
Keep constants files out of repository.

Google Analytics:
* Test account - dev@mlsdev.com _(see on MLSDev Articles / Accounts)_ - create app google analytics for staging and development servers.
* Production account is to be provided/created by/for client

Firebase:
* Test account for staging and development servers - dev@mlsdev.com
* [Firebase integration guide](https://docs.google.com/document/d/1qobl-BeepjCSQz8AxA8EpMsSiAnx4vX86CDc-NZSjJE) _(to be replaced on MLSDev Articles page)_
* Production account is to be provided/created by/for client

## Useful links

* [Frontend Dev Bookmarks](https://github.com/dypsilon/frontend-dev-bookmarks) - a _LOT_ of useful links
* [Material Design Icons](https://material.io/resources/icons)
* [AngularJS API Reference](https://docs.angularjs.org/api)
* [W3C](http://w3.org)
* [The Twelve-Factor App](http://12factor.net/)
