# Improve D Error Messages

## Description

D's error messages are of sufficient quality to get by, however they are fairly uninspiring compared to what is available in other languages with similar aims (C++, Rust etc).

A short example
Let's compare the error messages due to this nonsensical function in D, and then when transliterated into forms other compilers understand.

```d
int square(int num)
{
    return num * num + "chimp";
    //This exact operation was chosen so C++ would also give an error
    //e.g. num + 0.0 is relatively kosher in the eye's of even clang
}
```
D says: <source>(3): Error: incompatible types for (num * num) + ("chimp") int and string

Rust Says:

```
error[E0277]: cannot add `&str` to `i32`
 --> <source>:3:15
  |
3 |     num * num + "chimp";
  |               ^ no implementation for `i32 + &str`
  |
  = help: the trait `Add<&str>` is not implemented for `i32`
```

GCC Says:

```
<source>: In function 'int square(int)':
<source>:3:22: error: invalid conversion from 'const char*' to 'int' [-fpermissive]
    3 |     return num * num + "chimp";
      |            ~~~~~~~~~~^~~~~~~~~
      |                      |
      |                      const char*
```

From these examples we can identify three things that can be improved

D should provide an annotated quotation of the offending code.
D should attempt to be a little more prosaic in the text of it's messages, that is, we find that we can't do x because of y, then we proceed to print y but not x
D should get into the habit (more on this further down) of providing information in a structured manner. This extends beyond aesthetics - to take an example directly from programming, good code doesn't need indentation because it's pretty but rather because it communicates at an almost subconscious level what the flow of the code does.
These problems get worse as the code get's deeper - i.e. it's easy for template error messages like

<source>(3): Error: incompatible types for `(num * num) + ("chimp")`: `int` and `string`
<source>(6): Error: template instance `example.square!int` error instantiating
to get lost in a soup of error message output.

In this case, the compiler needs a mechanism to represent an Error (message) in the abstract as it goes through the compiler. Currently, the basic currency the frontend deals with is just the string

```
nothrow void error(ref const Loc loc, const(char)* format, ...);
```
This is clearly not good enough in 2023. There are areas of the compiler which effectively build their formatting code (like template constraints) - while greatly appreciated these changes are not an effective model for the future.

## What are rough milestones of this project?

- Introduce a compiler flag to turn all new features on or off.
Introducing changes in this area will likely mean updating a very large number of dmd tests - this can be done incrementally if the functionality is turned on.

- Decide on a simple datastructure to handle these error messages while they are being constructed and an API.
This doesn't have to be complicated, just general enough to be passed around safely and supporting having information added to it (notes, references to the docs etc.) in a structured manner.

- Implement the source quotations (wiggles and carats).
When the previous step is done, this feature can be implemented. The existing error message implementation can be rewritten to silently forward to nu-error-messages.

This should be fairly generic code, so it can be reused in less common paths like having two quotations in one error.

- Rewrite existing logic to understand these new error messages.
For example, templates instantiations should be able to effortlessly collect the errors that they cause - i.e so they can be presented in a more useful manner.

An arbitrary target: No D compiler code should use explicit formatting for errors (e.g. \n) eventually.

- Think about the feasibility of adding notes and tips.
If we collect some statistics on the most common error messages (this may be somewhat challenging logistically but we'll see) either directly or by looking at the forums we can add some helpful notes for the programmer or simply a reference to an explanation on dlang.org

These later steps are more for laying down a framework that can easily be added to than full completion.

### How does this project help the D community?
More informative error messages serve two main purposes, the first is to make explicit what the compiler considers to be an error and where, and the second is to aid newcomers to the D programming language by pointing them in the right direction as to how to fix their code.

### Recommended Skills

- Basic familiarity with the compiler frontend
- Familiarity with how the compiler is tested.

### What can students expect to get out of doing this project?

- Knowledge of what working on a real compiler looks and feels like.
- Experience of understanding how actual humans use said compiler

### Point of contact

@maxhaton @RazvanN7
