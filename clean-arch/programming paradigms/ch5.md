# OOP
"The combination of data and function"
* implies o.f() is somehow different than f(o)
"A way to model the real world"
* evasive statement, too loose

Encapsulation, Inheritance, and Polymorphism
* OO is the proper admixture of these 3 things, or at least that an OO lang must support these 3.

## Encapsulation?
OO langs provide easy and effective encapsulation of data and function. As a result, a line can be drawn around a cohesive set of data and functions. Outside of that line, data is hidden and only some of the functions are known. We see this concept in action as the private data members and the public member functinos of a class.

OO doesn't depend on strong encapsulation though (see Java/C#). Many OO langs have little or no enforced encapsulation.

## Inheritance?
If OO langs didn't give us better encapsulation, they sure did give use inheritance.

Inhertiance is simply the redeclaration of a group of variables and functions within an enclosing scope.

## Polymorphism?
Polymorphism is an application of pointers to functions. OO langs made it much safe and much more convenient. OO languages makes polymorphism trivial. It helps OO impose discipline on indirect transfer of control.

## The Power of Polymorphism
OO allows for plugin architecture to be anywhere, for anything (making UNIX I/O device plugins device independent so that you don't have to rewrite the code to support additional addons). See generics, abstractions.

## Dependency Inversion
The fact that OO langs provide safe and convenient polymorphism means that any source code dependency, no matter where it is, can be inverted.
Dependency Inversion allows for flow reversal in a dependency flow of control tree with an interface. Software architects working in an OOP lang have absolute control over the direction of all source code dependencies in the system. They are not constrained to align those dependencies with the flow of control. This is the power of OO from an architect perspective.

It also allows for independently deployability between components of a system. If modules in your system can be deployed independently, they can be developed independently by different teams. That's independent developability.

OOP is the ability, through the use of polymorphism, to gain absolute control over every source code dependency in the system.
