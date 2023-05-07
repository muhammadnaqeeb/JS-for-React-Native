

# **Run JS file in VS Code**
To run a JS file inside VS Code first you have to make sure you have **NodeJS** installed.

Once you have NodeJS installed, you can open your JS file in VS Code and simply **press F5 to start debugging.**

This will run the JS file.

# **JS**
JS is interpreted language.

JavaScript (JS) is a lightweight, interpreted, or just-in-time compiled programming language with first-class functions.

JavaScript is a prototype-based, multi-paradigm, single-threaded, dynamic language, supporting object-oriented, imperative, and declarative (e.g., functional programming) styles.
# **Declarations**
- Var 
- Let
- Const

![](https://github.com/muhammadnaqeeb/JS-for-React-Native/blob/main/Images/001.png)

![](https://github.com/muhammadnaqeeb/JS-for-React-Native/blob/main/Images/002.png)

## **Reassignable vs Redeclarable in JavaScript**
### 1. Reassign
A variable is reassignable if it can be assigned a new value using the assignment operator (=) after it has been declared. For example:
```
let x = 5;

x = 10; // x is reassignable
```
In the above code, **x** is declared with the value of **5**, and then it is **reassigned** to the value of **10**.

### 2. Redeclare
A variable is redeclarable if it can be declared again with the same name in the same scope. For example:
```
let x = 5;

let x = 10; // Error // x is not redeclarable 
```
In the above code, x is declared with the value of 5, and then it is declared again with the value of 10. This will result in an error because x is not redeclarable.

However, variables declared with the **var** **keyword** in JavaScript are both **reassignable** and **redeclarable**. For example:
```
var x = 5;

var x = 10; // x is redeclarable

x = 15; // x is reassignable
```

# **Declaring vs Initializing**
### 1. Declaring a variable:
```
let myVariable;
```
In this example, myVariable is declared, but no value is assigned to it yet.
### 2. Initializing a variable:
```
let myVariable = "Hello World!";
```
In this example, myVariable is both declared and initialized with the value "Hello World!".

# **JavaScript Hoisting**
Hoisting in JavaScript is a behavior in which a function or a variable can be used before **declaration**.
```
// using test before declaring

console.log(test);   // undefined

var test;
```
The above program works and the output will be undefined. The above program behaves as
```
// using test before declaring

var test;

console.log(test); // undefined
```
Since the variable test is only declared and has no value, undefined value is assigned to it.

🔑 **Note:** 

In hoisting, though it seems that the declaration has moved up in the program, the actual thing that happens is that the function and variable declarations are added to memory during the compile phase.
 ### 1. Variable Hoisting
In terms of variables and constants, keyword var is hoisted and let and const does not allow hoisting.
```
// program to display value
a = 5;
console.log(a);
var a; // 5
```
In the above example, variable a is used before declaring it. And the program works and displays the output 5. The program behaves as:
```
// program to display value
var a;
a = 5;
console.log(a); // 5
```
However, in JavaScript, initializations are not hoisted. For example,
```
// program to display value
console.log(a);
var a = 5;
```
**Output:** undefined

The above program behaves as:
```
var a;
console.log(a); // undefined
a = 5;
```
Only the declaration is moved to the memory in the compile phase. Hence, the value of variable a is undefined because a is printed without initializing it.

### 2. Function Hoisting
A function can be called before declaring it. For example,
```
// program to print the text
greet();
function greet() {
    console.log('Hi, there.');
}
```
**Output:** Hi, there

In the above program, the function greet is called before declaring it and the program shows the output. This is due to hoisting.

However, when a function is used as an **expression**, an error occurs because only declarations are hoisted. For example.
```
// program to print the text
greet();
let greet = function() {
    console.log('Hi, there.');
}
```
**Output**
```
Uncaught ReferenceError: greet is not defined
```
If **var** was used in the above program, the error would be:
```
Uncaught TypeError: greet is not a function
```
# Scopes
Scope is the location where a variable is defined and the context where other pieces of your code can access and manipulate it.

JavaScript variables have different scopes, they are:

- Global Scope
- Local Scope 
- Block Scope
- Function Scope
- Lexical Scope

### Global Scope
Any variable declared outside of a function is said to have Global Scope.

In simple terms, a variable that can be accessed anywhere in the program is known as a variable with global scope. Globally scoped variables can be defined using any of the three keywords: **let, const**, and **var**. 

![](https://github.com/muhammadnaqeeb/JS-for-React-Native/blob/main/Images/003.png)

### Local Scope
Any variable that you declare inside a function is said to have Local Scope. You can access a local variable can within a function. If you try to access any variable defined inside a function from outside or another function, it throws an error.

![](https://github.com/muhammadnaqeeb/JS-for-React-Native/blob/main/Images/004.png)

### Block Scope
With the introduction of let and const keywords, it added a new type of Scope in JavaScript. You cannot access the variables declared inside a particular block (represented by {}) from outside the block.

Block Scope is the area within if, switch conditions and for, while loops

![](https://github.com/muhammadnaqeeb/JS-for-React-Native/blob/main/Images/005.png)

The block scope does not work with the **var** keyword. You can either use let or const keywords for that.

### Function Scope
With the creation of each new function, it creates a new scope in JavaScript. You cannot access variables defined inside a function from outside the function or from another function. Var, let, and const work similarly when used inside a function.

![](https://github.com/muhammadnaqeeb/JS-for-React-Native/blob/main/Images/006.png)

### Lexical Scope
Lexical Scope allows inner functions to access the scope of their outer functions.

Lexical Scope means that in a nested group (function within a function) of function, the inner functions have to access to the variables and other resources of their parent scope.

This means that the child functions are lexically bound to the execution context of their parents. Lexical scope is sometimes also referred to as Static Scope.
```
function outer() {
  let a = 323;
  function inner(){
      console.log(a);}
  inner()
}

outer();  // 323
```

# Datatypes
![Data Types in JavaScript](.007.jpeg)

- **Number**: represents numeric values.
- **String**: represents textual data.
- **Boolean**: represents a logical value, either true or false.
- **Null**: represents the intentional absence of any object value.
- **Undefined**: represents a variable that has been declared but has not been assigned a value.
- **Symbol**: represents a unique identifier.

```
// Numbers:
let length = 16;

// Strings:
let color = "Yellow";

// Booleans
let x = true;

// Object:
const person = {firstName:"John", lastName:"Doe"};

// Array object:
const cars = ["Saab", "Volvo", "BMW"];

// Date object:
const date = new Date("2022-03-25");
```
🔑 **Note:** 

**null** is a special primitive type. If you run typeof null you’ll get 'object' back, but it’s actually a primitive type.

Everything that is not a primitive type is an object.

## The Concept of Data Types
Without data types, a computer cannot safely solve this:
```
let x = 16 + "Volvo";
```
Does it make any sense to add "Volvo" to sixteen? Will it produce an error, or will it produce a result?

JavaScript will treat the example above as:
```
let x = "16" + "Volvo";
```
🔑 **Note**

When adding a number and a string, JavaScript will treat the number as a string.

**Example**
```
let x = 16 + "Volvo";
```
**Example**
```
let x = "Volvo" + 16;
```
JavaScript evaluates expressions from left to right. Different sequences can produce different results:
```
let x = 16 + 4 + "Volvo";
```
**Result:** 20Volvo
```
let x = "Volvo" + 16 + 4;
```
**Result**: Volvo164

In the first example, JavaScript treats 16 and 4 as numbers, until it reaches "Volvo".

In the second example, since the first operand is a string, all operands are treated as strings.
```
let x = "Volvo" + 16 + 4 + 1;
console.log(x)
```
**Result**: Volvo1641
```
let x = "xyz" - 16;
console.log(x)
```
**Result**: NaN
```
let x = "xyz" * 16;
console.log(x)
```
**Result**: NaN
```
let x = "xyz" + 16 - 1 * 12;
console.log(x)
```
**Result**: NaN
```
let x =   16 - 1 * 10 +"xyz";
console.log(x)
```
**Result:** 6xyz

But if there is number inside “” then it will convert it into number
```
let x =   "15" * 2;
console.log(x)
```
**output**: 30
```
let x =   "15" - 2;
console.log(x)
```
**output**: 13

🔑 **Note:** 

NaN stands for "Not a Number" in JavaScript. It is a value that represents an unrepresentable or undefined value that cannot be converted to a numeric value.

# **Dynamic typing**
Dynamically typed languages are those (like JavaScript) where the interpreter assigns variables a type at runtime based on the variable's value at the time.
## **Explicit vs. Implicit Coercion**
In JavaScript, coercion refers to the process of converting one data type to another. There are two types of coercion: explicit coercion and implicit coercion.

### Explicit coercion
Explicit coercion is when you deliberately convert a value from one data type to another using a built-in method or operator. For example, you can use the Number() method to convert a string to a number or use the String() method to convert a number to a string.
```
const str = "123";
const num = Number(str);
console.log(typeof num); // "number"
```
### Implicit coercion
Implicit coercion, on the other hand, is when JavaScript automatically converts one data type to another during an operation.

```
12 + ""    //Output is "12" as number 12 is converted to string "12"

"15" * 2    //Output is 30 as string 15 is converted to number 15

"15" - "11" //Output is 4 as both the strings are converted to number

undefined + 6  //Output is NaN as undefined could not be converted to number

"Hello" + null   //Output is "Hellonull" as null is converted to string "null"
```

# **== vs ===**
### ==
The == operator is called the **abstract equality operator**, and it performs type coercion before comparing two values. This means that if the two values being compared are of different data types, JavaScript will try to convert them to a common type before making the comparison. For example, the string "3" would be converted to the number 3 before being compared to the number 3.

Here's an example:
```
console.log(3 == "3"); // true
```
In this example, the string "3" is converted to the number 3 before being compared to the number 3, so the expression returns true.

### ===
The === operator is called the **strict equality operator**, and it does not perform type coercion before making the comparison. This means that if the two values being compared are of different data types, the comparison will always return false.
```
console.log(3 === "3"); // false
```
In this example, the string "3" is not converted to a number before being compared to the number 3, so the expression returns false.

In simple words === also checks for datatype.

# **Primitives Vs. Objects**

|**Primitives**|**Objects**|
| :-: | :-: |
|Simple data types|Complex data types|
|Immutable (cannot be changed)|Mutable (can be changed)|
|Stored on the stack|Stored on the heap|
|Copied/passed by value|Copied/passed by reference|
|Examples: number, string, boolean, undefined, null, symbol|Examples: object, array, function, date, regexp|

## Pass by Value vs Pass by Reference

|**Pass by value**|**Pass by reference**|
| :-: | :-: |
|A copy of the value of the argument is passed to the function|A reference to the memory location of the argument is passed to the function|
|Any changes made to the parameter inside the function do not affect the original argument outside the function|Any changes made to the parameter inside the function affect the original argument outside the function|
|Primitive data types are passed by value|Objects and arrays are passed by reference|
|Examples: number, string, boolean, undefined, null, symbol|Examples: object, array, function, date, regexp|

**Pass by Value Example**
```
function changeValue(x) {
  x = 2;
}

let a = 1;
changeValue(a);
console.log(a); // Output: 1
```

In the above example, the function **changeValue** takes a parameter **x** which is a copy of the value of a (which is 1). Inside the function, **x** is changed to **2**, but this change does not affect **a** outside the function.

**Pass by reference example.**
```
function changeArray(arr) {
  arr.push(4);
}

let b = [1, 2, 3];
changeArray(b);
console.log(b); // Output: [1, 2, 3, 4]
```
In the above example, the function **changeArray** takes a parameter **arr** which is a reference to the memory location of **b**. Inside the function, an element is added to **arr**, which also affects **b** outside the function.

# **String Functions**
**length:** returns the length of the string.
```
let str = "hello";

console.log(str.length); // Output: 5
```

**charAt():** returns the character at a specified index in the string.
```
console.log(str.charAt(0)); // Output: "h"
```
**substring():** returns a portion of the string based on a specified start and end index.
```
let str = "hello";

console.log(str.substring(1, 4)); // Output: "ell"
```

**slice():** returns a portion of the string based on a specified start and end index. Can also be used with negative indexes to count from the end of the string.
```
let str = "hello";
console.log(str.slice(1, 4)); // Output: "ell"
console.log(str.slice(-3)); // Output: "llo"
```


**indexOf():** returns the index of the first occurrence of a specified substring in the string. Returns -1 if the substring is not found.
```
let str = "hello";
console.log(str.indexOf("l")); // Output: 2
```

**lastIndexOf():** returns the index of the last occurrence of a specified substring in the string. Returns -1 if the substring is not found.
```
let str = "hello";
console.log(str.lastIndexOf("l")); // Output: 3
```

**toUpperCase():** returns the string in all uppercase letters.
```
let str = "hello";
console.log(str.toUpperCase()); // Output: "HELLO"
```

**toLowerCase():** returns the string in all lowercase letters.
```
let str = "HELLO";
console.log(str.toLowerCase()); // Output: "hello"
```
**replace():** replaces a specified substring with another substring.
```
console.log(str.replace("l", "x")); // Output: "hexlo"
```

**concat():** concatenates two or more strings.
```
let str1 = "hello";
let str2 = "world";
console.log(str1.concat(" ", str2)); // Output: "hello world"
```

**charCodeAt():** Returns the Unicode value of the character at a specified index in a string.
```
const unicode = str.charCodeAt(1); // 101
```
**endsWith():** Returns true if a string ends with a specified string, otherwise false.
```
const str = "hello world";
const endsWith = str.endsWith("world"); // true
```

**includes():** Checks whether a string contains the specified string, and returns true or false.
```
const str = "hello world";
const includes = str.includes("world"); // true
```

**padEnd():** Pads the end of a string with a specified string, until it reaches a specified length.
```
const padded = str.padEnd(10, "."); // 'hello.....'
```
**padStart():** Pads the start of a string with a specified string, until it reaches a specified length.
```
const padded = str.padStart(10, "."); // '.....hello'
```
**startsWith():** Returns true if a string starts with a specified string, otherwise false.
```
const str = "hello world";
console.log(str.startsWith("hello")); // Output: true
console.log(str.startsWith("world")); // Output: false

```
# **Array Function**
**concat():** Joins two or more arrays and returns a new array.
```
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const newArr = arr1.concat(arr2);
console.log(newArr); // Output: [1, 2, 3, 4, 5, 6]
```

**every():** Checks if every element in an array passes a test specified by a function.
```
const arr = [1, 2, 3, 4, 5];
const isGreaterThanZero = (element) => element > 0;
console.log(arr.every(isGreaterThanZero)); // Output: true
```
**find():** Returns the value of the first element in an array that satisfies a provided function.
```
const arr = [1, 2, 3, 4, 5];
const isGreaterThanThree = (element) => element > 3;
console.log(arr.find(isGreaterThanThree)); // Output: 4
```
**forEach():** Executes a provided function once for each array element.
```
const arr = [1, 2, 3, 4, 5];
arr.forEach((element) => console.log(element)); // Output: 1, 2, 3, 4, 5
```
**includes():** Determines whether an array includes a certain value among its entries.
```
const arr = [1, 2, 3, 4, 5];
console.log(arr.includes(3)); // Output: true
console.log(arr.includes(6)); // Output: false
```
**indexOf():** Returns the first index at which a given element can be found in the array.
```
const arr = [1, 2, 3, 4, 5];
console.log(arr.indexOf(3)); // Output: 2
```
**join():** Joins all elements of an array into a string.
```
const arr = [1, 2, 3, 4, 5];
console.log(arr.join("-")); // Output: "1-2-3-4-5"
```
**pop():** Removes the last element from an array and returns that element.
```
const arr = [1, 2, 3, 4, 5];
console.log(arr.pop()); // Output: 5

console.log(arr); // Output: [1, 2, 3, 4]
```
**push():** Adds one or more elements to the end of an array and returns the new length of the array.
```
const arr = [1, 2, 3, 4, 5];
console.log(arr.push(6)); // Output: 6 (the new length of the array)
console.log(arr); // Output: [1, 2, 3, 4, 5, 6]
```
### Map
The map() method is used for creating a new array from an existing one, applying function to each one of the elements of the first array.

map(): creates a new array with the results of calling a provided function on every element in the array.

In the following example, each number in an array is doubled.
```
const arr = [1, 2, 3, 4, 5];
function double(x) {
    return x * 2;
}

const newArr = arr.map(double);
console.log(newArr); // Output: [2, 4, 6, 8, 10]
```

OR
```
const arr = [1, 2, 3, 4, 5];

const double = (element) => element * 2;
const newArr = arr.map(double);
console.log(newArr); // Output: [2, 4, 6, 8, 10]
```
### Filter
The filter() method takes each element in an array and it applies a conditional statement against it. If this conditional returns true, the element gets pushed to the output array. If the condition returns false, the element does not get pushed to the output array.

filter(): creates a new array with all elements that pass the test implemented by the provided function.
```
const arr = [1, 2, 3, 4, 5];
function isEven(element){
    return element % 2 === 0;
}

const filteredArr = arr.filter(isEven);
console.log(filteredArr); // Output: [2, 4]
```

OR

```
const arr = [1, 2, 3, 4, 5];
const isEven = (element) => element % 2 === 0;
const filteredArr = arr.filter(isEven);
console.log(filteredArr); // Output: [2, 4]
```

### Reduce
The reduce() method reduces an array of values down to just one value. To get the output value, it runs a reducer function on each element of the array.

Syntax
```
arr.reduce(callback[, initialValue])
```

```
const numbers = [1, 2, 3, 4];

function reducer(result, item) {
    return result + item;
}

const sum = numbers.reduce(reducer, 0);
console.log(sum); // 10
```

OR

```
const numbers = [1, 2, 3, 4];

const sum = numbers.reduce(function (result, item) {
   return result + item;
}, 0);

console.log(sum); // 10
```

- return of the function is use as the initial value on the next function call.
- if initial value is not present then it takes first argument as initial value
- but if initial value is present then it will take as first return value

**🔑 Note:** 

Map and filter both return an array.

Reduce return a single value.

# **Objects**
A JavaScript object is an entity having state and behaviour (properties and method).

Creating Objects in JavaScript

There are 3 ways to create objects.

- By object literal
- By creating instance of Object directly (using new keyword)
- By using an object constructor (using new keyword)

### 1) JavaScript Object by object literal
The syntax of creating object using object literal is given below:
```
object={property1:value1,property2:value2.....propertyN:valueN}  
```
As you can see, property and value is separated by : (colon).

Let’s see the simple example of creating object in JavaScript.
```
emp={id:102,name:"Naqeeb",salary:40}  
```
### 2) By creating instance of Object
The syntax of creating object directly is given below:
```
var objectname=new Object();  
```
Here, **new keyword** is used to create object.
```
var emp=new Object();  
emp.id=101;  
emp.name="Naqeeb ";  
emp.salary=50;  
```
### 3) By using an Object constructor / Template Function / Constructor Function
Here, you need to create function with arguments. Each argument value can be assigned in the current object by using this keyword.

The this keyword refers to the current object.
```
function emp(id,name,salary){  
this.id=id;  
this.name=name;  
this.salary=salary;  
}  
e=new emp(103,"Naqeeb ",30);
```


### Accessing properties
To access a property of an object, you use one of two notations: the dot notation and array-like notation.

**1) The dot notation (.)**

The following illustrates how to use the dot notation to access a property of an object:
```
objectName.propertyName

let person = {

    firstName: 'Muhammad',
    lastName: 'Naqeeb'
};
console.log(person.firstName);
console.log(person.lastName);
```

**2) Array-like notation ([])**
```
objectName['propertyName']
For example:
let person = {
    firstName: 'Muhammad',
    lastName: 'Naqeeb'
};
console.log(person['firstName']);
console.log(person['lastName']);
```

### Modifying the value of a property
To change the value of a property, you use the assignment operator (=). For example:
```
let person = {
    firstName: 'Muhammad',
    lastName: 'Naqeeb'
};
person.firstName = 'Ali';
console.log(person);
```
### Adding a new property to an object
The following statement adds the age property to the person object and assigns 25 to it:
```
person.age = 25;
```

### Deleting a property of an object
To delete a property of an object, you use the delete operator:
```
delete objectName.propertyName;
```
The following example removes the age property from the person object:
```
delete person.age;
```
If you attempt to reaccess the age property, you’ll get an undefined value.

### Checking if a property exists
To check if a property exists in an object, you use the in operator:
```
propertyName in objectName
```
The **in** operator returns **true** if the **propertyName** exists in the **objectName**.


```
let employee = {
    firstName: 'Muhammad',
    employeeId: 1
};
console.log('employeeId' in employee);
```

# **Comparing two objects.**
Objects are reference types so you can’t just use === or == to compare 2 objects.

non-primitive data types are compared by reference.
```
let a = { name: 'Ali', age: 26 };
let b = { name: 'Ali', age: 26 };
console.log(a === b) // false
a = b
console.log(a === b) // True
```
### Compare Objects Using The JSON.stringify()
One way you can compare two objects by value is by using the JSON.stringify function.

The JSON.stringify() function converts objects into equivalent JSON strings. You can then use any of the comparison operators to compare the strings.
```
let a = { name: 'Ali', age: 26 };
let b = { name: 'Ali', age: 26 };
console.log(a === b) // false
console.log(JSON.stringify(a) === JSON.stringify(b)); // true
```

But JSON.stringify() isn't always the best solution for comparing objects by value since it has limitations.

First of all, when using JSON.stringify(), the order of the keys matters.
```
let a = { age: 29, name: 'Dionysia'};
let b = { name: 'Dionysia', age: 29};
console.log(JSON.stringify(a) === JSON.stringify(b)); //false
```

JSON.stringify() stringifies the object as it is, so the order of the keys is important. If they are not in the same order, the result will be false.

### Compare Objects Using the Lodash \_.isEqual() Method
An elegant and sophisticated solution for comparing objects by their value is to use the well-tested JavaScript library Lodash and its \_.isEqual() method.

Let's take the example from the previous section, where the keys have the same value but are in a different order, and use the \_.isEqual() method:
```
let a = { age: 29, name: 'Dionysia'};
let b = { name: 'Dionysia', age: 29};
console.log(\_.isEqual(a, b)); // true
```

# **Arrow function**
Arrow functions allow us to write shorter function syntax:
```
let myFunction = (a, b) => a \* b;
```
**Arrow Functions Return Value by Default:**

It gets shorter! If the function has only one statement, and the statement returns a value, you can remove the brackets and the return keyword:
```
hello = () => "Hello World!";
```
If you have parameters, you pass them inside the parentheses:

**Arrow Function With Parameters:**
```
hello = (val) => "Hello " + val;
```
In fact, if you have only one parameter, you can skip the parentheses as well:

**Arrow Function Without Parentheses:**
```
hello = val => "Hello " + val;
```
**Arrow Function returning object.**
```
let fun = ()=> {text: "test"}
console.log(fun()) // undefined
```

This is an exceptional case: you have to use bracket and return statement when you have to return an object otherwise it will confused about bracket, it will consider object {} as function bracket.

**Arrow function as argument**
```
let arr = [1,2,3,4,5]
let newArr = arr.map((x)=> x\*\*2 )
console.log(newArr) // [1, 4, 9, 16, 25]
```

# **REST Operator**
The REST operator in JavaScript is denoted by three dots (...). It is used to represent an indefinite number of arguments as an array.

The rest parameter syntax allows a function to accept an indefinite number of arguments as an array,
```
function myFunction(...args) {
    // function body
}
```
In the above example, the args parameter uses the REST operator to capture an indefinite number of arguments passed to the function.

**Example**
```
function sum(...args) {
    return args.reduce((total, current) => total + current);
}
console.log(sum(1, 2, 3)); // 6
console.log(sum(1, 2, 3, 4, 5)); //15
```

# **Spread Operator**
The spread operator in JavaScript is a syntax that allows an iterable (e.g. an array, string, or object) to be expanded into individual elements.

The JavaScript spread operator (...) allows us to quickly copy all or part of an existing array or object into another array or object.

The spread operator can be a useful tool for manipulating and combining arrays, strings, and objects in JavaScript.

**Example1:**
```
let arr = ['a','b','c','d'];
console.log(arr) // ['a', 'b', 'c', 'd']
console.log(...arr) // a b c d
```

**Example 2:**
```
const numbersOne = [1, 2, 3];
const numbersTwo = [4, 5, 6];
const numbersCombined = [...numbersOne, ...numbersTwo];
console.log(numbersCombined) // [1, 2, 3, 4, 5, 6]
```

**Example 3:** Assign the first and second items from **numbers** to variables and put the rest in an **array**:
```
const numbers = [1, 2, 3, 4, 5, 6];
const [one, two, ...remaining] = numbers;
console.log(one) // 1
console.log(two) // 2
console.log(remaining) // [3, 4, 5, 6]
```

**Example4:** We can use the spread operator with objects too:
```
const myVehicle = {
    brand: 'Ford',
    model: 'Mustang',
    color: 'red'
}

const updateMyVehicle = {
    type: 'car',
    year: 2021, 
    color: 'yellow'
}

const myUpdatedVehicle = {...myVehicle, ...updateMyVehicle}
console.log(myUpdatedVehicle)

Output: {brand: 'Ford', model: 'Mustang', color: 'yellow', type: 'car', year: 2021}
```


**Example 5:** Copying array

```
let array1 = ['h', 'e', 'y'];
// Copying array1 to array2 
let array2 = [...array1];
// Printing array2
console.log(array2); // ['h', 'e', 'y']
array2.push("9")
console.log(array1); // ['h', 'e', 'y']
console.log(array2); // ['h', 'e', 'y', '9']
```

**Example6:** Array to arguments

Instead of having to pass each element like numbers[0], numbers[1] and so on, the spread operators allows array elements to be passed in as individual arguments.
```
function multiply(number1, number2, number3) {
    console.log(number1 * number2 * number3);
}

let numbers = [1, 2, 3];
// Calling multiply function and passing arguments 
// using spread operator
multiply(...numbers);
Output: 6
```
**Example 7:** Make new array with combination on previous array and some new values
```
const number = [1,2,3,4]
const newNumber = [...number, 10,11]
console.log(newNumber) // [1, 2, 3, 4, 10, 11]
```

### 🔑 Note:
(…) in function => rest

(…) in array or with array => Spread


# Destructuring

Destructuring is a feature in JavaScript that allows you to extract values from arrays, objects, and nested structures into individual variables.

There are two types of destructuring in JavaScript: array destructuring and object destructuring.

**Before:**
```
const vehicles = ['mustang', 'f-150', 'expedition'];
// old way
const car = vehicles[0];
const truck = vehicles[1];
const suv = vehicles[2];
```
**With destructuring:**
```
const vehicles = ['mustang', 'f-150', 'expedition'];
const [car, truck, suv] = vehicles;
console.log(car) // mustang
console.log(truck) // f-150
console.log(suv) // expedition
```

### With Arrays
**Case 1**
```
let number = [1,2,3,4]
let [a,b,c,d, e] = number;
console.log(a,b,c,d, e) // 1 2 3 4 undefined
```
**Case 2:** Assigning Default Values
```
let number = [1,2,3,4]
let [a=10, b=20, c=30, d=40, e=50] = number;
console.log(a,b,c,d,e) // 1 2 3 4 50
```
Default value is applied only if there is no value present in the array for that variable.

**Case 3:** If you only want a perticular value
```
let number = [1,2,3,4]
let [, , , d=40] = number;
console.log(d)
```

### With Object
Object destructuring in JavaScript is a way to extract properties from an object into separate variables.

**Case 1:** existing variable names
```
var person = {s_name: "Naqeeb", age: 22, gender: "M"}
var {s_name, age, gender} = person;
console.log(s_name, age, gender) // Naqeeb 22 M
```

These name must be same otherwise it will return undefined i.e.
```
var person = {name: "Naqeeb", age: 22, gender: "M"}
var {s_name, age, gender} = person;
console.log(s_name, age, gender) // undefined 22 M
```

**Case 2:** shuffling
```
var person = {s_name: "Naqeeb", age: 22, gender: "M"}
var {age, gender, s_name} = person;
console.log(s_name, age, gender) // Naqeeb 22 M
```
shuffling of the variable does not matter in object because  it matches the key

**Case 3:** Nested Object
```
const person = { name: 'John', age: 30, address: { city: 'New York', state: 'NY' } };
const { name, age, address: { city } } = person;
console.log(name); // 'John'
console.log(age); // 30
console.log(city); // 'New York'

```
In this example, we're creating an object called **person** with three properties: **name**, **age**, and **address**. The address property is itself an object with two properties: **city** and state. We're using object destructuring to extract the name, age, and city properties into separate variables.

**Case4:** assign new variable names
```
var employee = {    
    firstname: 'Muhammad',
    lastname: 'Naqeeb',
    dateofbirth: '2000'
};

var { firstname: fn, lastname: ln, dateofbirth: dob } = employee;
console.log( fn, ln,",", dob);
```
Output: Muhammad Naqeeb , 2000

# **Higher order Functions**
In JavaScript, 

- functions can be assigned to variables in the same way that strings or arrays can. 
- They can be passed into other functions as parameters 
- or returned from them as well.

A “higher-order function” is a function that accepts functions as parameters and/or returns a function.

### 1. Assign functions to variables
```
const hiFunction = function() {
   return 'Hello!' 
};

console.log(**hiFunction**()); // Hello!
```

### 2. Use functions as arguments to other functions
```
function iUseFunction(func) {
     func();
}
iUseFunction(function () { return console.log("Value is: ", 42) }); 
```
Output: Value is:  42

### 3. And even return functions from functions
```
function iReturnFunction() {
    return function () { return 42 };
}

// returned function will be assigned to myFunc and then we can call it later
const myFunc = iReturnFunction();
console.log(myFunc()); // 42
```
“****The functions that use other functions as arguments or return functions are named higher-order functions.***”

Language which support higher order function is known as Higher Order Languages.JS is a **Higher order Language.**

# For of loop

The JavaScript for of statement loops through the values of an iterable object.

It lets you loop over iterable data structures such as Arrays, Strings, Maps, NodeLists, and more:

This loop cannot work with objects
### With array
```
// for of loop
let nameArray = ["Ali", "Bilal", "Akmal"]
for (let element of nameArray) {
    console.log(element)
}

Output:
Ali 
Bilal 
Akmal
```
### With String
```
// for of loop
let name= "Bilal"
for (let element of name) {
    console.log(element)
}

Output
B 
i 
l 
a 
l
```
### Element with index
```
let nameArray = ["Ali", "Bilal", "Akmal"]
for(let [index, element] of nameArray.entries()){
    console.log("element: ",element, "index: ",index)
}
Output
element: Ali index: 0 
element: Bilal index: 1 
element: Akmal index: 2
```
# **For in loop**
- The for in loop iterates over a object
- Each iteration returns a key (x)
- The key is used to access the value of the key
- The value of the key is Object[x]

### With Object
```
let nameArray = {"A":"Ali", "B":"Bilal", "C":"Akmal"}
for(let key in nameArray){
    console.log(key)
}

Output
A 
B 
C
```

### With Array
```
let nameArray = ["Ali", "Bilal", "Akmal"]
for(let index in nameArray){
    console.log(index)
}

output
0 
1 
2
```
Do not use for in over an Array if the index order is important.

# **Looping through objects**
If you have an array that is considered to be an object in javascript, you can’t loop through the array using map(), forEach(), or a for..of loop.
### You will get errors:
```
const items = {
    'first': new Date(),
    'second': 2,
    'third': 'test'
}
```

map() will give you TypeError: items.map is not a function:
```
items.map(item => {})
```
forEach() will give you TypeError: items.forEach is not a function:
```
items.forEach(item => {})
```
for..of will give you TypeError: items are not iterable:

for (const item of items) {}
### Solution
Use for...in Loop 
# **Classes**

A JavaScript class is not an object.

It is a template for JavaScript objects.
```
class Car {

    constructor(name, year) {
        this.name = name;
        this.year = year;
    }
    // method in class
    age() {
        const date = new Date();
        return date.getFullYear() - this.year;
    }

    // Getter
    get getName() {
        return this.name;
    }

    // Setter
    set setName(newName) {
        this.name = newName;
    }
}

const myCar1 = new Car("Audi", 2022)
const myCar2 = new Car("V8", 2020)
console.log(myCar1.name) // Audi
console.log(myCar1.year) // 2022
console.log(myCar1.age()) // 1

// you have to call getter function without ()
console.log(myCar1.getName) // Audi

// you have to call setter like this
myCar1.setName = "NewAudi"
console.log(myCar1.name) // NewAudi
```
## Private variable
```
class Circle {
    #radius;
    constructor(value) {
        this.#radius = value;
    }

    get area() {
        return Math.PI \* Math.pow(this.#radius, 2);
        // you can directly return it
        // return this.#radius;
    }

    set setRadius(newRadius)
        this.#radius = newRadius;
    }
}

const c = new Circle(20);
console.log(c.area) // 1256.6370614359173
c.setRadius = 30;
console.log(c.area) // 2827.4333882308138
```
## Class as Expression
```
let CircleClass = class {
    #radius;
    constructor(value) {
        this.#radius = value;
    }

    get area() {
        return Math.PI * Math.pow(this.#radius, 2);
        // you can directly return it
        // return this.#radius;
    }

    set setRadius(newRadius) {
        this.#radius = newRadius;
    }
}

const c1 = new CircleClass(10)
console.log(c1.area) // 314.1592653589793
```


|**Class Expressions**|**Class Declarations**|
| :- | :- |
|In "Class Expressions", the class object NamedFoo is being assigned to a variable named Foo, like so:|In "Class Declarations", the class object NamedFoo is being declared solely by itself, like so:|
|var Foo = class NamedFoo {}|class NamedFoo {}|

# **JavaScript Template Literals**

Synonyms:

- Template Literals
- Template Strings
- String Templates
- Back-Tics Syntax

## Back-Tics Syntax
Template Literals use back-ticks (``) rather than the quotes ("") to define a string:

```
let text = `Hello World!`;
```
## Quotes Inside Strings
With template literals, you can use both single and double quotes inside a string:
```
let text = `He's often called "Ali"`;**
```

## Multiline Strings
Template literals allows multiline strings: (back-tics)
```
let text =

`The quick

brown fox

jumps over

the lazy dog`;
```
If you use “” it will ive error

## Interpolation
Template literals provide an easy way to interpolate variables and expressions into strings.

The method is called string interpolation.

${...}

## Variable Substitutions
Template literals allow variables in strings:
```
let firstName = "Ali";

let lastName = "Ahmed";

let text = `Welcome ${firstName}, ${lastName}!`;
```
Automatic replacing of variables with real values is called string interpolation.
## Expression Substitution
Template literals allow expressions in strings:
```
let price = 10;
let VAT = 0.25;
let total = `Total: ${(price * (1 + VAT)).toFixed(2)}`;
console.log(total) // Total: 12.50

```
# **“This” Keyword in JS**
In JavaScript, the this keyword refers to an object.

Which object depends on how this is being invoked (used or called).

The this keyword refers to different objects depending on how it is used:


|In an object method, this refers to the object.|
| :- |
|Alone, this refers to the **global object**.|
|In a function, this refers to the **global object**.|
|In a function, in strict mode, this is undefined.|
|In an event, this refers to the element that received the event.|
|Methods like call(), apply(), and bind() can refer this to any object.|

**this** is not a variable. It is a keyword. You cannot change the value of this.
## this Alone
- When used alone, this refers to the global object.
- Because this is running in the global scope.
- In a browser window the global object is [object Window]:

## this in a Function (Default)
In a function, the global object is the default binding for this.

In a browser window the global object is [object Window]:
```
function myFunction() {
  return this;
}
```
## this with arrow function function
Example
```
let ab = {
    a:1,
    b:2,
    display: ()=>{
        console.log(this.a) // undefined
    }
}

ab.display()
```

In case of arrow function this will use Lexical scope

## this in simple function
```
let ab = {
    a:1,
    b:2,
    display: function (){
        console.log(this.a) // 1
    }
}

ab.display()

```
## this with anonymous function function
When we use anonymous function this reference will be lost and it will return undefined

# **Prototyping**
In JavaScript, every function and object has a property named prototype by default.

In JavaScript, a prototype can be used to add properties and methods to a constructor function. And objects inherit properties and methods from a prototype.
```
// constructor function
function Person (name, age) {
    this.name = name,
    this.age = age
}

// creating objects
const person1 = new Person("Naqeeb",22);
const person2 = new Person("Ali",21);
// adding property to constructor function

Person.prototype.gender = 'male';

// prototype value of Person

console.log(Person.prototype); // {gender: 'male', constructor: ƒ}

// inheriting the property from prototype

console.log(person1.gender); // male

console.log(person2.gender); // male

// adding a method to the constructor function

Person.prototype.greet = function() {

    console.log('hello' + ' ' +  this.name);
}

person1.greet(); // hello Naqeeb

person2.greet(); // hello Ali
```
# **Implement JavaScript function-based classes**
```
// Define the class using a function

function Person(name, age) {

    // Define properties
    this.name = name;
    this.age = age;
  }

  // Define methods on the prototype
  Person.prototype.sayHello = function() {
    console.log("Hello, my name is " + this.name);
  }

  // Create a new instance of the class
  var john = new Person("Ali", 30);


  // Call a method on the instance
  john.sayHello(); // Output: "Hello, my name is Ali"
```

# **Inheritance in Function based classes**
In JavaScript, inheritance in function-based classes can be achieved using prototypes. 

**Define the superclass using a function**
```
function Person(name, age) {
    this.name = name;
    this.age = age;
  }
```
**Define a method on the superclass's prototype**
```
  Person.prototype.sayHello = function() {
    console.log("Hello, my name is " + this.name);
  }
```
**Define the subclass using a function**
```
function Employee(name, age, salary) {

    // Call the superclass constructor with the subclass's context
    Person.call(this, name, age);

    // Define a new property
    this.salary = salary;
  }

```
**Inherit from the superclass's prototype**
```
Employee.prototype = Object.create(Person.prototype);
```
**Define a method on the subclass's prototype**
```
Employee.prototype.doWork = function() {
    console.log(this.name + " is working");
}
```
**Create a new instance of the subclass**
```
var Ali = new Employee("Ali", 30, 50000);
```
**Call methods on the instance**
```
Ali.sayHello(); // Output: "Hello, my name is John"
Ali.doWork(); // Output: "Ali is working"  
```
