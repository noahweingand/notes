# Functional Programming
## Immutability and Architecture
All race conditions, deadlock conditions, and concurrent update problems are due to mutable variables. You cannot have a race condition or a concurrent update problem if no variable is ever updated. You cannot have deadlocks without mutable locks.

All problems we face in concurrent applications--all the problems we face in apps that require multiple threads, and multiple processors--cannot happen if there are no mutable variables. Make sure that the systems you design will be robust in the presence of multiple threads and processors. 

Is immutability practicable? Yes, if you have infinite storage and processor speed. Immutability can be practicable, if certain compromises are made.

## Segregation of Mutability
Common compromise to immutability is to segregate the application, or the services within, into mutable and immutable components. The immutable components perform their tasks in a purely functional way, without using any mutable variables. The immutable components allow for the state of their variables to be mutated.

Immutable components (x5) -> mutable component <-> transactional memory

Use some kind of transactional memory to protect the mutable variables from concurrent updates and race conditions. Transactional memory simply treats the variables in memory the same way a database treats records on disk. It protects those variables with a transaction- or retry-based scheme.

## Event Sourcing
With modern technology improving day-by-day, the more memory we have, and the faster our machines are, the less we need mutable state.

Event sourcing is a strategy wherein we store the transactions, but not the state. When state is required, we simply apply all the transactions from the beginning of time. If we have enough storage and enough processor power, we can make our applications entirely immutable--and therefore, entirely functional.
* CR vs. CRUD
* how version control works

