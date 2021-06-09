# Types cont.
## Type Aliases
You can declare a type alias that points to a type.
```js
type Age = number

type Person = {
    name: string
    age: age
}
```
Aliases are never inferred by TS, you have to type them explicitly.
```js
let age: Age = 55

let driver: Person = {
    name: 'James May'
    age: age
}
```

You can't declare a type twice.
```js
type Color = 'red'
type Color = 'blue' // Error
```

## Union and Intersection Types
TS gives special type operators to describe unions and intersections of types: | for unions and & for intersection.
```js
type Cat = { name: string, puurs: boolean}
type Dog = { name: string, barks: boolean, wags: boolean}
type CatOrDogOrBoth = Cat | Dog
type CatAndDog = Cat & Dog
```

## Arrays
General rule of thumb: keep arrays homogenous (same type)
```js
let a = [1, 2, 3]
var b = ['a', 'b']
let c: string[] = ['a']
```

## Tuples
Slightly different notation since similar to arrays.
```js
let a: [number] = [1]
// a tuple of [first name, last name, birth year]
let b: [string, string, number] = ['malcolm', 'gladwell', 1963]
b = ['queen', 'elizabeth', 'ii', 1926] //error type 'string' is not assignable to type 'number'

// an array of train fares, which sometimes vary depending on direction
let trainFares: [number, number?][] = [
    [3.75],
    [8.25, 7.70],
    [10.50]
]
// equivalently
let moreTrainFares: ([number] | [number, number])[] = [ ]

// Tuples also support rest elements, which you can use to type tuples w/ minimum lengths:
let friends: [string, ...string[]] = ['Sara', 'Noah', 'Kathryn', 'Bob'] // list of strings w/ at least 1 element
let list: [number, boolean, ...string[]] = [1, false, 'a', 'b', 'c']
```

## null, undefined, void, and never
