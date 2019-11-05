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
