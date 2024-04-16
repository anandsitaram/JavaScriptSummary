**Page Update in Progress
This page is currently being updated. Stay tuned for more content!**

# JavaScript in Summary

JavaScript is a versatile language with the following characteristics:
- **Synchronous & Single-threaded:**
  - Executes code sequentially.
  - Processes one command at a time.

- **Weakly Typed:** 
  - Data types can change dynamically.

- **Object-oriented:**
  - Supports logical objects for data organization.

- **Versatile:** 
  - Runs in browsers, on computers, and servers.

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

1. **var:** 
   - Globally or locally scoped.
   - Value can be reassigned.

2. **let:** 
   - Block scoped.
   - Value can be reassigned.

3. **const:** 
   - Block scoped.
   - Value cannot be reassigned.

Preference of usage: `const` > `let` > `var`

## Functions

### Declarative Function

```javascript
function printHello() {
    console.log("This is a Declarative function");
}
printHello();
// Output: This is a Declarative function
```
### Declarative Function with return
```javascript
function doSquare(num) {
    return num * num;
}
console.log(doSquare(5));
// Output: 25
```
## Function Expression
Assigning a function to a variable. Here the function acts like a value.
// Anonymous Function - Function without a name
```javascript
var b = function() {
    console.log('Function expression');
};
b();
// Output: Function expression
// Named Function Expression
var c = function xyz() {
    console.log("c called");
};
c();
// Output: c called
// xyz(); // Throws ReferenceError: xyz is not defined.
```
## Arrow Function

```javascript
var test = () => console.log("This is an Arrow Function");
test();
// Output: This is an Arrow Function

const incr = a => a + 1;
console.log(incr(5));
// Output: 6

const add = (a, b) => a + b;
console.log(add(5, 7));
// Output: 12
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
// Output:
// QA
// 32
// true
// Hi, this is QA and age is 32
```
## Arrays

```javascript
const arrExample=["Mandya",false,"Mysore",67,"Testing"]

console.log(arrExample[2])

for(let arr of arrExample){
    console.log(arr)
}

const cities=["Mandya","Bengaluru","Mysore","Mangalore"]

console.log(cities.length)

cities.push('Udupi');

const newArray=cities.map(a=>a+" "+"QA");
console.log(newArray)

const copiedArray = newArray.slice();
```

## Spread and Rest Operators

###  Spread operators - a.k.a three dots operator (...)

Used to  quickly copy all or parts of an existing array or objects into another array or objects

```javascript
// Example for Array
const cities=["Mandya","Bengaluru","Mysore","Mangalore"]
const copyArray= [... cities]
console.log(copyArray)
```

```javascript
// Example for Objects
const person ={

   name:"QA",
   age:32,
   isEligible:true,
   greet(){
      console.log("Hi this is "+this.name+" and age is "+this.age)
}
}
const copyObject={... person};
console.log(copyObject)
```

###  Rest operators - a.k.a three dots operator (...)



```javascript
function returnValues(arg1,arg2,arg3,arg4){
  return [arg1,arg2,arg3,arg4]
}

console.log(returnValues(3,4,5,8))
```

Using Rest operator for above code

```javascript
function returnValues(...args){
  return args
}

console.log(returnValues(3,4,5,8))
```

Real time example for rest operator usage

```javascript
const fun=(...input) =>{
        let sum = 0;
        for (let i of input) {
        sum += i;
        }
        return sum;
        }
        
console.log(fun(1, 2)); //3
console.log(fun(1, 2, 3)); //6
console.log(fun(1, 2, 3, 4, 5)); //15  
```

##  Destructuring

###  Object Destructuring 

Consider an example :- 
```javascript
const account = {

    accountName:"Savings",
    accountNo:677343431212,
    isActive:true,
    custumer:"John Hammer",
    greet(){
        console.log("Hi this is "+this.custumer+" and accountNo is "+this.accountNo)
    }

};

```

To fetch only account name from account object the old way was

```javascript
const acctName=account.accountName
console.log(acctName)

```
and the other way was

```javascript
const accountNme=(acc)=>{
    console.log(acc.accountName)
}
accountNme(account);
```

Using object destructuring \
Note that the  variable names inside the curly bracket should match with the names inside object

```javascript
const {accountName,accountNo} = account;

console.log(accountName)
console.log(accountNo)


const acct=({isActive,custumer})=>{
    console.log(isActive,custumer)
}
acct(account);

const {accountName,...rest}=account;
console.log(accountName)
console.log(rest)
console.log(rest.isActive)
```

###  Array Destructuring 

Consider an example :-
```javascrpt

const captials=["Delhi","Chennai","Hyderbad","Mumbai","Lucknow"]

```
Using Array destructuring 

```javascrpt
const [cap1,cap2]=captials;

console.log(cap1)
console.log(cap2)


const [cap3,cap4,...rest]=captials;
console.log(cap3)
console.log(cap4)
console.log(rest)

```

##  Higher-Order Functions and Callbacks

A Higher-order functions are regular functions that take other functions as arguments or return functions as their
results. Eg:

```javascript

function hello(name){
    console.log("Hello "+name)
}

function greet(func){
    const name="Testing";
    func(name);
}

greet(hello);

```
Here greet is a higher order function \
hello is a callback function

One more Example:- 

```javascript


const area = radius=> Math.PI * radius * radius;

const calculate = function(radiusArr,operation){
    const output = [];
    for(let rad of radiusArr){
        output.push(operation(rad))
    }
    return output;
}

const radius =[7,9,6,8];
console.log(calculate(radius,area))

```

Here calculate is a higher order function \
area is a callback function

A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.
