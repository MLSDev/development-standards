# Open Source

Among else, we consider GitHub as a:
 * sales & marketing channel _(clients review our code; they see how we work)_
 * talent aquisition channel _(we look at applicants' code; they look at our code; they see how we work)_

**Contents**
* [Our Open Source Contribution Strategy](#our-open-source-contribution-strategy)
* [Project Releases](#project-releases)
* [Decoration](#decoration)
  * [README](#readme)
  * [Contributing Guide](#contributing-guide)
  * [LICENSE](#license)
  * [Badges](#badges)

## Our Open Source Contribution Strategy

* Extract the most useful, well-turned and successful common tasks solutions (for company and community) into open source projects under the company GitHub Ogranization profile.
* Of course, do not publish Intellectual Propety of our clients. Just public domain stuff.
* Give a higher priority to these frequently appearing tasks:
  * Registration & Login
  * Chats
  * Pagination / Endless Scroll
  * Push Notifications
  * Error Handling
  * Payments
  * SMS
  * Maps, Geolocation
  * Analytics
  * Validations
  * Simple and full-text search
  * Authentication / Authorization, JSON Web Tokens
  * I18n
  * L10n
* Do not hesitate to use third-party open source projects, _if they benefit us, our projects and our clients and save our time (but [check the license][licenses] first)._
* Invest our time to fork and make pull-requests to third-party open source projects, _if that benefits us, our projects and our clients and saves our time._
* Invest our time to support, maintain and update our open source projects (react to others developers' feedback, feature and pull requests, in particular)

## Project Releases

* Follow [MLSDev Version Numbering conventions][versioning]
* We are trying to present our projects to the community in the best possible way (see _Decoration_ section below)
* Publish under MIT License (see below)

## Decoration

Add as much useful information as possible to our open-source projects.

### README

`README.md` file should contain:

* Intro and some fancy but useful badges
* Brief overview of what the project does
* Features description
* Requirements for a usage
* Use cases
* Installation instructions
* Status (_in active development_, _not maintained anymore_ etc)
* Link to docs/wiki
* Link to License
* Link to Contributing guide
* _Information About MLSDev Inc (see example at the bottom of this page)_

A good example can be found [here](https://github.com/MLSDev/TRON).

### LICENSE

All of our open source projects are licensed under [MIT License](https://choosealicense.com/licenses/mit).

`LICENSE` file should be added to repo's root directory.
This file should also be mentioned in project's `README` file. See example snippet in Markdown:

```
## License

<project-name> is Copyright © 2016-2017 Denys Telezhkin and MLSDev Inc.
It is free software, and may be redistributed under the terms specified in the [LICENSE](LICENSE) file.
```

You can find MIT License text here: [https://opensource.org/licenses/MIT](https://opensource.org/licenses/MIT)


### CONTRIBUTING Guide

In order to help your project contributors do a good work put a `CONTRIBUTING.md` file in the root directory of the repository.
Anyone who opens a pull request or creates an issue will see a link to that file.

Contribution guidelines should include:

* Steps for creating meaningful issues or valuable pull requests.
* Links to external documentation, conventions, code of conduct etc.
* Community and behavioral expectations.

**Good Guidelines Examples:**

* [Atom](https://github.com/atom/atom/blob/master/CONTRIBUTING.md)
* [Rails](https://github.com/rails/rails/blob/master/CONTRIBUTING.md)
* [Kaminari](https://github.com/kaminari/kaminari/blob/master/CONTRIBUTING.md)


### Badges

Read more at [shields.io](http://shields.io).

## About MLSDev

[<img src="/mlsdev-logo.png" alt="MLSDev.com">][mlsdev]

Development Standards are maintained by MLSDev, Inc. We specialize in providing all-in-one solution in mobile and web development. Our team follows Lean principles and works according to agile methodologies to deliver the best results reducing the budget for development and its timeline. 

Find out more [here][mlsdev] and don't hesitate to [contact us][contact]!

[mlsdev]: http://mlsdev.com
[contact]: http://mlsdev.com/contact-us


[licenses]: https://github.com/MLSDev/development-standards/blob/master/common/common.md#licenses
[versioning]: https://github.com/MLSDev/development-standards/blob/master/common/versioning.md
[about-mlsdev]: https://github.com/MLSDev/development-standards/blob/master/README.md#about-mlsdev
