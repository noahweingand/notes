# All About Types
**Type** - a set of values and the things you can do w/ them.

## any
Default type when you and TS can't figure out what type something is. Last resort type, avoid when possible.
Exhibits behavior like regular JavaScript, defeats point of typechecker.

## unknown
Use case: where the type of a value isn't known ahead of time. 
1. TS will never infer a type as unknown-- you have to explicitly annotate it.
2. You can compare values to values that are of type unknown.
3. But, you can't do things that assume an unknown value is of a specific type; you have to prove value is really of that type.

## boolean


