## Description

It's common to see potential D users comment that large parts of the standard library aren't usable with the GC.
It's difficult to counter that assertion without any data - I don't think anyone knows how much of Phobos can be used from @nogc code, nor could we point people to a resource for more information.

Similarly to Python's former wall of shame that got renamed to the wall of superpowers, it would be great if D had a webpage titled "Are we @nogc yet", preferably with a code-coverage-style visualisation of Phobos.
At the very least, a list of functions/structs/classes that are @nogc compatible.

## What are rough milestones of this project?

- annotation of Phobos unittests with @nogc if possible
- a tool to extract the information of what Phobos code is called/covered by such unittests
- a web page to visualise the data

## How does this project help the D community?

It helps the community by helping to dispel the myth that the GC is central to D programming.

## Recommended Skills

Webpage design and implementation

## What can students expect to get out of doing this project?

Students will learn how to design and implement a webpage.
Students will get familiar with the structure of a standard library and with memory allocation techniques.
Also, they will learn about the infrastructure involved in building and testing production software.

## Point of contact

Atila Neves

## References

https://github.com/dlang/phobos
https://dlang.org/spec/function.html#nogc-functions
