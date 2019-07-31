# iOS

1. [Supported OS Versions](#supported-os-versions)
1. [Supported Devices](#supported-devices)
1. [Development Tools](#development-tools)
    * [Programming Languages](#programming-languages)
    * [IDE](#ide)
    * [Other Tools](#other-tools)
1. [Codesigning](#codesigning)
1. [Dependency Management](#dependency-management)
1. [Coding Conventions](#coding-conventions)
1. [Apple Guidelines](#apple-guidelines)
1. [.gitignore](#gitignore)
1. [Test-Driven Development](#test-driven-development)
1. [Automated Builds](#automated-builds)
1. [Crash Logs](#crash-logs)
1. [Best Practices](#best-practices)
1. [Distributing To AppStore](#distributing-to-appstore)
1. [Useful Links](#useful-links)

## Supported OS Versions

### iOS 

* iOS 12.x+
* iOS 11.x (limited support for legacy projects)

### watchOS

* watchOS 5.0+

### tvOS

* tvOS 12.0+

## Supported Devices

[List of supported devices for iOS 12](https://www.apple.com/lae/ios/ios-12/)

## Development Tools

### Programming Languages

* Swift 5.0(preferred)
* Swift 4.2
* Swift 4.0

### IDE

* Xcode 10.2+

### Other Tools

* [Homebrew](http://brew.sh/) for package management (not MacPorts)
* If you need to manage Ruby environment, prefer [rbenv](https://github.com/sstephenson/rbenv) to [rvm](http://rvm.io). System Ruby is OK for iOS development needs, though.

## Codesigning

* Never revoke certificates yourself, ask Team Leader to do that if needed.
* Use **manual** code-signing option in Xcode along with [Fastlane](https://github.com/fastlane/fastlane) to specify pair of code-signing certificate and provisioning profile.
* Follow [Provisioning Portal Naming Conventions](/platform/ios/provisioning-portal-naming-conventions.md) (profiles, certificates and devices)
* Use [match](https://codesigning.guide) from [Fastlane](https://github.com/fastlane/fastlane) for generating development and distribution certificates as well as provisioning profiles. When generating certificates, specify not empty password, other way you won't be able to open certificate by tools like Knuff.
* Use a single [match](https://codesigning.guide) repo with certificates for one developer account instead of creating repo for each app developed on an account.

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

https://www.gitignore.io/api/swift

## Test-Driven Development

Use [XCTest](https://developer.apple.com/library/ios/documentation/DeveloperTools/Conceptual/testing_with_xcode/chapters/01-introduction.html) for unit tests

Matcher Frameworks:
* [Nimble](https://github.com/Quick/Nimble) - Swift
* [Expecta](https://github.com/specta/expecta) - Objective-C

Mocking Frameworks(Objective-C):
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
* There should be several types of builds, each of them having specific environment, for example Staging build should work with Staging server, Production build should work with Production server.
* There should be 4 CI jobs per app - one, that automatically runs tests on each pushed commit in every branch, one that compiles staging build when pushed to staging branch, one that makes production build on push to master branch, and one CI job, that refreshes DSYMS for Fabric. The last job should be run daily, all other events should be triggered by push event from git.

## Crash Logs

Use [Fabric](https://www.fabric.io) for crash logs. Install Fabric and follow the instructions. Fabric and Crashlytics frameworks must be installed via `CocoaPods`.

To provide Fabric symbolicated crash logs there should be a dedicated CI job, that runs daily, and uploads DSYMs from iTunesConnect to Fabric. Code to do that can be found on internal swift-snippets repo.

## Preferred libraries and frameworks

* [AFNetworking](https://github.com/AFNetworking/AFNetworking) 2.x+ for networking - Objective-C
* [EasyMapping](https://github.com/EasyMapping/EasyMapping) for JSON parsing - Objective-C
* [Alamofire](https://github.com/Alamofire/Alamofire) + [AlamofireImage](https://github.com/Alamofire/AlamofireImage) + [SwiftyJSON](https://github.com/SwiftyJSON/SwiftyJSON) for networking and parsing - Swift
* [CoreData](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/CoreData) for app local database (TBD: links to useful articles, about background context for example)

## Push notifications

* Use [Knuff](https://github.com/KnuffApp/Knuff) for testing push notifications. 
* Do not store push certificates in repository. 
* Use development certificate for debug builds and production certificate for release builds.

## Best Practices

* Create app user interface in Interface Builder, using XIBs or Storyboards. Custom UIView creation in a source code files is undesirable. Use [tools and frameworks](https://github.com/MLSDev/LoadableViews) to make your views small and reusable
* Avoid big Storyboards. Split Storyboards into smaller ones. More than 7-8 ViewControllers in one Storyboard are unacceptable. Use Storyboard references in XCode 7 to refactor large storyboards into small ones.
* Do not let UIViewController subclasses grow to more than 400 lines of code. Always try to keep them simple and short, preferably under 100 lines of code.

## Distributing To AppStore

* Make sure, that your app works with correct server and API version
* Update your [changelog](/common/git.md#changelog) with relevant changes
* Merge `develop` branch to `master` branch
* Create a [tag](/common/git.md#tags) in repository, that represents your Release

## Useful links

* [iOS Dev Weekly](https://iosdevweekly.com) - _worth to subscribe._
* [Erica Sadun blog](http://ericasadun.com) - Interesting in-depth articles on various Swift topics.
* [Swift weekly brief](https://swiftweekly.github.io)- Weekly updates on Swift development.
