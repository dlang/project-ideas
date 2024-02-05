## Description

D has been using the auto-tester for a very long time (it was created in 2006 for D) and it has become a crucial part of D's infrastructure as it allows testing a PR on four platforms (Windows, Linux, OSX, FreeBSD) and 9 configurations (x86 <-> x86_64).
However, as only one person has access to it, it is very hard for the community to make changes to it and integrate newer testing strategies which is why over the time many other CI systems have been added (CircleCi, SemaphoreCI, Azure, Jenkins ...).
A few years back, the project tester (the CI system which checks out the ~top50 dub projects and runs their test suite on every pull request) has been moved to Buildkite and we have made excellent experiences with it.
In short, it allows to setup agents anywhere and connect to a central build server.
This allows to use cheap or university resources, but also unavailable resources.
For example, FreeBSD isn't available on most CI systems.
As the aggregation of various CI systems leads to a lot of problems (frequent failures, no access, knowledge separation, upgrade issues), the goal of this project would be to unify all systems, s.t. all of them are run on Buildkite.

## What are rough milestones of this project?

- Migrate CircleCi to Buildkite. CircleCi is used for CodeCov coverage report generation
- Migrate dmd Azure jobs. Azure is used to test various Windows builds.
- Migrate CirrusCi jobs. CirrusCi is used to test builds of various compiler backends on various platforms.
- Migrate C++ interoperability tests
- Migrate the documentation tester

There are a few side dependencies:

- build/auto-publish Debian docker image for Buildkite agents
- setup agents for Windows (Step 3), OSX (Step 5) + FreeBSD (Step 5)

Extensions:

- setup performance statistic agent
- migrate from makefiles to D build files or viceversa

## How does this project help the D community?

A single CI system means that we can take full advantage of the individual features (e.g. Buildkite supports automatic retries of failing builds), no problems with CI machine access (you only need to be able to access one system, not 7), less confusion and missing knowledge (currently only very few people understand how all systems work).
Moreover, being a single system will make it a lot more reliable and easier to extend (e.g. DragonFlyBSD testing or Musl tests). However, most importantly we will be able to do upgrades and changes to the system a lot easier (e.g. upgrading from Debian 8 to 9, upgrade gcc, llvm, ...).

## Recommended Skills

- Experience with Debian
- Experience with CI systems
- Experience with Bash
- Experience with Docker

## What can students expect to get out of doing this project?

As we currently use almost all popular CI services, the student will aggregate a lot of experience with them which very likely will help him for future jobs as well.
Moreover, he will learn more DevOps skills and gather experience on best-practices for reliable CI systems.

## Point of contact

Sebastian Wilzbach, Dennis Korpel, Max Haughton

## References

- https://github.com/dlang/ci
- https://wiki.dlang.org/Guidelines_for_maintainers#CI
- https://buildkite.com/dlang
- https://auto-tester.puremagic.com
- https://github.com/braddr/at-client
- https://github.com/braddr/d-tester
