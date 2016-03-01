# Common

1. [In a nutshell](#in-a-nutshell)
1. [User Experience](#user-experience)
1. [Error Handling](#error-handling)
1. [Exception Handling](#exception-handling)
1. [Personal Data Security](#personal-data-security)
1. [Non-stable Components](#non-stable-components)
1. [Deprecated API](#deprecated-api)
1. [Don’t Reinvent the wheel](#dont-reinvent-the-wheel)
1. [Don't Use Outdated Source Components](#dont-use-outdated-source-components)
1. [Licenses](#licenses)
1. [Networking](#networking)
1. [Source Code Management](#source-code-management)
1. [Continuous Integration](#continuous-integration)
1. [Product Versioning](#product-versioning)
1. [Code Review](#code-review)


## In a nutshell

* Provide the best possible User Experience
* Handle errors and exceptions carefully
* Take user personal data security into account
* Never use non-stable components in production code
* Never use deprecated API
* Never use outdated components
* Don’t reinvent the wheel
* Check licenses of third-party components
* Use industry standard technologies and and follow best practices for networking
* Use Git for source control
* Use Jenkins for Continuous Integration
* Track product versions
* Perform Code Review on project start and on-going, once per two weeks

_Find more details about each point below._


## User Experience

* Follow platform-specific User Interface Guidelines
* Never block User Interface of your app:
    * perform network requests in background
    * do all database work in background
    * etc    
* If something is happening in background, let user know about it (show activity indicator, progress bar etc)


## Error Handling

Try to cover all the critical cases when you write error handling code.

For instance, handle not only `HTTP 200 OK` response status, take care of 401, 403, 404, 500-504 and [others](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes).


## Exception Handling

Handle exceptions properly.

Bad:

```java
    try {
        doSomethingDangerous();
    }
    catch (Exception e) {
        Log(e.printStackTrace());
    }
```

Good:

```java
    try {
        doSomethingDangerous();
    }
    catch (ConcreteException e) {
        logErrorMessage(e);
        closeNetworkConnections();
        closeDatabaseConnections();
        freeOtherResources();
        showComprehensiveErrorMessage(e); // or showSendCrashReportDialog();
        gracefullyTerminateTheApp();
    }
    catch (OtherConcreteException e) {
        // ...
    }
```


## Personal Data Security

Never store user's login credentials, credit card details and other potentially vulnerable personal information on mobile devices or in web browser local storage.


## Non-stable Components

Never use non-stable versions of components (SDKs, frameworks, libraries, gems, pods, jars etc) in a production code.

Non-stable versions are:
* alpha, beta (v2.0-alpha)
* nightly builds (v0.10.12-nightly-20130615)
* release candidates (v1.0-rc1 etc)

You can use non-stable versions for research projects, proof of concept, or your own skill-up.


## Deprecated API

Never use API classes, methods or functions marked as _“Deprecated”_.


## Don’t Reinvent The Wheel

Before start to work on new non-trivial problem, check if the solution already available. Do not hesitate to use solutions from your teammates or third-party components, libraries and frameworks (either open-source or proprietary).

On the other hand, think twice before using the third-party component:
* is it good enough or poorly designed/written?
* isn't it an overkill/redundant?


## Don't Use Outdated Source Components

Don't use frameworks, libraries, SDKs and other source code which is outdated or does not have active support community.

For instance, don't use [CanCan](https://github.com/CanCanCommunity/cancancan) gem which is not supported anymore. Use [CanCanCan](https://github.com/CanCanCommunity/cancancan) instead.

Another example. For Dependency Injection in Android, don't use outdated [Dagger 1](http://square.github.io/dagger), use [Dagger 2](http://google.github.io/dagger/) instead.


## Licenses

If you are going to use a third-party component in your project, check its license first. You can use a component with permissive type of license (e.g. BSD, MIT, Apache) with no doubts. For other licenses, discuss and agree the usage of component with Project Manager and Client.

Useful web site: http://choosealicense.com/


## Networking

* Communicate via secured connection
* Use industry standard technologies for authentication
* Develop and use RESTful web services
* Prefer JSON to XML


### Secured Connection

For production-mode apps (both mobile and web), establish [TLS](https://en.wikipedia.org/wiki/Transport_Layer_Security)-secured network connection.


### Authentication

Never use HTTP Basic Authentication or other authentication methods that transfer credentials as a plain text.

Use industry standard authentication methods: at least HTTP Digest Authentication, OAuth 2.0 is preferred.


### RESTful Web Services

REST architectural style is a standard de-facto for modern web services development.

If you are web developer, don’t reinvent the square wheel - develop RESTful web services for your clients (i.e., another developers).

If you are not web developer - don’t hesitate to tell the web developer to not reinvent the square wheel if one proposes something weird instead of RESTful web services.

More info:
* REST:
    * http://en.wikipedia.org/wiki/Representational_state_transfer
    * http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm
    * http://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm
* CRUD: http://en.wikipedia.org/wiki/Create,_read,_update_and_delete
* HTTP: http://tools.ietf.org/html/rfc2616


### JSON vs. XML

[JSON](http://json.org) format is simpler than XML.

JSON serialization and parsing is supported on all platforms we develop apps for, so it is good for communication between our apps.

Minimum development efforts required to add JSON support to a project. JSON support works out of the box in most platforms.


## Source Code Management

We use Git for source code management.

**Please read about the practices we follow in a [Git](/common/git.md) section of this document.**

We have a [GitLab](https://about.gitlab.com/)-powered server to keep projects we develop for our clients:
* http://git.mlsdev.com

We have a GitHub account for open-source projects:
* https://github.com/MLSDev

We can work with client's repositories upon request. We have experience with [Bitbucket](https://bitbucket.org/) and [GitHub](https://github.com/) repository hostings and
CVS, Subversion and Mercurial SCMs.


## Continuous Integration

We use [Jenkins](http://jenkins-ci.org) and [GitLab CI](https://about.gitlab.com/gitlab-ci) for Continuous Integration.

Each app of the project should have at least 2 build configurations in Continuous Integration system (either Jenkins or GitLab CI):
* **nightly** - builds are running every night, fetching the latest source from **develop** branch of Git repository.
* **stable** - builds are running when changes available in **master** branch of Git repository.

For more information on platform-specific set up, check the corresponding sections of this document.

Our servers:
* http://ci.mlsdev.com
    * iOS apps
* http://android-ci.mlsdev.com
    * Android apps
    * Back-end apps
    * Front-end apps


### Jenkins + Dropbox

If the application build file (IPA, APK etc) is too large to send by email, use `dropbox_uploader.sh` script that is already installed on our Jenkins servers.

Add _“Execute Shell”_ build step to the configuration:

```
${JENKINS_HOME}/dropbox_uploader.sh upload path_to_build_file dropbox_destination_path
```

where

* `path_to_build_file` - path to the app build
* `dropbox_destination_path` - path to a directory in MLSDev Dropbox account, where you want a build to be uploaded. This path should be like `Projects/<Manager's Name>/<Project Name>/Builds/<Debug or Release>/`

Script is taken from [Dropbox-Uploader](https://github.com/andreafabrizi/Dropbox-Uploader)


## Product Versioning

Track product version numbers and keep them up-to-date. See [Versioning](/common/versioning.md) section for details.


## Code Review

Code Review should be performed for every project on regular basis.

**Please read about our Code Review process [here](/common/code-review.md).**
