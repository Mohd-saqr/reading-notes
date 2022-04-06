# purely functional programming.
purely functional programming usually designates a programming paradigm—a style of building the structure and elements of computer programs—that treats all computation as the evaluation of mathematical functions.

Purely functional programming consists of ensuring that functions, inside the functional paradigm, will only depend on their arguments, regardless of any global or local state. A pure functional subroutine only has visibility of changes of state represented by state variables included in its scope.

## Difference between pure and impure functional programming
A program is usually said to be functional when it uses some concepts of functional programming, such as first-class functions and higher-order functions. However, a first-class function need not be purely functional, as it may use techniques from the imperative paradigm, such as arrays or input/output methods that use mutable cells, which update their state as side effects. In fact, the earliest programming languages cited as being functional, IPL and Lisp, were both "impure" functional languages by the current definition.

## Properties of purely functional programming
Each evaluation strategy which ends on a purely functional program returns the same result. In particular, it ensures that the programmer does not have to consider in which order programs are evaluated, since eager evaluation will return the same result as lazy evaluation.

1- Parallel computing: Purely functional programming simplifies parallel computing since two purely functional parts of the evaluation never interact.


2- Data structures :Purely functional data structures are often represented in a different way than their imperative counterparts.[6] For example, array with constant-time access and update is a basic component of most imperative languages and many imperative data-structures, such as hash table and binary heap, are based on arrays. Arrays can be replaced by map or random access list, which admits purely functional implementation, but the access and update time is logarithmic. Therefore, purely functional data structures can be used in languages which are non-functional, but they may not be the most efficient tool available, especially if persistency is not required.


## Purely functional language
A purely functional language is a language which only admits purely functional programming. Purely functional programs can however be written in languages which are not purely functional.

## Which languages are purely functional
So, a pure functional language is simply one in which a function cannot observe things besides its inputs. Given that, we can split the current crop of Pacman-complete languages up into pure and impure ones:

Pure languages
 
