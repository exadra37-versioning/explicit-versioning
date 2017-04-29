# Background

As a Developer I like to be Organized as much as possible, this means for me to really separate as much as I can into their own places.

So when I started to use Git and Tag each release after sometime I realised that [SemVer]((http://semver.org/)) is not separating everything as I would like, therefore in my point of view, not fully addressing the problem is trying to solve.


## The Problem

So the current [SemVer]((http://semver.org/)) adopts a versioning schema that uses `MAJOR.MINOR.PATCH` and in a glance it seems perfect.

To add a **_Bug Fix_** we will increment only the `PATCH` version number, like from `1.0.0` to `1.0.1`.

When we need to add, at same time, a **_Bug Fix_** and a **_New Feature_** then both the `MINOR` and `PATCH` version number need an update, like from `1.0.1` to `1.1.0`.

In the case we have one or both of the above situations, that are **_Backwards Incompatible_**, we will need to increment the `MAJOR` version number and reset the `MINOR` and `PATCH`, like from `1.1.0` to `2.0.0`.

Wait, wait and wait... So we need to update the `MAJOR` from `1` to `2` for the smallest change that is **_Backwards Incompatible_** as if we are performing a complety **_Overhaul_** in the code?

So in my point of view the `MAJOR` should only be used to go from `1.1.0` to `2.0.0`, when a big revolution happens in the **_CODE_** and a significant part of is **Public Api** changes.

For me something to handle changes that are **_Backwards Incompatible_** is missing between `MAJOR` and `MINOR`.


## A different angle

We, as developers, are preaching to write easy to understand code that is more difficutl to misunderstand and uses variable numbers that help enforce that, trying to make the code as explicit as possible. 

But when it comes to versioning, we're doing the complete opposite of what we're asking others to do. And that creates confusion, which leads to lots of misunderstandings which lead to misuse on a large scale. *Simply put, ilogic.*


## An Example

I use Laravel Framework professionally in a daily base, so I will use it as example to show as one that does not follow the [SemVer]((http://semver.org/)) version schema, or if you prefer, it works around it when needs to release changes that are **_Backwards Incompatible_**.

On the time I was using Laravel 4, in composer the required version was `4.*`, because I was aiming for all **_Bug Fixes_** and **_New Features_**, but one day everything broken due to the upgrade from `4.0.*` to `4.1.*`.

The solution was to aim only for **_Bug Fixes_**, therefore composer requirement changed to `4.1.*`, but even here at some point a **_Bug Fix_** was **_Backwards Incompatible_** and the `MAJOR` was not incremented, only the `MINOR`, resulting again in a broken APP.

So the final solution was to cap composer to require a specific version `4.1.21`(21 is random) to avoid breaking deployments to production.

This is far from the ideal process to maintain our software up to date, specially regarding **_Security_** and **_Bug Fixes_**.

[Check here](https://laravel.com/docs/5.3/upgrade) for more details on how Laravel handles releases with **_Backwards Incompatible_** changes using the `MINOR` version number.


## Considerations

Maybe is because of this [current schema]((http://semver.org/)) not addressing very well the problem, that we see a lot of different approaches across a lot of popular projects.

Following [SemVer]((http://semver.org/)) increment of `MAJOR` version for a **Bug Fix** that is **_Backwards Incompatible_** is not aligned with the **_Business_** and **_Marketing_** needs for lots of commercial projects, to not say all.

If the versioning where having a number to increment for **_Backwards Incompatible_** changes, then **Businees**, **Marketing** and **Developers** will not need to work around [SemVer]((http://semver.org/)) current schema. At same time they will avoid the need to reflect on this questions and their proposed solutions:

* [End up in version 42.0.0 very rapidly](https://github.com/mojombo/semver/blob/master/semver.md#if-even-the-tiniest-backwards-incompatible-changes-to-the-public-api-require-a-major-version-bump-wont-i-end-up-at-version-4200-very-rapidly).
* [Using Your Best Judgement](https://github.com/mojombo/semver/blob/master/semver.md#what-if-i-inadvertently-alter-the-public-api-in-a-way-that-is-not-compliant-with-the-version-number-change-ie-the-code-incorrectly-introduces-a-major-breaking-change-in-a-patch-release)


## The Solution

For me the solution, in my personal projects, is to use from now on this schema `PUBLIC_API.BACKWARDS_INCOMPATIBLE.CODE_IMPROVMENT.BUG_FIX`.

Why I have changed the names... because if I want a **Semantic Versioning** schema, the names for each version number must reflect better what they represent, without further explanations.

So when introducing a change that is **_Backwards Incompatible_** I will go from `1.0.1.1` to `1.1.0.0`, instead of the current [SemVer]((http://semver.org/)) practice of going from `1.1.1` to `2.0.0`.


## Conclusion

This are my 2 cents on it and anybody is free to disagree and discuss it.

I will start to use this new approach in all my personal projects.

Professionally I will continue to follow the Software Development guidelines in place at the Company I work for.
