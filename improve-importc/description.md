# Improve ImportC

## Description

[ImportC](https://dlang.org/spec/importc.html) adds the ability to import C code directly from a D module.
Because of many complexities, there are a number of open issues.
Sometimes valid C features are rejected:
- [Issue 23040](https://issues.dlang.org/show_bug.cgi?id=23040) - importC: optimizer rejects null dereference of volatile pointer

Some C features have not been implemented:
- [Issue 23053](https://issues.dlang.org/show_bug.cgi?id=23053) - importC: can't take address of some compound-literals
- [Issue 23374](https://issues.dlang.org/show_bug.cgi?id=23374) - ImportC: only 1 designator currently allowed for C struct field initializer
- [Issue 23888](https://issues.dlang.org/show_bug.cgi?id=23888) - ImportC: VLAs (Variable Length Arrays) are not supported

And there are some issues related to integration with D code:
- [Issue 23812](https://issues.dlang.org/show_bug.cgi?id=23812) - ImportC: allow adding function attributes to imported C functions
- [Issue 24444](https://issues.dlang.org/show_bug.cgi?id=24444) - ImportC: no way to specify where header files "live"
- [Issue 23389](https://issues.dlang.org/show_bug.cgi?id=23389) - ImportC: types from core.stdc.* are distinct types when imported from C

In general:
- [List of open issues with importC keyword](https://issues.dlang.org/buglist.cgi?bug_status=NEW&component=dmd&keywords=ImportC%2C%20&keywords_type=allwords&list_id=247849&product=D&query_format=advanced&resolution=---)

The goal is to implement fixes and reduce the number of open issues.

## What are rough milestones for this project

Since ImportC is a moving target, it's hard to pre-define an exact list of issues: issues are being opened and fixed all the time.
At the start of the project, a selection of actionable existing issues will be made which will become milestones.

Alternatively, issues can be found by testing popular C libraries with ImportC and checking for deficiencies.
Such deficiencies can be errors when compiling the library with ImportC, but also missing translations of macros which are part of the library's public API.

## Expected outcome

- A number of open issues with the 'importC' keyword have been fixed.
- New issues from testing ImportC in the wild have been reduced and put in the issue list
- ImportC has been improved in other ways (Documentation, tooling support, etc.)

## Recommended Skills

- Experience with C and D.
- Familiarity with dmd repository and its contribution process.

## Get started

- [ImportC specification page](https://dlang.org/spec/importc.html)
- [List of open issues with importC keyword](https://issues.dlang.org/buglist.cgi?bug_status=NEW&component=dmd&keywords=ImportC%2C%20&keywords_type=allwords&list_id=247849&product=D&query_format=advanced&resolution=---)
- [List of popular binding packages on dub](https://code.dlang.org/?sort=score&category=library.binding&skip=0&limit=20) (can be used to find C libraries to test ImportC with)
