Good software systems begin with clean code.

SOLID principles tell us how to arrange our functions and data structures into classes, and how those classes should be interconnected.
* GOALS - to create mid-level software that
    * tolerate change
    * are easy to understand
    * are the basis of components that can be used in many software systems

* SOLID
    * SRP: The Single Responsibility Principle
        * An active corollary to Conway's law: The best structure for a software system is heavily influenced by the social structure of the organization that uses it so that each software module has one, and only one, reason to change.
    * OCP: The Open-Closed Principle
        * For software systems to be easy to change, they must be designed to allow the behavior of those systems to be changed by adding new code, rather than changing existing code.
    * LSP: The Liskov Substitution Principle
        * To build software systems from interchangeable parts, those parts must adhere to a contract that allows those parts to be substituted one for another.
    * ISP: The Interface Segregation Principle
        * Advises software designers to avoid depending on things that they don't use.
    * DIP: The Dependency Inversion Principle 
        * Code that implements high-level policy should not depend on the code that implements low-level details. Rather, details should depend on policies.

# SRP: The Single Responsibility Principle
SRP might be least well understood. *a module should have one, and only one, reason to change*

## Accidental Duplication
*Separate code that different actors depend on*

## Merges
Merge conflict on a file that different actors depend on. Always a risk, no matter how helpful the tools to resolve are.

## Solutions
Separate code, but then you have new classes instantiated and that need to be tracked.