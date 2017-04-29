# Explicit Versioning

To know why another Software Versioning Schema exists as an alternative to [SemVer]((http://semver.org/)) please read [here](WHY.md).

Explicit Versioning is a specification for developers that care about releasing software and explicit announce intended
breaking changes, by using an extra required identifier to handle Incompatible changes that are intentional.


# Specification Schema

Explicit Versioning specification will use a schema that can be represented like:

* **Release**.**Incompatible**.**Compatible**.**Fix**-*Optional_Identifiers*


## Required Identifiers

Given `1.0.0.0` as the first version for a **_Production Release_**:

* **Release**
    + is incremented when changing the API, changing the UX, switching to a new recommended version or ending support
        for previous versions.
    + version will go from `1.0.0.0` to `2.0.0.0`.
* **Incompatible**
    + is incremented when adding, changing, removing code or changing the UX while breaking compatibility with previous
        versions.
    + version will go from `1.0.0.0` to `1.1.0.0`.
* **Compatible**
    + is incremented when adding, changing or removing code while remaining compatible with previous versions.
    + version will go from `1.0.0.0` to `1.0.1.0`.
*  **Fix**
    + is incremented when a bug is fixed, or a security gap is solved.
    + version will go from `1.0.0.0` to `1.0.0.1`.

>**NOTE**:
>
> The usage of `v` preceding the schema, like `v1.0.0.0` is not recommend, but is acceptable.


## Optional Identifiers

Each team of Developers and Organization may have specific needs in their Software release process that they can address
with the Optional Identifiers.

### Optional Identifiers are not intended to be used for:

* Announce a Major release.
* Breaking change release.
* New Feature release.
* Security release.
* Patch release.
* Any other situation that clashes with the Required Identifiers implementation.

### Optional Identifiers Usage Examples

#### Targeting `2.0.0.0` Production Release:

* `2.0.0.0-Alpha3` - where 3 is the third Alpha Release, that will be incremented until be ready for a Beta Release.
* `2.0.0.0-Beta1` - where 1 is the first Beta Release, that will be incremented until be ready for a Release Candidate.
* `2.0.0.0-RC2` - where 2 is the second Release Candidate, that will be incremented until be ready for a Production Release.

#### Other Usage Examples:

* `1.0.0.8-Build_12345` - When for some reason the Build number needs to be associated with the release.
* `1.0.1.0-Release_Name` - For when Teams/Organizations like to give a Human name to their releases that normally are
    associated with a Project/Milestone.

Remember that Tags can have a message associated with them, therefore Optional Identifiers MUST_NOT be used for that purpose.


# Conclusion

Basically Explicit Versioning main differential factors to [SemVer]((http://semver.org/)) version schema are:

* the possibility to isolate intentional **_Incompatible_** releases from any other type of Release.
* only increment the most left number when a Major situation happens in the Software, not to be increment per the
    minimal backward incompatible change.
* remove/reduces ambiguity from usage/interpretation of the versioning schema.
