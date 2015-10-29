# Provisioning Portal Naming Conventions

1. [Certificates](#certificates)
1. [Identifiers](#identifiers)
    * [App Identifier](#app-identifier)
    * [Pass Type Id](#pass-type-id)
1. [Devices](#devices)
1. [Provisioning Profiles](#provisioning-profiles)


## Certificates

`Username` of person who issued a certificate, or company name.

Examples:

```Dick Mountain```


## Identifiers

### App Identifier

```
com.<company name>.<CamelCased app name>
```

Example:

```
com.mlsdev.AdFox
```


## Pass Type Id

```
pass.com.<company name>.<CamelCased app name>.<CamelCased pass name>
```

Example:

```
pass.com.mlsdev.AdFox.AirplaneTicket
````


## Devices

```
[<company name>]<phone owner's name>[<project name>]<device full name>[<device number>]
```

Examples:

```
Dick Mountain AdFox iPhone 5C
Apple Steve Jobs iPad Air
```


## Provisioning Profiles

```
[<company name>] <app name> <profile type (AdHoc|AppStore)>
```

Company name may be skipped if it is the same as app name.

Examples:

```
Apple FaceTime AdHoc
Instagram AppStore
```