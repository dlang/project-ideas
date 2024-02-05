## Description

Currently, the D runtime library contains `core.stdcpp`.
This creates a few problems, and was essentially a mistake.
It needs to be moved to its own repository.

## What are rough milestones of this project?

- Create a repository for core.stdcpp;
- Copy the code the code there;
- Put in place a comprehensive CI, which uses DMD at least, ideally LDC and GDC as well;
- Add a dub package;
- Deprecate the bindings in druntime;

## How does this project help the D community?

It improves the C++ integration of D.

## Recommended Skills

- familiarity with C++
- familiarity with CI testing tools

## What can students expect to get out of doing this project?

- knowledge of working on a real compiler runtime
- knowledge on how to create, build, maintain a library
- how to be the owner of a library

## Point of contact

@geod24
