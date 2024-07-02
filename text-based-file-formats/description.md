# Text-Based File Formats

## Description

Version 3 of Phobos, the D standard library, is currently in development. In the new Phobos, we would like to include a package that provides modules for reading and writing various text-based file formats. XML, JSON, and YAML in particular, and other formats as time allows.

The goal of this project is to establish a range-based API for reading and writing text-based file formats. The API should take advantage of the range redesign for Phobos v3. Ideally, the interface should be as uniform as possible across formats while exposing format-specfic details as necessary.

Several text-based file format libraries exist in D's package registry at [code.dlang.org](https://code.dlang.org/). These can serve as inspiration, or potentially a starting point for a new implementation.

The initial draft of the redesigned range interface is expected to be ready before DConf '24, which begins two days after the start of Milestone 1 of SAOC 2024. The SAOC particpant who works on this project will need to become familiar with the new range interface, so should consult with Jonathan M. Davis (@jmdavis), who is overseeing the range redesign, upon notification of a successful SAOC application, and should be prepared to adapt as necessary if the interface changes during the course of the event.

## What are rough milestones of this project?

- gain a thorough understanding of the range interface and review existing libraries
- determine the features that will be included in the new package and design a range-based API for reading and writing text-based file formats
- implement readers and or writers for one or more formats, based on consultation with the project mentor

## How does this project help the D community?

XML, YAML, and JSON files are everywhere. Manipulating them should be as easy as possible, without requiring the programmer to search for and evaluate multiple libraries. A performant implementation in the statandard library reduces the barrier.

## Recommended skills

- Experience with C++ templates
- Experience with text-based file formats
- Experience with code build automation tools

## What can students expect to get out of doing this project?

The student will be exposed to the process of designing an API and creating a library module from scratch. The student will be among the first D programmers to employ the redesigned range API in production code.

## Point of contact

@burner, @RazvanN7, @mdparker

