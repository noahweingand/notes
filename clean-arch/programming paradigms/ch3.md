# Paradigm Overview
Binary - 1945
Assemblers - Late 1940s
First compiler - 1951 (Grace Hopper)
Fortran - 1953
COBOL, C, Pascal, C++, Java - ad infinitum

Paradigms are ways of programming, relatively unrelated to languages. A paradigm tells you which programming structures to use, and when to use them. To date, there have been three such paradigms.

## Structured Programming
Summary:
* first paradigm to be adopted (but not first to be invented)
* discovered by Dijkstra in 1968
* unrestrained jumps (goto statements) is harmful to program structure
    * replaced with more familiar if/then/else and do/while/until constructs
### Structured programming imposes discipline on direct transfer of control.

## Object-Oriented Programming
Summary:
* discovered two years earlier in 1966 by Dahl and Nygaard
* They noticed that the function call stack frame in the ALGOL language could be moved to a heap, thereby allowing local variables declared by a function to exist long after the function returned. The function became a constructor for a class, the local variables became instance variables, and the nested functions became methods.
* This led inevitably to the discovery of polymorphism through the disciplined use of function pointers.
### OOP imposes discipline on indirect transfer of control.

## Functional Programming
Summary:
* only recently adopted
* Direct result of Alonzo Church, who in 1936 invented 1-calculus while pursuing the same mathematical problem that was motivating Alan Turing at the same time.
    * 1-calculus is the foundation of LISP invented by John McCarthy in 1958.
* A foundation of 1-calculus is immutability (the notion that values of symbols do not change) [functional languages don't have assignment statements]
### Functional programming imposes discipline upon assignment.

## Food for Thought
Each paradigm removes capabilites from the programmer. None of them adds new capabilites. The paradigms tell us what *not* to do. 