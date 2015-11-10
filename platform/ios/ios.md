# iOS

1. [Supported OS Versions](#supported-os-versions)
1. [Supported Devices](#supported-devices)
1. [Development Tools](#development-tools)
    * [Programming Languages](#programming-languages)
    * [IDE](#ide)
    * [Other Tools](#other-tools)
1. [Certificates, Profiles And Devices](#certificates-profiles-and-devices)
1. [Dependency Management](#dependency-management)
1. [Coding Conventions](#coding-conventions)
1. [Apple Guidelines](#apple-guidelines)
1. [.gitignore](#gitignore)
1. [Test-Driven Development](#test-driven-development)
1. [Automated Builds](#automated-builds)
1. [Crash Logs](#crash-logs)
1. [Best Practices](#best-practices)
1. [Distributing To AppStore](#distributing-to-appstore)

## Supported OS Versions

### iOS 

* iOS 8.1+
* iOS 9.x

### watchOS

* watchOS 2.0+

### tvOS

* tvOS 9.0+

## Supported Devices

We support:
* iPhones:
    * iPhone 4S
    * iPhone 5, iPhone 5C, iPhone 5S
    * iPhone 6, iPhone 6 Plus
    * iPhone 6s, iPhone 6s Plus
* iPads:
    * iPad 2, iPad 3, iPad 4
    * iPad Air, iPad Air 2
    * iPad Mini 1st generation, iPad Mini Retina
    * iPad Pro
* iPods:
    * iPod 5th generation
    * iPod 6th generation


## Development Tools

### Programming Languages

* Swift 2 (preferred)
* Objective-C

### IDE

* xCode 7.1+


### Other Tools

* [Homebrew](http://brew.sh/) for package management (not MacPorts)
* If you need to manage Ruby environment, prefer [rbenv](https://github.com/sstephenson/rbenv) to [rvm](http://rvm.io). System Ruby is OK for iOS development needs, though.



## Certificates, Profiles And Devices

* Never revoke certificates yourself, ask Team Leader to do that if needed.
* Never use _"Fix Issue"_ option of xCode when you experience any issue with certificate (but you can use it for provisioning profile issues).
* Use MLSDev development certificate for running apps which do not use Push Notifications.
* For testing Push Notifications use client's development certificate.
* Follow [Provisioning Portal Naming Conventions](/platform/ios/provisioning-portal-naming-conventions.md) (profiles, certificates and devices)


## Dependency Management

Use [CocoaPods](https://cocoapods.org) to add third-party components (frameworks, libraries) to your project. Use frameworks, not static libraries, for dependencies. This is done by calling `use_frameworks!` method in `Podfile`.

`Pods` directory is considered a build artefact, and therefore should be added to `.gitignore`.

`Podfile.lock` file should be committed to repository, along with .xcworkspace file.


## Coding Conventions

* [Swift Coding Conventions](/platform/ios/swift-coding-conventions.md)
* [Objective-C Coding Conventions](/platform/ios/objective-c-coding-conventions.md)


## Apple Guidelines

Strictly follow these guidelines:
* [AppStore Review Guidelines](https://developer.apple.com/app-store/review/guidelines)
* [iOS Human Interface Guidelines](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG)
* [watchOS Human Interface Guidelines](https://developer.apple.com/watch/human-interface-guidelines/)
* [tvOS Human Interface Guidelines](https://developer.apple.com/tvos/human-interface-guidelines/)

## .gitignore

* https://www.gitignore.io/api/swift

## Test-Driven Development

Use [XCTest](https://developer.apple.com/library/ios/documentation/DeveloperTools/Conceptual/testing_with_xcode/chapters/01-introduction.html) for unit tests

Matcher Frameworks:
* [Nimble](https://github.com/Quick/Nimble) - Swift
* [Expecta](https://github.com/specta/expecta) - Objective-C

Mocking Frameworks:
* [OCMock](https://github.com/erikdoe/ocmock)
* [OCMockito](https://github.com/jonreid/OCMockito)
* [OHHTTPStubs](https://github.com/AliSoftware/OHHTTPStubs)
* [KIF](https://github.com/kif-framework/KIF) for functional tests


## Automated Builds

* Use [fastlane](https://github.com/KrauseFx/fastlane) for app building and submission
* Make schemes shared and commit them to repository
* Before submitting build, all unit tests must pass. If even 1 test is failing, build should also fail
* Stable builds are made in the end of each development cycle (Iteration, Sprint, Milestone etc)
* Access should be given to developers, testers, managers and client team
* Apple's Testflight is preferred service for delivering beta builds
* There should be 2 types of builds - _nightly_ and _stable_


## Crash Logs

Use [Fabric](https://www.fabric.io) for crash logs.


## Preferred libraries and frameworks

* [AFNetworking](https://github.com/AFNetworking/AFNetworking) 2.x+ for networking - Objective-C
* [EasyMapping](https://github.com/EasyMapping/EasyMapping) for JSON parsing - Objective-C
* [Alamofire](https://github.com/Alamofire/Alamofire) + [AlamofireImage](https://github.com/Alamofire/AlamofireImage) + [SwiftyJSON](https://github.com/SwiftyJSON/SwiftyJSON) for networking and parsing - Swift
* [CoreData](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/CoreData) for app local database (TBD: links to useful articles, about background context for example)
* [BlocksKit](https://github.com/zwaldowski/BlocksKit) for block API


## Best Practices

* Create app user interface in Interface Builder, using XIBs or Storyboards. Custom UIView creation in a source code files is undesirable.
* Avoid big Storyboards. Split Storyboards into smaller ones. More than 7-8 ViewControllers in one Storyboard are unacceptable. Use Storyboard references in XCode 7 to refactor large storyboards into small ones.
* Do not let UIViewController subclasses grow to more than 400 lines of code. More information can be found [here]().


## Distributing To AppStore

* Make sure, that your app works with correct server and API version
* Update your [changelog](/common/git.md#changelog) with relevant changes
* Merge `develop` branch to `master` branch
* Create a [tag](/common/git.md#tags) in repository, that represents your Release
