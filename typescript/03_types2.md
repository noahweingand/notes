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
*undefined* means that something hasn't been defined yet.
*null* means an absence of a value.
*void* is the return type of a function that doesn't explicitly return anything.
*never* is the type of a function that never returns at all.
```js
// null example
function a(x: number) {
    if (x < 10) {
        return x
    }
    else {
        return null
    }
}

// undefined example
function b() {
    return undefined
}

// void example
function c() {
    let a = 2 + 2
    let b = a * a
}

// never example
function d() {
    throw TypeError('I error')
}

// another never
function e() {
    while (true) {
        doSomething()
    }
}
```

## Enums
Enums are a way to enumerate the possible values for a type. They're unordered data structures that map keys to values.
Two kinds: enums that map from strings to strings, and enums that map from strings to numbers. By convention, enum names are uppercase and singular. Their keys are also uppercase.
```js
enum Language {
    English,
    Spanish,
    Russian
}

// to retrieve a value
let myFirstLang = Language.Russian;
let mySecondLang = Language['English'];

// can split across multiple declarations
enum Language {
    English = 0,
    Spanish = 1,
}
enum Language {
    Russian = 2
}

// can use computed values, don't have to define all
enum Language {
    English = 100,
    Spanish = 200 + 300,
    Russian, // TS infers 501
}

// can use access enums by value and key
let a = Language.English // number
let c = Color[0] // language string

// we can prevent unsafe access w/ const on an enum
const enum Language {
    English,
    Spanish,
    Russian
}

let a = Language.English // language
let b = Language.Tagalog // error - tagalog doesn't exist
let c = Language[0] // error - can only access w/ string literal