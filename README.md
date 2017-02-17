# Semantic Versioning Specification

To know why I am not using [SemVer]((http://semver.org/)) please see [here](WHY.md).


## Specification

My Semantic Version schema can be represented like `PUBLIC_API.BACKWARDS_INCOMPATIBLE.CODE_IMPROVMENT.BUG_FIX`.

Given `1.0.0.0` as the first version for a **_Production Release_**:

* **BUG_FIX**:
    + _Security Fix(es)_ will increment version to `1.0.0.1`.
    + _Bug Fix(es)_ will increment version to `1.0.0.1`.
* **CODE_IMPROVMENT**:
    + _New Features_ will increment version to `1.0.1.0`.
    + _Refracting Code_ that do not impact _Public Api_ will increment version to `1.0.1.0`.
    + _Deprecating Code_ that do not impact _Public Api_ will increment version to `1.0.1.0`.
    + _Removing Code_ that do not impact _Public Api_ will increment version to `1.0.1.0`.
* **BACKWARDS_INCOMPATIBLE**:
    + _Any Breaking Code Change_ will increment version to `1.1.0.0`.
*  **PUBLIC_API**:
    + _Major Code Overhaul_ that impacts a significant number of end points in the _Public Api_ will increment
        version to `2.0.0.0`.


## Conclusion

Basically I only miss from [SemVer]((http://semver.org/)) version schema the possibility to isolate
**_Backwards Incompatible_** changes and consequently a better isolation for when I should increment their `MAJOR`
version number.
