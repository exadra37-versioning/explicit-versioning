# SOFTWARE VERSIONING BEST PRACTICES

When versioning Software for Development or Production releases we must adhere to some guidelines to keep consistency
across releases and ensure we obey to the Versioning Specification we use.


## Software Versioning earlier to Release Fast and to Release Often

With the tools available for Developers to build test suites and automate all the Release process in a Continuous
Integration pipeline, the accumulation of new features with bugs and security fixes to go in the same release is not
any more a wise solution.

Nowadays we should take advantage of all this tools to build a pipeline that allows us to have fast releases per feature
and bug or security fix, with several releases per day if necessary.

Go from Development to the first Production Release as fast as you have a stable and complete set of working
functionality that have gather a positive feedback from your Users during the [Alpha](TERMS_SCOPE.md#alpha), [Beta](TERMS_SCOPE.md#beta) and [Release Candidates](TERMS_SCOPE.md#rc-or-release-candidate).

Don't wait to Release for Production until all fancy and nice to haves are ready, they are improvements that can be
introduced later and may benefit from the feedback received after the Software is being actively used in Production.


## When Software Releases MUST be tagged

* As soon as we get a minimal working state for a feature or set of features that depending on each other.
* Immediately after you have done a bug or security [Fix](TERMS_SCOPE.md#fix).
* Each time a [Compatible](TERMS_SCOPE.md#compatible) code improvement/refracting is done.
* Every time a intentional backwards [Incompatible](TERMS_SCOPE.md#incompatible) change is introduced.
* When a major overhaul takes place with a [Disruptive](TERMS_SCOPE.md#disruptive) impact in the way the Software is used through the Web, API, CLI
    Interfaces or as a dependency in other Software.

## When [Optional Identifiers](README.md#optional-identifiers) should be used

* For [Alpha](TERMS_SCOPE.md#alpha), [Beta](TERMS_SCOPE.md#beta) and [RC](TERMS_SCOPE.md#rc-or-release-candidate) releases to collect feedback from final Users in the several stages of development. Earlier we
    start, better the Users will be served once released into Production.
* To tag a release as having [Long Term Support(LTS)](TERMS_SCOPE.md#lts-or-long-term-support).
* When we want to announce the [End of Support](TERMS_SCOPER.md#eos-or-end-of-support) for a Production release `1.*` after we already have launched the `2.*`.

## Think twice when a [Incompatible](TERMS_SCOPE.md#incompatible) release is to

* Fix a bug.
* Fix a series of related bugs.
* Add a new feature.
* Add a set of features.
* Code improvements/refracting.

>**NOTE:**
>
> Think more than twice if you still want to make an [Incompatible](TERMS_SCOPE.md#incompatible) Release due to any of the above scenarios and I am
>   sure that you will find a better solution.
>
> As last resource you can try the [Rubber Duck](https://rubberduckdebugging.com/) approach used for debugging, but you can switch the Rubber Duck by a real person
>   if it makes you feel more comfortable ;).


## Testing and Testing and more Testing

* To avoid involuntary [Incompatible](TERMS_SCOPE.md#incompatible) Releases our Software MUST be covered by a strong suite of tests for Unit, Integration and Acceptance tests.
* Without a strong suite of tests it will be easy to accidentally tag a [Compatible](TERMS_SCOPE.md#compatible) or [Fix](TERMS_SCOPE.md#fix) Release that will break things.
