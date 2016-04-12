# Versioning

This section describes MLSDev Version Numbering conventions.

1. [Intro](#intro)
1. [Versioning During MVP Development](#versioning-during-mvp-development)
1. [Versioning During Ongoing Development](#versioning-during-ongoing-development)
1. [How to track version numbers in source code](#how-to-track-version-numbers-in-source-code)
    * [Front-end](#front-end)
    * [Back-end](#back-end)
    * [iOS](#ios)
    * [Android](#android)
1. [References](#references)


## Intro

Version number should consist of 3 non-negative integer numbers separated by dots:

```
x.y.z
```

where
* ```x``` - major version number, represents "big" product releases to market
* ```y``` - minor version number, represents new features or critical bug fixes
* ```z``` - tiny version number, represents minor updates and bug fixes

Versions should start from ```0.0.0``` at initial project commit to source code repository.


## Versioning During MVP Development

Tiny version number (z) should be updated after each bug fix or new feature developed.

Minor version number (y) should be updated after each successful Sprint (deployment to staging server or deliverance of stable mobile app build).

Major version number (x) should be updated from 0 to 1 on first market release of product.

Examples:

* 0.0.0 - initial commit
* 0.1.0 - result of Sprint 1 (potentially shippable product increment)
* 0.3.0 - result of Sprint 3
* 0.3.1 - bug fix in Sprint 3
* 1.0.0 - first product release to market/Google Play/App Store etc.


## Versioning During Ongoing Development

Tiny version number (z) should be updated when:
* new feature added during Sprint
* non-critical bug fixed during Sprint
* few minor issues fixed (typo, markup, layout etc)

_Tiny version updates may not be released to market/production._

Minor version number (y) should be updated:
* when Sprint finished successfully _(Note: minor version number may not equal to Sprint number)_
* when critical bug fixed (server fault, app crash)
* after security vulnerability fix
* after core platform upgrade (e.g. Rails 4.x -> Rails 5.0, AngularJS 1.x -> 2.0, iOS 8.x -> 9.0, Android 4.x -> 5.0 etc)
* **each time when end-users should update the app from AppStore or Google Play**

_Minor version updates may not be released to market/production unless they provide critical updates or bug fixes._

Major version number (x) should be updated when:
* product increment has significant number of completely new features added
* product made a pivot (see [Lean Startup](https://en.wikipedia.org/wiki/Lean_startup))
* product UI/UX _completely_ redesigned

_Major version updates must be released to market/production._

Examples:

* 1.0.1 - minor update or bug fix to first product release
* 1.1.0 - major update, security update or critical bug fix to first product release
* 1.2.0 - app now supports iOS 9.0
* 1.3.0 - crash on iPhone 6 Plus fixed
* 1.4.0 - Sprint 46 product increment 
* 1.4.1 - UI layout issue fix to 1.4.0
* 2.0.0 - App became universal and now supports iPads (supported iPhones only before)


## How to track version numbers in source code

### Front-end

In ```package.json```. See [gulp](https://github.com/gulpjs/gulp/blob/master/package.json) source code for example.


### Back-end

Create ```lib/<project_name>/version.rb``` file. See [Redmine source code](https://github.com/redmine/redmine/blob/master/lib/redmine/version.rb) for example.


### iOS

Keep `CFBundleShortVersionString` property up-to-date.

As a reference of good versioning approach, see https://github.com/artsy/eidolon/blob/master/fastlane/Fastfile

#### Testflight

Because of how Apple's Testflight works, it may require 3-5 days of external review for external tester builds, which may be very inconvenient. Which is why, if Testflight is used as builds distribution service, it is allowed to have external and internal versions. 

##### External version

Is set in ```CFBundleShortVersionString``` and set to 1.0.0 on start of the project. When next version is developed(e.g. 1.1.0), version number is set, and sent to external app review with the first build on first sprint of development. Sending subsequent builds with the same version does not require review.

##### Internal version

Is kept in CHANGELOG.MD and updated as defined in top of this document. It should also be included in `What to Test` section of TestFlight build. This version is used to set tags in git repo, when release is made.


### Android

Keep ```versionName``` property up-to-date in Gradle build file of application module. 

Also, update (increment) ```versionCode``` each time you update version number.


## References

* [Semantic Versioning 2.0.0](http://semver.org/)
