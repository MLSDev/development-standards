# Git

1. [Best Practices](#best-practices)
1. [Tags](#tags)
1. [README](#readme)
1. [CHANGELOG](#changelog)

## Best Practices

Follow these practices when you work with Git: 
* Avoid “big” commits (several features or bug fixes at once). Commit small code changes instead
* Follow [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/) ([Russian translation](http://habrahabr.ru/post/106912/))
* Try to push to remote repository after each commit in order to avoid non-synced repository state
* Push code at least once per day
* Use ```git rebase``` before using ```git merge``` if needed to have streamlined history.
* After ```git merge``` delete unused branches on remotes.
* Never use ```--force``` option for any Git command (except for rebase in your branch)
* Tag commits for each app build or server app deployment, at the end of each Sprint or when the product is going to be Released (read more below).
* If you need UI client for Git, use [SourceTree](https://www.sourcetreeapp.com)
* There should be a ```README.md``` file in the root of repository (read more below)
* There should be a ```CHANGELOG``` file in the root of repository (read more below)

### Tags

Tag the final commits at the end of each development cycle (Sprint, Iteration, Milestone, Release etc):

```
# git tag -a version_string -m "version_description"
```

where

* ```version_string``` - version number as string. See [MLSDev Version Numbering conventions](https://github.com/MLSDev/development-standards/blob/master/common/versioning.md) for more information. 
* ```version_description``` - short description of version. For instance:
    * Iteration 1
    * Build \#42
    * AppStore v2.0.0 Aug 20, 2014
    * Production v1.4.6 Jul 1, 2014

Examples:

```
# git tag -a v2.0.6-rc1 -m "Build #314"
# git tag -a v2.0.6 -m "AppStore v2.0.6 Aug 20, 2014"
```


#### Profit

Tagging helps to fix bugs like “this feature worked in previous release, it stopped to work in current release” very fast:

```
# git diff <tag of version that worked fine>
```


### README

In a repository root, there should be a README.md file in Markdown format.
README should contain :
* a brief project description
* list of technologies, platforms and frameworks used (with versions specified)
* build instructions

Examples:
* https://github.com/MLSDev/TRON/blob/master/README.md
* https://github.com/okolodev/ios_ci/blob/master/README.md


### CHANGELOG

In a repository root, there should be a CHANGELOG file in plain text or Markdown format.
CHANGELOG should contain a history of changes from version to version, in particular:
* functionality changes
* new features
* fixed bugs

It is allowed to store `CHANGELOG.MD` file in Documentation folder of the project, if you have more documentation, for example - https://github.com/ReactiveX/RxSwift/tree/master/Documentation

Example of `CHANGELOG.MD`:

```
2.1.6
Improvement work with database
Fixed layout in post
Fixed Recent Chats synchronizing
Fixed mentions in anon posts

2.1.5
Improvement to Streamer performance

2.1.4
Bug fixes from Google Analytics

2.1.3
Changed sort order for Recent chats

...
```
