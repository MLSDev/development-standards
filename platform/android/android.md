# Android 

1. [Platform Versions](#platform-versions)
1. [Development Tools](#development-tools)
1. [User Interface](#user-interface)
1. [Coding Conventions](#coding-conventions)
1. [Best Practices](#best-practices)
1. [.gitignore](#gitignore)
1. [Test-Driven Development](#test-driven-development)
1. [Preferred Libraries And Frameworks](#preferred-libraries-and-frameworks)
1. [Location](#location)
1. [Dependency Management](#dependency-management)
1. [Project Environments](#project-environments)
1. [Release Key](#release-key)
1. [Graphic Assets](#graphic-assets)
1. [ProGuard](#proguard)
1. [Useful Links](#useful-links)


## Platform Versions


### Min SDK Version

Support Android OS versions starting from 4.1 (Jelly Bean, API Level 16). 
Do not support older versions (2.2 Froyo, 2.3 Gingerbread, 3.x Honeycomb, 4.0.3 - 4.0.4 Ice Cream Sandwich etc).
Check [Dashboard](http://developer.android.com/intl/ru/about/dashboards/index.html) page for information about platform versions, screen sizes and densities statistics.

### Target SDK Version

For new projects, use latest stable version of Android API (7.1.1 Nougat, API Level 25).
Do not use beta versions or developer previews.


## Development Tools


### JDK

Use Java  Development Kit (JDK) [version 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).


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
* Use _Analyse->Inspect Code_ in Android Studio for static analysis of project code and XML at the end of each development cycle (Iteration, Spring, Milestone etc)


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


## Preferred Libraries And Frameworks

* Use latest stable [Retrofit](http://square.github.io/retrofit/) to access RESTful web services
* [OkHttp](http://square.github.io/okhttp/) for more flexible networking (for example, when the API is not RESTful)
* [GSON](https://github.com/google/gson) for JSON serialization and parsing
* [Glide](https://github.com/bumptech/glide) or [Picasso](https://github.com/square/picasso) for image downloading, caching and displaying
* [Crashlytics](https://try.crashlytics.com) for crash logs
* [Dagger 2](http://google.github.io/dagger) for Dependency Injection
* [RxJava](https://github.com/ReactiveX/RxJava) for asynchronous programming
* Java [classes generator](http://www.jsonschema2pojo.org) by JSON scheme or JSON example. Compatible with Gson and Jackson


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
* Prefer Multi-Density Vector Graphics.

More info: [MLSDev Design Requirements](/common/design-requirements.md)

## ProGuard

* Use [Proguard](http://developer.android.com/intl/ru/tools/help/proguard.html) tool for improving security of your application. Proguard obfuscates your code by renaming classes, fields, and methods with semantically distorted names. The result apk file is more difficult to reverse engineer. It's important to use Proguard when your application should hide authorization protocol (e.g. client_id and client_secret of OAuth).
* Proguard tool shrinks and optimize your code which can help you remain within 65k methods.

### Warning

When working with legacy code it's important to know is ProGuard enabled or not. While you are making changes you should add appropriate rules into configuration file.

### Warning

Whenever ProGuard runs, it outputs a mapping.txt file, which shows you the original class, method, and field names mapped to their obfuscated names. You must keep mapping.txt file for every release build, otherwise you will be unable to read stack trace of crash reports.

## Useful Links

* [Android Weekly](http://androidweekly.net) - _subscribe to it!_
