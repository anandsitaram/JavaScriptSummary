# JavaScript Basics

## JavaScript in Summary

JavaScript is a versatile language with the following characteristics:
- **Weakly Typed:** No explicit type assignment; data types can change dynamically.
- **Object-oriented:** Data can be organized into logical objects, supporting primitive and reference types.
- **Versatile:** Can run in browsers, directly on computers, and servers, performing a broad range of tasks like browser events, DOM manipulation, file, and database operations.

## Datatypes

JavaScript has 8 data types:
1. String
2. Number
3. BigInt
4. Boolean
5. Undefined
6. Null
7. Symbol
8. Object

The object data type can contain:
1. Object
2. Array
3. Date

## Variables

JavaScript has three variable types:
1. **var:** Declares a variable globally or locally to an entire function, and its value can be reassigned.
2. **let:** Declares a variable with block scope, and its value can be reassigned.
3. **const:** Declares a constant variable with block scope, and its value cannot be reassigned once defined.

Preference of usage: `const` > `let` > `var`

## Functions

### Declarative Function

```javascript
function printHello() {
    console.log("This is a Declarative function");
}
printHello();
