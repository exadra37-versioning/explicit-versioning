# Explicit Versioning Specification

To know why I am not using [SemVer]((http://semver.org/)) please see [here](WHY.md).


## Specification

My Explicit Version schema can be represented like `Release.Incompatible.Compatible.Fix`.

Given `1.0.0.0` as the first version for a **_Production Release_**:

* **Release**
    + is incremented when changing the API, changing the UX, switching to a new recommended version or ending support for previous versions,
    + version `1.0.0.0` to `2.0.0.0`.
* **Incompatible**
    + is incremented when adding, changing or removing code while breaking compatibility with previous versions or changing the UX,
    + version `1.0.0.0` to `2.0.0.0`.
* **Compatible**
    + is incremented when adding, changing or removing code while remaining compatible with previous versions,
    + version `1.0.0.0` to `2.0.0.0`.
*  **Fix**
    + is incremented when a bug is fixed, or a security gap is solved.
    + version `1.0.0.0` to `2.0.0.0`.


## Conclusion

Basically I only miss from [SemVer]((http://semver.org/)) version schema the possibility to isolate
**_Backwards Incompatible_** changes and consequently a better isolation for when I should increment their `MAJOR`
version number.
