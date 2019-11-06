# UnNamed Language

*<sub>for short: unl</sub>*

## Motivation

*My Imagination of the best language*

I wanted to learn how compilers (& interpreters) & language design work

-> because it is meant to be to learn, it will be compiled to typescript / javascript

## Syntax

Mostly taken from EcmaScript & Python

## Next Statement

Semicolons are used to end a statement or a new line after the end of a statement

## Comments

```js
// Full comment until new line
/* Inline Comment */
/*
  Multiline Comment
*/
```

## Declarations

Dynamic, current scope and down:

```js
let
```

Constants (not meant to be re-defined):

```js
const
```

Declare a variable:

```js
let name = expression
```

## Primitives

### Booleans

```js
true
// and
false
```

### Strings

Normal Strings:

```js
"some string"
```

Template Strings:

```js
`${expression}`
```

Multiline Strings:

```txt
let name =
  """
  This is a multiline string
  This is with 0-space indentation // Full line comment
    This is with 2-space indentation /* Inline / Multiline Comment */
      This is with 4-space indentation \// This is NOT a comment
  """; // semicolon is optional
```

The multiline string above with `\//` is not a comment, because to be a full comment it would need to match `//`

### undefined and null

`undefined` means the value is not existing

`null` the value exists, but has nothing assigned to it

example (with json)

```jsonc
{
  "value": null, // value exists, but has nothing assigned to it
  "value2": "" // value exists, and has a string assigned to it
  // when trying to access any other value, it will be `undefined`
}
```

### Functions

`func` is the keyword for a function, it can have the following attributes:
- `func*` "*" means it is a generator function, which allows `yield`
- `async function` "async" means it is an async function, which always returns an `Promise` and allows the use of `await`
- `() => {}` for "this" keeping functions - is only allowed for embedded functions

Example:

```txt
func name(param1, param2) { // name is optional for embedded functions
  // statements
}
```

### Regex

fully like ecmascript

### Arrays

Arrays work with `[` as a start and end with `]`, the operator between types is `,`

Example:

```js
[1, 2, 3, 4, 5]
["hi", "hi", "hi", "hi"]
// OR
array ["hi", "hi2", "hi3"] // the "array" idenifier is optional
```

### Maps

Maps are *like* arrays, but work with a `key-value` pair

Example:

```txt
map [
  "key" => "value",
  "key" => null,
  "key" => func() {
    // functions in here can be anything, they dont need to return anything
  },
  "key" => () => {}, // embedded functions
  "key" => map [], // nested maps
  "key" => any
];
```

## Operators

### Comparison Operators

For `==`, `===`, `!=`, `!==` they are the same as [in EcmaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Equality_operators)

#### is Operator

The `is` operator returns true if the left-side is the type of the right-side

Example:

```coffee
value is type // syntax
"hi" is string
3 is number
array [] is array
map [] is map
```

#### Number Operators

Only work if both sides are a number, implicitly has an `value is number` check for every side

##### >

returns `true` if the left-side is a higher number than the right-side

##### <

returns `true` if the left-side is a lower number than the right-side

##### >=

returns `true` if the left-side is a (higher number OR the same) than the right-side

##### <=

returns `true` if the left-side is a (lower number OR the same) than the right-side

### Logical Operators

#### AND (&&)

returns `true` if both sides return `true`

```txt
expr && expr
```

#### OR (||)

returns `true` if one of the sides returns `true`

```txt
expr || expr
```

### Invert (!)

returns the opposite of the following expression

```js
!expr // syntax
!true // returns "false"
!false // returns "true"
// any other than Boolean, will result in an error
```

### Grouping

Group statements together  
-> Evaluate all the group operations first, then the parent operation

```js
(expr) Operator (expr) // syntax
(true && true) || (true && true)
!(true) && !(true)
("hi" is string) && ("hi".length === 2)
```

## if else

`if-else` statements always need parentheses AND block statements

```js
if () {} else {}// syntax
if (true) {
  // scoped operation
}
if (false) {
  // scoped operation when statement is true
} else {
  // scoped operation when statement is false
}
```

## switch

`switch` statements always need parentheses AND block statements
the `switch` operator uses `===` to evaluate `value` against each `case`'s `value`

```js
switch () {
  case expr:
  default:
    break;
} // syntax

const value = "Hello";
switch (value) {
  case "Hello1":
    break;
  case "Hello":
    break;
  default:
    break;
}
```

## Spreading / Destructuring

using the `...expr` or called the Spread Operator

```js
const arr1 = array [1, 2, 3];
const arr2 = array [4, 5, 6];
[...arr1, ...arr2] // Result: [1, 2, 3, 4, 5, 6]

const obj1 = {
  key: 1,
  key2: 2
}
const obj2 = {
  key3: 3,
  key4: 4
}
{...obj1, ...obj2} // Result: { key: 1, key2: 2, key3: 3, key4: 4}

const obj1 = {
  key: 1,
  key2: 2
}
const obj2 = {
  key: 4,
  key3: 6
}
{...obj1, ...obj2} // Result: { key: 4, key2: 2, key3: 6}

const { key1: key } = { key1: "hi" }
// "key" will be "hi"

func t(...args) {} // "args" will be an array of all arguments

const { key1: key, ...rest } = { key1: "hi", key2: "2", key3: "3" }
// "key" will be "hi"
// "rest" will be "{key2: '2', key3: '3'}"
```

## throw

`throw` is used to throw an error

## try-catch-finally

This operator is used to `try` an scoped block, if it throws an error, the `catch` block gets executed, and in any case the `finally` block gets executed (after all before)

```js
try {
  throw new Error("hi")
} catch (err) {
  log(err);
} finally {
  log("finally");
}
```

## for

*<sub>Please add documentation</sub>*

## while

*<sub>Please add documentation</sub>*

## loop

`loop` is executed until an `break;` gets executed

```coffee
loop {
  if (condition) {
    break;
  }
  // execute code
}
```

## do

`do` is used as a one-time function for variable declaration

```coffee
const value = do {
  if (condition) {
    return "1";
  }
  if (condition2) {
    return "2";
  }
  return "3";
}
```

## enum

`enum` is used for enumerations, they cannot be modified
-> when no value is assigned, it will be a number, auto-incremented

```ts
enum Name {
  Key,
  Key = Assignment
}

(value === Name.Key) // usage
```

with `enum*` there cannot be an assignment, the key will always be used and return a string

```txt
enum* Name {
  Key1,
  Key2
}

"Key1" === Name.Key1 // Result: "true"
```

## Pipeline

*<sub>Please add documentation</sub>*

## Discard operator (_)

the char `_` is used as a discard operator
-> it cannot be used to get from it ("Cannot use '_', it is the Junk operator")
-> it can be assigned to

```js
let _ = "something"; // is allowed, but "_" can never be used
let { key1: _ } = { key1: "hi" };
let []
```

## Scoping

using `{}` always creates a scope

```js
func () {
  // new scope
}
if () {
  // new scope
}

const key1 = "hi";
if (true) {
  log(key1); // exists
  const key2 = "2";
}

log(key2); // ReferenceError! There is no "key2" in this scope
```

## import / export

Not planned for now

## Classes

`class` is used to create an class

```js
class Hi {
  constructor() {

  }
}
```
