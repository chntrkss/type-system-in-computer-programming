# Types systems in computer programming

In computer programming, type system is a logical system comprising a set of rules that assigns a property called a type (for example, integer, floating point, string) to every "term" (a word, phrase, or other set of symbols). Usually the terms are various constructs of a computer program, such as variables, expressions, functions, or modules. A type system dictates the operations that can be performed on a term. For variables, type system determines the allowed values of that term. Type systems formalize and enforce the otherwise implicit categories the programmer uses for algebraic data types, data structures, or other components (e.g. "string", "array of float", "function returning boolean").

Type systems are often specificed as part of programming languages and built into interpreters and compilers, although the type system of a language can be extended by optional tools that perform added checks using the languages's original type syntax and grammar.

The main purpose of a type system in a programming language is to reduce posibilities for bugs in computer programs due to type errors. The given type system in question determines what constitutes a type error, but in general, the aim is to prevent operations expecting a certain kind of value from being used with values of which that operation does not make sense (validity errors). Type systems allow defining interfaces between different parts of a computer program, and then checking that the parts have been connected in a consistent way. This checking can happen statically (at compile time), dynamically (at run time), or as a combination of both. Type systems have other purposes as well, such as expressing business rules, enabling certain compiler optimization, allowing for multiple dispatch, providing a form of documentation.

## Usage Overview

An example of a simple type system is that of the C language. The portions of a C program are the function definitions. One function is invoked by another function. The inferface of a function states the name of the function and a list of parameters that are passed to the function's code. The code of an invoking function states the name of the invoked, along with the names of variables that hold values to pass to it. During execution, the values are placed into temporary storage, then execution jumps to the code of the invoked function. The invoked function's code accesses the values and makes use of them. If the instructions inside the function are written with the assumption of receiving an integer value, but the calling code passed a floating-point value, then the wrong result will be computed by the invoked function. The C compiler checks the types of the arguments passed to a function when it is called against the types of parameters declared in the function's definition. If the types do not match, the compiler throws a compile-time error or warning.

The compiler may also use the static type of a value to optimize the storage it needs and the choice of algorithms for operations on the value. They will thus use floating-point-specific microprocessor operations on those values (floating-point addition, multiplication, etc.).

The depth of type constraints and the manner of their evaluation affect the typing of the language. A programming language may further associate an operation with various resolutions for each type, in the case of type polymorphism. Type theory is the study of type systems. The concrete types of some programming languages, such as integers and strings, depend on practical issues of computer architecture, compiler implementation and language desing.

## Fundamentals

Formally, type theory studies type systems. A programming language have must the opportunity of type check using type system, whether at compile time or runtime, manually annotated or automatically inferred. As Mark Mannase concisely put it:

The fundamental problem addressed by a type theory that programs have meanings. The fundamental problem caused by a type theory is that meaningful programs may not have meanings ascribed to them. The quest for richer type system result from this tension.

Assigning a data type, termed typing gives meaning to a sequence of bits such as a value in memory or some object such as a variable. The hardware of a general purpose computer is unable to discriminate between for example a memory address and an instruction code, or between a character, an integer, or a floating-point number, because it makes no intrinsic distinction between any of the possible values that a sequence of bits might mean. Associating a sequence of bits with a type conveys that meaning to the programmable hardware to form a symbolic system composed of that hardware and some program.

A program associates with at least each value, but it also can occur that one value is associated with many subtypes. Other entities, such as objects, modules, communication channels and dependencies can become associated with a type. Even a type can become associated with a type. The implementation of a type system could in theory associate identification called data type (a type of a value, a type of an object, a type of a type or metatype).

When a programming language evolves a more elaborate type system, it gains more finely grained rule set than basic type checking, but this comes at price when the type inference become undecidable, and when more attention must be paid by the programmer to annotate code or to consider computer-related operations and functioning. It is challenging to find a sufficiently expressive type system that satisfies all programming practices in a type safe manner.

A programming language compiler can also implement a dependent type or an effect system, which enables even more program specifications to be verified by a type checker. Beyond simple value-type pairs a virtual "region" of code is associated with an "effect" component describing what is being done with what, and enabling for example to "throw" an error report. Thus the symbolic system may be a type and effect system, which endows it with more safety checking than type checking alone.

Whether automated by the compiler or specified by a programmer, a type system makes program behavior illegal if outside the type-system rules.

Advantages provided by programmer-specified type systems included:

-   **_Abstraction (or Modularity)_** - Types enables programmers to think at a higher level than the bit or byte, not bothering with low-level implementation. For example, programmers can begin think of a string as a set of character values instead of as a mere array of bytes. Higher still, types enable programmers to think about and express interfaces between two of any-sized subsystems. This enables more levels of localization so that the definitions required for interoperability of the subsystems remain consisten when those two subsystems communicate.

-   **_Documentation_** - In more expressive type systems, types can serve as a form of documentation clarifying the intent of the programmer. For example, if a programmer declares a function as returning a timestamp type, this documents the function when the timestamp type can be explicitly declared deeper in the code to be an integer type.

Advantages provided by compiler-specified type systems include:

-   **_Optimization_** - Static type checking may provide useful compile-time information. For examples, if a type require that a value must align in memory at a multiple of four bytes, the compiler may be able to use more efficient machine instructions.

-   **_Safety_** - A type system enables the compiler to detect meaningless and invalid code. For examples, we can identify an expression 3`/"Hello, World"` as invalid, when the rules do not specify how to divide an integer by a string. Strong typing offers more safety, but cannot guarantee complete type safety.

### Type Errors

A type errors is an unintended condition which might manifest in multiple stages of a program's development. Thus a facility for detection the error is needed in the type system. In some languages, such as Haskell, for which type inference is automated, lint might be available to its compiler to aid in the detection of error.

Type safety contributes to program correctness, but might only guarantee correctness at the cost of making the type checking itself an undecidable problem (as in the Halting problem). In the type system with automated type checking a program may prove to run incorrectly yet produce no compiler errors. Division by zero is an unsafe and incorrectly operation, but a type checker which only runs at compile time does not scan for division by zero in most languages. That division would surface as a runtime error. To prove the absence of these defects, other kinds of formal methods, collectively known as program analyses, are in common use. Alternatively, a sufficiently expressive type system, such as in dependently type system can prevent these kinds of errors (for example, expressing type of non-zero numbers). In addition software testing is an empirical method for finding error that such a type checker would not detect.

[Orjinal Makale](https://en.wikipedia.org/wiki/Type_system)
