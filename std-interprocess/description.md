## Description

The goal of this project is to implement a flexible interprocess data structure, synchronization and communication library.
An equivalent library in C++ is Boost Interprocess.
The important goal would be to port all the features from boost.interprocess to D.

## What are rough milestones for this project

- default and custom allocators to operate on shm
- named IPC primitives: shm, semaphores, spinlock, mutex, condvar, barriers
- standard containers like vector, deque, list, string, set that operates on shm
- message queue on shm without relying on the kernel for data transfer
- managed shared memory
- IPC smart pointers

## Expected outcome

A module - `std.interprocess` - merged in the standard library.

## Recommended Skills

Basic D language skills
Understanding of IPC mechanisms and other operating systems concepts
Experience with C++

## Potential mentors

Robert Schadek


## Get started

Boost Interprocess - https://www.boost.org/doc/libs/1_69_0/doc/html/interprocess.html
