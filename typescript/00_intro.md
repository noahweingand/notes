# Introduction
## Pros
Safer, serve as documentation for yourself and future engineers, easier refactoring, less unit tests

**Type Safety** - Using types to prevent programs from doing invalid things

## The guts
compiler -> abstract syntax tree -> bytecode -> runtime
TypeScript compiles into JavaScript instead of compiling straight into bytecode.
Before TSC generates an AST, it typechecks your code.

TS
1. TypeScript source -> TypeScript AST
2. AST is checked by typechecker
3. TypeScript AST -> JavaScript source
4. JS source -> JS AST
5. JS AST -> bytecode
6. Bytecode is evaluated at runtime

Different JS engines: V8 (NodeJS, Chrome, Opera), SpiderMonkey (Firefox), JSCore (Safari), Chakra (Edge)
These different engines make JavaScript an interpreted language.

## The Type System
**Type System** - A set of rules that a typechecker uses to assign types to your program.

2 types of type systems (generally):
1. tell compiler what type of everything is w/ explicit syntax
2. type systems that infer the types automatically

In TypeScript, you can explicitly annotate your types, or you can let TS infer most of them for you.

**In general, it is good style to let TS infer as many types as it can for you, keeping explicitly typed code to a minimum.**

### How are types bound?
Dynamic type binding means that JS needs to actually run the program to know the types (JS doesn't know before program is ran). 
TS is a gradually typed language. Gradually typed languages are useful for migrating legacy codebases from JS to TS.

### Are types automatically converted?
JS is weakly typed, meaning it will use a series of rules to resolve invalid statements (to prevent an runtime error).

### When are types checked?
JS - see above.
TS typechecks at compile time. It statically analyzes your code for errors.

## Setup

