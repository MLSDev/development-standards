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
* [Angular](https://angular.io/) for complex Enterprise solutions
* [Vue.js](https://vuejs.org/) for simple-to-moderate complexity web sites
* [Pug](https://pugjs.org) - HTML template engine
* [Stylus](http://stylus-lang.com/) - CSS preprocessor
* [Webpack](https://webpack.js.org/) 4.x.x - JavaScript module bundler
* [TypeScript](https://www.typescriptlang.org/) 4.x.x - optional types, classes, and modules to JavaScript


## Development OS

We don’t recommend use Windows as OS for development machines. We use latest Mac OS X or Ubuntu/Debian (long-term support releases are preferred).


## IDE

* [WebStorm](https://www.jetbrains.com/webstorm) (not required)


## Coding Conventions

* [JavaScript Style Guide](https://github.com/airbnb/javascript)
* [Angular style guide](https://angular.io/guide/styleguide)
* [CSS and SASS style guide](https://github.com/airbnb/css)
* [Stylus style guide](https://github.com/skyout/stylus-styleguide)


## Unit testing

Use these frameworks:
* [Karma](http://karma-runner.github.io)
* [Jasmine](http://jasmine.github.io)


## Preferred Libraries

* [RxJS](https://github.com/ReactiveX/rxjs)
* [Underscore](http://underscorejs.org) / [lodash](https://lodash.com)
* [date-fns](https://date-fns.org/)
* [normalize.css](https://github.com/necolas/normalize.css/)
* [For Angular](./angular.md)
* [For Vue.js](./vue.md)


## Best Practices

* Keep in mind that desktop web site is not a mobile app
* Keep in mind [300 milliseconds `onClick` delay](http://www.sitepoint.com/5-ways-prevent-300ms-click-delay-mobile-devices) in mobile devices' browsers
* Be careful with finding npm packages for your project and follow these rules:
  1. [Check license](https://github.com/MLSDev/development-standards/blob/master/common/common.md#licenses).
  2. Evaluate indicators of quality, popularity and maintenance (good [resource](https://npms.io)).
  3. Check size of package for project bundle (good [resource](https://bundlephobia.com/)).
  4. Save dependencies without automatic a major version bump.
  5. Periodically check for outdated dependencies (command `npm outdated`).


## Design And Markup

__Web sites that we develop should be *responsive and adaptive* by default.__

#### We support these browsers:
Desktop:
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
* [W3C](http://w3.org)
* [The Twelve-Factor App](http://12factor.net/)
