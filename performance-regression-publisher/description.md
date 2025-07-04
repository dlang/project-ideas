# Performance Regression Publisher

**Mentor:** [Dennis Korpel](dkorpel@gmail.com)

## Description

The D compiler currently does not have an automated performance regression test.
Oftentimes pull requests that claim to improve compiler performance are being made (be it spatial or temporal).
However, it's up to the reviewer to actually believe the committer or to test things on their own.
To make things simpler and more transparent, we want to implement a bot that monitors all the pull requests made to the compiler codebase and analyzes the compiler's performance with and without the pull request.

The list of stats should include, but not be limited to:

- size of some predefined binaries (like a "hello world" program)
- compile time of popular projects
- compiler size
- runtime of test suite

Adding more performance tests, such as stress tests also falls under the scope of this project.
Ideally the bot could also store a history of performance regressions within a web page.

## Project milestones:

1. Analyze the best way to publish the results: it could be a GitHub action, a bot that sends data to a website.
Depending on your skills and preferences, we expect you propose something and toghether we will decide what's best.
1. Implement the initial part that simply collects how long running the testing pipeline took and publishes the result.
1. Decide on other metrics that need to be collected and implement them.
1. Add more stress tests to the compiler testing suite.

## Resources

- [Compiler pull request queue](https://github.com/dlang/dmd/pulls)
