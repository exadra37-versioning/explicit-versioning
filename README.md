# Explicit Versioning

To know why another Software Versioning Schema exists as an alternative to [SemVer]((http://semver.org/)) please read [here](WHY.md).

Explicit Versioning is a specification for developers that care about releasing software and explicit announce intended
breaking changes, by using an extra required identifier to handle **[Incompatible](TERMS_SCOPE.md#incompatible)** changes that are intentional.


* [HOME](#)
    + [Specification Schema](#specification-schema)
        - [Required Identifiers](#required-identifiers)
        - [Optional Identifiers](#optional-identifiers)
    + [Explicit Versioning vs Semantic Versioning](#explicit-versioning-vs-semantic-versioning)
* [Best Practices](BEST_PRACTICES.md)
* [FAQ](FAQ.md)
* [Terms Scope](TERMS_SCOPE.md)
* [Why Explicit Versioning](WHY.md)
* [Workflow](WORKFLOW.md)


# Specification Schema

Explicit Versioning specification will use a schema composed of 4 identifiers, that are represented like:

* **Disruptive**.**Incompatible**.**Compatible**.**Fix**-*Optional_Identifiers*

## Required Identifiers

Creating a Tag, by incremented any of the 4 required identifiers, represents a new Software Release.

Given `1.0.0.0` as the first version for a **_Production Release_**:

* **[Disruptive](TERMS_SCOPE.md#disruptive)**
    + is incremented when deep changes will occur across the API, Web or CLI Interfaces in a way that will be **Disruptive**
        for the previous User Experience.
    + version will go from `1.0.0.0` to `2.0.0.0`.
* **[Incompatible](TERMS_SCOPE.md#incompatible)**
    + is incremented when a _Intentional_ and backwards **Incompatible** change is introduced as part of a bug or security
        fix, while keeping the affected User Experience localized in a specific Feature of the API, Web or CLI Interfaces.
    + version will go from `1.0.0.0` to `1.1.0.0`.
* **[Compatible](TERMS_SCOPE.md#compatible)**
    + is incremented when adding or improving functionality in a **Compatible** way with previous User Experience when using
        the API, Web or CLI Interfaces.
    + version will go from `1.0.0.0` to `1.0.1.0`.
*  **[Fix](TERMS_SCOPE.md#fix)**
    + is incremented when a bug is fixed, or a security gap is solved without affecting the previous User Experience for
        using the API, Web or CLI Interfaces.
    + version will go from `1.0.0.0` to `1.0.0.1`.

>**NOTE**:
>
> The usage of `v` preceding the schema, like `v1.0.0.0` is not recommend, but is acceptable.


## Optional Identifiers

Each team of Developers and Organization may have specific needs in their Software release process that they can address
with the Optional Identifiers.

### Recommended:

* **[Alpha](TERMS_SCOPE.md#alpha)**
    + Unstable Release to gather earlier user feedback in the Development process.
    + Tags will look `1.0.0.0-Alpha1`, `1.0.0.0-Alpha2`...

* **[Beta](TERMS_SCOPE.md#beta)**
    + Experimental Release to test viability and get user feedback.
    + Tags will look `1.0.0.0-Beta1`, `1.0.0.0-Beta2`...

* **[RC - Release Candidate](TERMS_SCOPE.md#rc-or-release-candidate)**
    + A stable release to get user feedback and hunt last minute bugs.
    + Tags will look like `1.0.0.0-RC1`, `1.0.0.0-RC2`...

* **[LTS - Long Term Support](TERMS_SCOPE.md#lts-or-long-term-support)**
    + A release that guarantees the software will be supported until a certain date, using the format `LTS_YYYY-MM`.
    + Tag `1.0.0.0-LTS_2019-05`
        - guarantees support until May of 2019 for any [Incompatible](TERMS_SCOPE.md#incompatible), [Compatible](TERMS_SCOPE.md#compatible)
            or [Fix](TERMS_SCOPE.md#fix) Release.
        - to be required as `1.*`.
    + Tag `1.1.0.0-LTS_2019-05`
        - guarantees support until May of 2019 for any [Compatible](TERMS_SCOPE.md#compatible) or [Fix](TERMS_SCOPE.md#fix) Release.
        - to be required as `1.1.*`.
    + Tag `1.0.1.0-LTS_2019-05`
        - guarantees support until May of 2019 for any [Fix](TERMS_SCOPE.md#fix) Release.
        - to be required as `1.0.1.*`.

* **[EOS - End of Support](TERMS_SCOPER.md#eos-or-end-of-support)**
    + A Release to announce the termination of support for a Software Life Cycle.
    + MUST NOT be used when already exists a _LTS_ Release for this Software Life Cycle.
    + Given that the last tag was `1.0.8.22`:
        - the End of Support tag will be `1.0.9.0-EOS_2018-05`.
        - guarantees support for Security and Bug _Fixes_ Releases until May of 2018.
        - to be required as `1.0.9.*`.
        - in any tag from `1.*` MUST NOT exist a _LTS_ Release.

### MAY be used to:

* Give a name to the Release, like `1.0.0.0-Xenial_Xerus`.
* Track the build, like `1.0.1.0-Build_12345`.
* For other wisely chosen situations, that should be Explicit and not Implicit.

### MUST NOT be used to:

* Announce a Major release.
* Breaking change release.
* New Feature release.
* Security release.
* Patch release.
* To identify a Developer. Use branches instead.
* Any other situation that clashes with the Required Identifiers implementation.

>**NOTE:**
>
> When creating a tag a message can be added, therefore don't use an Optional Identifier for something that is more
>   appropriated to be told in the message.


# Explicit Versioning vs Semantic Versioning

The most known specification for Semantic Versioning is [SemVer](http://semver.org/), but many other ones exist, due to the nature of Semantic Versioning approach to Software Versioning.

Basically Explicit Versioning main differential factors to Semantic Versioning schema are:

* Isolates any **[Incompatible](TERMS_SCOPE.md#incompatible)** Release, that is _Intentional_, from any other type of Release, by using 4 identifiers `v.x.y.z`, instead of the 3 ones of Semantic Versioning `x.y.z`.
* Only increment the most left number when a **[Disruptive](TERMS_SCOPE.md#disruptive)** situation happens in the Software, not to be increment per the
    minimal backward **[Incompatible](TERMS_SCOPE.md#incompatible)** change.
* Remove/reduces the ambiguity from usage/interpretation of the versioning schema. A good example why Semantic Versioning has this issue is the amount of different versioning schemas redefining the meaning of their 3 identifiers `x.y.z`.

