```diff
- text in red
+ text in green
! text in orange
# text in gray
```
# memo-javascript

## Introduction

### Console

In JavaScript, the console keyword refers to an object, a collection of data and actions.
One action, or method, that is built into the console object is the .log() method. 
> console.log(5); 

### Comments
#### A single line comment 
> // Prints 5 to the console
> console.log(5);

#### A multi-line comment 
> /*
> This is all commented, none of this is going to run!
> console.log(99);
> */

### Data Types

There are 7 fundamental data types in JavaScript:

* number
* string
* boolean
* null (null is where the thing is known to exist, but it's not known what the value is)
* undefined (undefined is where no notion of the thing exists; it has no type, and it's never been referenced before in that scope)
* symbol (A newer feature to the language, symbols are unique identifiers, useful in more complex coding)
* object

The first 6 of those types are considered **primitive data** types.

### Arithmetic Operators
* Add: +
* Subtract: -
* Multiply: *
* Divide: /
* Remainder: %

### String Concatenation

> console.log('front ' + 'space'); 
> // Prints 'front space'
> console.log('back' + ' space'); 
> // Prints 'back space'
> console.log('no' + 'space'); 
> // Prints 'nospace'
> console.log('middle' + ' ' + 'space'); 
> // Prints 'middle space'

### Properties

When you introduce a new piece of data into a JavaScript program, the browser saves it as an instance of the data type. Every string instance has a property called length.

> console.log('Hello'.length); // Prints 5

### Methods

We call, or use, these methods by appending an instance with:

* a period (the dot operator) (We can access properties and methods by using the ., dot operator)
* the name of the method
* opening and closing parentheses

> console.log('hello'.toUpperCase()); // Prints 'HELLO'
> console.log('Hey'.startsWith('H')); // Prints true
> console.log('    Remove whitespace   '.trim());

### Built-in Objects

JavaScript has the built-in Math object or Number object. They are collections of methods and properties that JavaScript provides.

> console.log(Math.floor(Math.random() * 100)); // Prints a random whole number between 0 and 100
> console.log(Number.isInteger(2017));

## Variables

Var, let, const

* L’instruction let
* L’instruction const
* L’instruction var

https://medium.com/@vincent.bocquet/var-let-const-en-js-quelles-diff%C3%A9rences-b0f14caa2049
