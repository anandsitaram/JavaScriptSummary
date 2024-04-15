**Page Update in Progress
This page is currently being updated. Stay tuned for more content!**

# JavaScript in Summary

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
```
### Declarative Function with return
```javascript
function doSquare(num) {
    return num * num;
}
console.log(doSquare(5));
```
## Function Expression
Assigning a function to a variable. Here the function acts like a value.
// Anonymous Function - Function without a name
```javascript
var b = function() {
    console.log('Function expression');
};
b();

// Named Function Expression
var c = function xyz() {
    console.log("c called");
};
c();  // c called
// xyz(); // Throws ReferenceError: xyz is not defined.
```
## Arrow Function

```javascript
var test = () => console.log("This is an Arrow Function");
test();

const incr = a => a + 1;
console.log(incr(5));

const add = (a, b) => a + b;
console.log(add(5, 7));
```

## Objects

```javascript
const person = {
    name: "QA",
    age: 32,
    isEligible: true,
    // It can have functions too
    greet() {
        console.log("Hi, this is " + this.name + " and age is " + this.age);
    }
};

console.log(person.name);
console.log(person.age);
console.log(person.isEligible);
person.greet();
```
