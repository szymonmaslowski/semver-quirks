# SemVer


> <span style="font-size: 1.6em">**Sem**<span style="font-size: 0.8em">antic</span> **Ver**<span style="font-size: 0.8em">sioning</span></span>

### Purpose

SemVer is about trust and communication between maintainers and users of a project.

- **clear and predictable** versioning system,
- developers and users understand changes made in a particular release especially in terms of **compatibility**.
- it helps package managers and dependency tools know whether it’s safe to update.
- it encourages developers to think about API stability and responsibility.

### Rules

Given a version number **MAJOR**.**MINOR**.**PATCH**, increment the:

- **MAJOR** when you make <span style="color: red">**incompatible**</span> API changes
- **MINOR** when you make a <span style="color: green">**backward compatible**</span> changes and **add functionality**
- **PATCH** when you make a <span style="color: green">**backward compatible**</span> changes and **fix bug(s)**

There are additional labels for **pre-release** and **build** metadata available as sufix to the main MAJOR.MINOR.PATCH format.
 - 1.2.3-alpha.4
 - 1.2.3+456
 - 1.2.3-alpha.4+567

### Version range specifiers

 - Exact: = or no specifier e.g. `"1.2.3"`
 - Patch:
   - 1.0 or 1.0.x ~1.0.4
 - Minor:
   - 1 or 1.x
   - ^1.0.4
 - Major: * or x
 -  < / <= / > / >= / =

When adding a dependency to the project using your package manager of choice by not specifying any version range selector

`yadn add lodash`

the dependency will be specified with `^` - allowing any backward compatible version

`"lodash": "^4.17.21"`

### The fun...
...of `^` specifier in immature projects.

What versions would you expect be installed by the bellow command?
```
npm add react@^0.0.1 lodash@^0.1.0
```

<details>
  <summary>Answer</summary>

The command uses `^` version range specifier which
the biggest version of particular major.

However, installed versions are:
 - lodash: `0.1.0` instead of newest `0.10.0`
 - react: `0.0.1` instead of newest `0.14.10`

In reality where using `^` there are more schemes of a version:

 - <span style="color: red">**MAJOR**</span>.<span style="color: green">**MINOR**</span>.<span style="color: orange">**PATCH**</span>
 - **0**.<span style="color: red">**MAJOR**</span>.<span style="color: green">**MINOR**</span>
 - **0**.**0**.<span style="color: red">**MAJOR**</span>

</details>

### Good practises

 - Start your project form version 0.1.0
   - indicates it is immature
   - leaves a room for shipping non-breaking changes

### Links
 - https://semver.org/
 - https://docs.npmjs.com/about-semantic-versioning
 - https://semver.npmjs.com/
