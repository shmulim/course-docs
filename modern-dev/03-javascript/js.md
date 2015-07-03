[Operators](#operators) | [Data Types](#data-types) | [Conditionals](#conditionals) | [Loops](#loops) | [String Manipulation](#string-manipulation) | [Objects](#objects) | [Functions](#functions) | [Regex](#regex) | [HTML Form Values](#html-form-values) | [Events](#events) | [Type Conversion](#type-conversion) | [Scope](#scope) | [This](#this) | [Prototype](#prototype) | [Dates](#dates) | [DOM Traversal & Manipulation](#dom-traversal-and-manipulation)

## Basic Syntax

A great overview of basic JS syntax can be found on [this Wikipedia page](https://en.wikipedia.org/wiki/JavaScript_syntax).

## Operators

### Unary Operators

[Unary operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Unary_operators) require only one operand, which can come before or after the operator.

```
operator operand

// or

operand operator

// example

x++
++x
```

#### typeof

The [typeof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof) operator returns a value that indicates the type of the operand.

```
typeof operand

// or

typeof (operand)
```

```js
typeof (5 + 2)	// returns "number"
typof "javascript"  // returns "string"
```

### Arithmetic

TBC.

### Assignment

The [assignment operator](#https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment_Operators) assigns the value of the right operand to the left operand.

```
operand operator operand
```

```js
x = "javascript"

console.log(x) 	// returns "javascript"
```

Mathematical assignment and incrementing can happen through a number of shorthand operators. For example:

```js
// traditional version
x = x + y

// shorthand version
x += y
```

The above syntax can be used in conjunction with all mathematical operators (`-`, `*`, `/`, `%`).

### Comparison 

TBC.


- Basic syntax
- Operators (||, &&, ===, etc)
	- unary
	- conditional
	- inequality
- Data types
- Conditionals
- Loops
- String manipulation
	- Search
	- Split
	- Replace
	- Reverse
	- Convert
- Objects
	- CRUD
	- Global object
	- Serialization
	- Add / remove properties
- Functions
- Basic Regex
- Retrieve and set form field values
- Basic events (i.e. click, mouse over)
- Type conversion
- Variable scope
- This
- Dates (different formats)
- DOM traversal / manipulation