# Software Versioning Workflow

This is not meant to be an exhaustive or strict guide to be followed, just an example how we should do Software
Versioning with fast interactions between tagging new Releases by following this [Best Practices](BEST_PRACTICES.md).

Mileage will change per team, project and other factors in the organization.


## The App Requirements

Let's imagine that we are the developer that is about to build Trello for internal use with a very simple set of
requirements.

So the initial requirements state the App:

* Will be protected by a simple Authentication system, with Registration, Login and Password Recovery.
* Is composed by Boards.
* Boards will be made of Lists.
* Lists will contain Cards.


## Development Workflow

* `0.0.1.0` - When Authentication is in a minimal working state.
* `1.0.0.0-Alpha1` - First [Alpha](TERMS_SCOPE.md#alpha) release to collect User feedback on Authentication.
* `0.0.1.1` - Some bug is fixed in Authentication Login due to a User report.
* `1.0.0.0-Alpha2` - Second [Alpha](TERMS_SCOPE.md#alpha) release to collect User feedback on Authentication.
* `0.0.2.0` - Boards functionality is in a minimal working state.
* `1.0.0.0-Alpha3` - Third [Alpha](TERMS_SCOPE.md#alpha) release to collect User feedback primarily on Boards functionality.
* `0.0.3.0` - Validation is improved for Authentication Registration after report of too many registration issues.
* `0.0.3.1` - As per User report bug is fixed when editing Boards.
* `0.0.3.2` - Another bug is fixed in Authentication for Password Recovery.
* `1.0.0.0-Alpha4` - Forth [Alpha](TERMS_SCOPE.md#alpha) release to collect User feedback.
* `0.0.4.0` - Lists functionality is in a minimal working state.
* `1.0.0.0-Alpha5` - Fifth [Alpha](TERMS_SCOPE.md#alpha) release to collect User feedback.
* `0.0.5.0` - Cards functionality is in a minimal working state.
* `1.0.0.0-Alpha6` - Sixth [Alpha](TERMS_SCOPE.md#alpha) release to collect User feedback.
* `0.1.0.0` - A security bug in Authentication is fixed and is backwards [Incompatible](TERMS_SCOPE.md#incompatible).
* `0.1.0.1` - Some bug is fixed with cards being assigned to the wrong list up on creation.
* `0.1.1.0` - In preparation for a [Beta](TERMS_SCOPE.md#beta) Release code is refracted in a backwards [Compatible](TERMS_SCOPE.md#compatible) way.
* `1.0.0.0-Beta1` - First [Beta](TERMS_SCOPE.md#beta) release to continue collecting User feedback.
*  ... base on User Feedback, reported bugs and crashes further development will happen, with more [Beta](TERMS_SCOPE.md#beta) Releases until
    code is stable enough for the first [Release Candidate](TERMS_SCOPE.md#rc-or-release-candidate).
* `1.0.0.0-RC1` - First [Release Candidate](TERMS_SCOPE.md#rc-or-release-candidate) to collect User feedback before we launch the Production Release.
* ... fix reported bugs an release as many [Release Candidates](TERMS_SCOPE.md#rc-or-release-candidate) as needed until is acceptable to make a Production Release.


## Production Workflow

* `1.0.0.0` - The first Production Release.
* `1.0.0.1` - Whoops... fixing some bug after been in Production.
* `1.0.0.2` - Dam... fixing a security issue.
* `1.0.1.0` - Adding one of that fancy stuffs, like be possible to add Labels to the Cards.
* `1.0.2.0` - Add Drag functionality to be able to reorder Lists and Cards.
* `1.0.2.1` - Fix bug when dragging cards.
* ... after a some years and many fast and frequent releases, the necessity to perform a deep change in the Software to
    keep innovating and up to date with technologies is urging.
    While keeping the ongoing development in the `1.0.*` we will start in a separate branch the development for
    `2.0.0.0` [Disruptive](TERMS_SCOPE.md#disruptive) Release, but creating tags only for [Alpha](TERMS_SCOPE.md#alpha), [Beta](TERMS_SCOPE.md#beta) and [Release Candidates](TERMS_SCOPE.md#rc-or-release-candidate) versions.
* `2.0.0.0-Alpha1` - First [Alpha](TERMS_SCOPE.md#alpha) release.
* `1.0.21.10` - Security [Fix](TERMS_SCOPE.md#fix) release.
* `1.0.22.0` - Add new feature.
* `2.0.0.0-Alpha2` - Another [Alpha](TERMS_SCOPE.md#alpha) release.
* `1.0.22.0` - Bug [Fix](TERMS_SCOPE.md#fix) release.
* `2.0.0.0-Beta1` - First [Beta](TERMS_SCOPE.md#beta) release.
* `2.0.0.0-Beta2` - Another [Beta](TERMS_SCOPE.md#beta) release.
* `1.1.0.0` - High level priority security fix that can't be applied without making a backwards [Incompatible](TERMS_SCOPE.md#incompatible) change.
* `2.0.0.0-Beta3` - One more [Beta](TERMS_SCOPE.md#beta) release.
* `2.0.0.0-RC1` - First [Release Candidate](TERMS_SCOPE.md#rc-or-release-candidate).
* `1.1.1.0` - a new feature being released.
* `2.0.0.0` - Second Production Release for a [Disruptive](TERMS_SCOPE.md#disruptive) identifier.
* ... and the life continues with more fixes and new features.
* `2.0.10.0-LTS_2019-05` - now that we have a stable `2.*` we create a [LTS](TERMS_SCOPE.md#lts-or-long-term-support) tag, targeting only [Fix](TERMS_SCOPE.md#fix) Releases, to help Businesses that only use Software with [Long Term Support](TERMS_SCOPE.md#lts-or-long-term-support) policies.
* `1.1.2.0-EOS_2018-05` - now that we have released an [LTS](TERMS_SCOPE.md#lts-or-long-term-support) tag is also time to announce the [End of Support](TERMS_SCOPER.md#eos-or-end-of-support) for `1.*`.
* ... keep going in fast and safe pace with Explicit Versioning [Best Practices](BEST_PRACTICES.md) for Software Versioning.


[HOME](README.md)
