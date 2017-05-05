# TERMS SCOPE

The intention of this documentation is to give more detail about the scope of each Term used in the context of
    Explicit Versioning.


## For Required Identifiers

### Disruptive

* a shift occurs in the architecture that completely breaks the way it was previously used.
* conventions used are subject to profound changes that is no more compatible with the previous versions.
* previous functionality goals is maintained but achieved in a completely different way that requires to relearn them.
* concept changes deeply and lot's of new functionality are added while other ones are removed.

[HOME](README.md)


### Incompatible

* a security fix can be only implemented in a way that isn't compatible with previous versions usage.
* a bug fix can only be implemented by breaking the compatibility with previous versions usage.
* one functionality needs to be imperatively removed, due to Business and/or Legal demands.
* the only way to introduce a new critical/imperative/legal functionality will affect how another one is used.

[HOME](README.md)


### Compatible

* functionality is added without compromising existing usability.
* code is refracted/added/removed without changing is Public Interface.

[HOME](README.md)


### Fix

* bug is fixed without affecting how everything is used.
* security fix is implemented while keeping functionality untouched in how is used.

[HOME](README.md)


## For Optional Identifiers

### Alpha

* Is a Release with a minimal working state for the incorporated functionality.
* Should be considered unstable once is prone to bugs and crashes.
* This type of Release allows final Users to start giving earlier feedback.
* Will be used to collect feedback that will help to shape the ongoing Development.
* Allows deviations from User expectations to be detected earlier in the Development, making them cheap to fix.
* Very prone to backwards Incompatible changes.

[HOME](README.md)


### Beta

* Is a Release with a much more complete state for the incorporated functionality then Alpha Releases.
* Should be considered almost stable, but still prone to bugs and crashes.
* This type of Releases should reflect the User feedback from previous Alpha Releases.
* Everything still open to change here, once some functionality can be added only for evaluation and viability purposes.
* User feedback continues to be fundamental for shaping the ongoing Development.
* Still prone to Incompatible changes.

[HOME](README.md)


### RC or Release Candidate

* Is a Release where all the functionality is in a full working state.
* Should be considered stable and only prone to minor bugs and crashes are not expected at this stage.
* If user feedback was respected and jumping from Beta to Release Candidate was not precipitated, then Incompatible
    changes are not expected.
* User feedback still fundamental to achieve a Production Release with a pretty good stable state.
* Next Release Candidate should be only used to accommodate bug fixes, for more deep changes you MUST consider to go
    back to Beta Releases.

[HOME](README.md)


### LTS or Long Term Support

* Is a Release where is guaranteed a life span for the current version with support for Bug and Security fixes.
* For example bug fixes are guaranteed for 1 year and security fixes for 2 years.
* Lot's of companies only use Software with a defined LTS, more longer the LTS better is the like hood of being adopted.
* Means that no more active development will occur on it for any of the 4 required identifiers after termination of
    given periods.

[HOME](README.md)


### EOS or End of Support

* MUST not be used with LTS tagged Releases, once LTS already have the periods defined for security and bugs fixes.
* When we want to announce that a version have reached is end of line for any type of support.
* A period of 1 year should be given for security fixes.
* A period of 6 months should be given for bugs fixes.
* Means that no more active development will occur on it for any of the 4 required identifiers after termination of
    given periods.
