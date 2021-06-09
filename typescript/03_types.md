# All About Types
**Type** - a set of values and the things you can do w/ them.

## any
Default type when you and TS can't figure out what type something is. Last resort type, avoid when possible.
Exhibits behavior like regular JavaScript, defeats point of typechecker.

## unknown
Use case: where the type of a value isn't known ahead of time. 
1. TS will never infer a type as unknown-- you have to explicitly annotate it.
    * let a: unknown = 30
2. You can compare values to values that are of type unknown.
    * let b = a === 123
3. But, you can't do things that assume an unknown value is of a specific type; you have to prove value is really of that type.
    * if (typeof a === 'number') { let d = a + 10 }

## boolean
true/false. Almost entirely expressed through let a = false vs. let a: boolean = false.
Booleans in TS can be expressed as **Type Literals** (a type that represents a single value and nothing else). [let e: true = true].
'const' will explicitly annotate variables as type literals since it knows the value will never change.

## number
the set of all numbers, integers, floats, positives, negatives, Infinity, NaN, and so on.

## bigint
newcomer to JS and TS. Not natively supported by every JS engine. Declarations same as boolean and number.

## string
Declarations same as boolean and number.

## symbol
Relatively new language feature that arrived with one of the latest major JS revisions (ES2015). They're used as an alternative to string keys in objects and maps, in places where you want to be extra sure that people are using the right well-known key and didn't accidentally set the key.

## Objects
TS's object types specify the shapes of objects. Notably, they can't tell the difference between simple objects (the {} kind) and more complicated ones (the 'new Blah') kinds. This is by design. JS is structurally typed, so TS favors that style of programming over a nominally typed style.

**Structural Typing** - a style of programming where you just care that an object has certain properties, and not what its name is (nominal typing). Also called duck typing in some languages.

Ex:
* let a: object = { b: 'x' }

If you access b, you'll get a error saying property b doesn't exist.

Leave off explicit annotation:
* let a = { b: 'x'}
* a.b //works

This is called object literal syntax. You can either let TS infer your object's shape for you, or explicitly describe it inside curly braces.
* let a: {b: number} = { b: 12 }

Declaring an object as 'const' will not automatically infer our object type because objects are mutable.

```js
let c: {
    firstName: string
    lastName: string
} = {
    firstName: 'john',
    lastName: 'barrowman'
}

class Person {
    constructor(
        public firstName: string, // public is shorthand for this.firstName = firstName
        public lastName: string
    ){}
}

c = new Person('matt', 'smith')
```

How do you tell TS that something may be optional in an object?
```js
let a: {
    b: number
    c?: string,
    [key: number]: boolean
}
```
1. a has a property b that's a number
2. a might have a property c that's a string. And if c is set, it might be undefined.
3. a might have any number of numeric properties that are booleans

Here is what we can assign to a:
```js
a = {b: 1}
a = {b: 1, c: undefined}
a = {b: 1, c: 'd'}
a = {b: 1, 10: true}
a = {b: 1, 10: true, 20: false}
a = {10: true} // false, property b missing
a = {b: 1, 33: 'red'} // 'string' is not assignable to type 'boolean'
```

### Index Signatures
```js
let airplaneSeatingAssignments: {
    [seatNumber: string]: string
} = {
    '34D': 'Boris Cherny',
    '34E': 'Bill Gates'
}
```
tells Typescript that the given object might contain more keys. The way it is read is "For this object, all keys of type T must have values of type U."

### Quick Object Summary
Optional (?) isn't the only modifier you can use when declaring object types. You can also mark fields as read-only (this is, you can declare that a field can't be modified after it's assigned an initial value--kind of like const for object properties) with the *readonly* modifier:
```js
let user: {
    readonly firstName: string
} = {
    firstName: 'abby'
}

user.firstName //string
user.firstName = 'noah' // error
```

Object literal notation has one special case: empty object types ({}). Every type--except null and undefined--is assignable to an empty object type, which can make it tricky to use. Try to avoid these when possible:
```js
let danger: {}
danger = {}
danger = {x: 1}
danger = []
danger = 2
```
1. Object literal notation (like {a: string}), also called a *shape*. Use this when you know which fields your object could have, or when all your object's values will have the same type.
2. Empty object literal notation ({}). Try to avoid this.
3. The object type. Use this when you just want an object, and don't care about which fields it has.
4. The Object type. Try to avoid this.

