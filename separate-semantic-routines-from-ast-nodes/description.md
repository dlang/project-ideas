## Description

In the DMD compiler codebase, AST nodes are defined as classes within various files. The ideal structure for these nodes is to have minimal fields and methods focused solely on field queries. However, the current state of the DMD frontend deviates from this ideal. AST nodes are laden with numerous methods that either perform or are dependent on semantic analysis. Furthermore, many AST node files contain free functions related to semantic analysis. Our objective is to decouple AST nodes from these functions, both directly and indirectly.

This project is ideal for someone that has no prior experience with compilers but wants to understand how a compiler works by doing valuable work.

## What are rough milestones for this project?

A list of the files that contain AST nodes that depend on semantic analysis is provided in [this project](https://github.com/orgs/dlang/projects/41). Ideally, by the end of the programme, most, if not all, of the files should be marked as done from the list. Below, a potential schedule is provided:

M1:

- get up to speed with the compiler contribution process (building from source, PR guidelines)
- understand the code organization
- break semantic dependency for ast nodes in `attrib.d` and `cond.d`

M2:

- break dependency for ast nodes in `dclass.d`, `declaration.d`, `denum.d`, `dmodule.d`, `dstruct.d`

M3:

- break dependency for ast nodes in `dtemplate`, `func.d`, `mtype.d`, `dsymbol.d`

M4:

- make other necessary changes for other files that depend on semantic analysis indirectly, as a result of prior code changes.
- implement checks that make sure that semantic analysis dependencies are not added to ast node files.

## Recommended Skills

OOP, visitor pattern, D\C\C++, Git, algorithms and data structures

## Point of contact

Razvan Nitu (@RazvanN7)

## References

[Blog post that gives more context for the project](https://dlang.org/blog/2024/02/22/dmd-compiler-as-a-library-a-call-to-arms/)
[Guide on how to tackle the project](https://github.com/dlang/dmd/blob/master/CONTRIBUTING.md#refactoring-the-dmd-ast)
[The project where we are tracking the progress](https://github.com/orgs/dlang/projects/41/views/1)
