# Android 

1. [Platform Versions](#platform-versions)
1. [Development tools](#development-tools)
1. [User Interface](#user-interface)
1. [Coding Conventions](#coding-conventions)
1. [Best Practices](#best-practices)
1. [.gitignore](#gitignore)
1. [Test-Driven development](#test-driven-development)
1. [Preferred libraries and frameworks](#preferred-libraries-and-frameworks)
1. [Location](#location)
1. [Dependency Management](#dependency-management)
1. [Project Environments](#project-environments)
1. [Release Key](#release-key)
1. [Graphic Assets](#graphic-assets)


## Platform Versions


### Min SDK Version

Support Android OS versions starting from 4.0 (Ice Cream Sandwich, API Level 14). 
Do not support older versions (2.2 Froyo, 2.3 Gingerbread, 3.x Honeycomb etc).


### Target SDK Version

For new projects, use latest stable version of Android API (6.0.0 Marshmallow, API Level 23).
Do not use beta versions or developer previews (e.g. API Level 20).


## Development Tools


### JDK

Use Java  Development Kit (JDK) [version 7](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html).


### IDE

Use latest stable [Android Studio](http://developer.android.com/sdk/index.html).
Migrate old projects from Eclipse and IntelliJ IDEA.


## Coding Conventions

Follow [MLSDev Android Coding Conventions](/platform/android/coding-conventions.md). 

Use Android Studio for auto formatting.


## Best Practices

* Avoid anonymous classes usage
* Use `ContentProviders`
* Use `SyncAdapters` (more info [here](http://habrahabr.ru/company/e-Legion/blog/206210/) and [here](http://habrahabr.ru/company/e-Legion/blog/216857/))
* Prefer `Services` for long-running background tasks
* Understand the difference between `Loader` and `AsyncTask`
* Use _Analyse->Inspect Code_ in Android Studio for static analysis of project code and XML at the end of each development cycle (Iteration, Spring, Milestone etc).  


## User Interface

Follow [Android Design Principles](https://developer.android.com/design/get-started/principles.html), particularly the [Style Guide](https://www.google.com/design/spec/style/color.html).

Useful links:
* [Introduction to material design](http://www.google.com/design/spec/material-design/introduction.html)
* [Material Design on Android Checklist](http://android-developers.blogspot.com/2014/10/material-design-on-android-checklist.html)


## .gitignore

Use IDE for default ```.gitignore``` file generation. 
Do not forget about OS temporary files (`.DS_Store` in Mac OS, `Thumbs.db` in Windows etc).


## Test-Driven Development

* Use [Android JUnit](http://developer.android.com/tools/testing/testing_android.html) for unit tests.
* Use [Mockito](https://code.google.com/p/mockito) for mocks.
* Use [Espresso](https://google.github.io/android-testing-support-library/docs/espresso/index.html) for automated UI tests.
* Use [Spoon](http://square.github.io/spoon) for testing on multiple devices


## Preferred Libraries and Frameworks

* Use latest stable [Retrofit](http://square.github.io/retrofit/) to access RESTful web services.
* Use [OkHttp](http://square.github.io/okhttp/) for more flexible networking (for example, when the API is not RESTful).
* Use [GSON](https://github.com/google/gson) for JSON serialization and parsing.
* Use [Glide](https://github.com/bumptech/glide) or [Picasso](https://github.com/square/picasso) for image downloading, caching and displaying.
* Use [Crashlytics](https://try.crashlytics.com) for crash logs.
* Use [Dagger 2](http://google.github.io/dagger) for Dependency Injection.
* Java [classes generator](http://www.jsonschema2pojo.org) by JSON scheme or JSON example. Compatible with Gson and Jackson.


## Location

Prefer [Google Play Services](https://developers.google.com/android/guides/setup) to `LocationManager`.
More info can be found in this [blog post](http://mlsdev.com/blog/37).


## Dependency Management

Never add third-party source code or libraries to project repository.
Use [Gradle](http://gradle.org) and [Maven](https://maven.apache.org).


## Project Environments

Project should contains at least 2 Gradle tasks: _Release_ and _Debug_.

Release task should include: 
* release build signing (see [Release Key](#release-key) section)
* positive Crashlytics flag
* configuration for the stable API version
 
Debug task should include:
* debug build signing
* negative Crashlytics flag
* configuration for the development (staging) API version


## Release Key

* Release key file can be stored in project tracker (JIRA, Redmine etc), password can be on Wiki page or some other private/secured place.
* [Generating Release key](https://developer.android.com/tools/publishing/app-signing.html#studio). Main information needed from client - company name and location.
* Info on [Jenkins setup](http://sysmagazine.com/posts/205308/)


## Graphic Assets

* Require graphic designers to provide assets in all sizes (mdpi, hdpi, xhdpi, xxhdpi etc).
* Prefer [9patch](http://developer.android.com/tools/help/draw9patch.html) graphics.

More info: [MLSDev Design Requirements](/common/design-requirements.md)
