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
  * pas obligatoire de déclarer une variable avec sa valeur initiale
  * on peut modifier sa valeur après sa déclaration
  * Sa principale caractéristique est sa portée : elle est limité à celle du bloc courant (un bloc en Javascript, c’est ce qu’on retrouve entre accolades : une comparaison en if, une boucle while etc.)
* L’instruction const 
  * doit être déclaré au début
  * ne peut pas être re-déclarer
* L’instruction var
  * Comme let, on peut aussi ne pas définir de valeur initiale, la variable aura donc une valeur undefined
  * La portée de la variable est celle du contexte dans lequel elle est déclarée (dans ou hors fonction)
  * La déclaration sans instruction var (exemple : maVar = ‘test’) revient à écrire var maVar = ‘test’ dans un contexte global. La variable devient donc une propriété de l’objet global (Objet window en javascript)
https://medium.com/@vincent.bocquet/var-let-const-en-js-quelles-diff%C3%A9rences-b0f14caa2049

## CONDITIONAL STATEMENTS

### If Statement
### If...Else Statements

> if (false) {
>  console.log('The code in this block will not run.');
>} else {
>  console.log('But the code in this block will!');
>}

### Comparison Operators
* Less than: <
* Greater than: >
* Less than or equal to: <=
* Greater than or equal to: >=
* Is equal to: ===
* Is not equal to: !==

### Logical Operators
* the and operator (&&)
* the or operator (||)
* the not operator, otherwise known as the bang operator (!)

### Truthy and Falsy
The list of falsy values includes:

* 0
* Empty strings like "" or ''
* null which represent when there is no value at all
* undefined which represent when a declared variable lacks a value
* NaN, or Not a Number

### Truthy and Falsy Assignment

> let defaultName;
> if (username) {
>  defaultName = username;
> } else {
>  defaultName = 'Stranger';
> }

We can use a **short-hand syntax** for the code above:

> let defaultName = username || 'Stranger';

Because || or statements check the left-hand condition first, the variable defaultName will be assigned the actual value of username if it is truthy, and it will be assigned the value of 'Stranger' if username is falsy. This concept is also referred to as **short-circuit evaluation**.

### Ternary Operator

> let favoritePhrase = 'Love That!';

> if (favoritePhrase === 'Love That!') {
>   console.log('I love that!');
> } else {
>   console.log("I don't love that!");
> }

transformé en :

> favoritePhrase === 'Love That!' ? console.log('I love that!') : console.log("I don't love that!");

### Else If Statements

> let stopLight = 'yellow';
 
> if (stopLight === 'red') {
>   console.log('Stop!');
> } else if (stopLight === 'yellow') {
>   console.log('Slow down.');
> } else {
>   console.log('Caution, unknown!');
> }

### The switch keyword

> let athleteFinalPosition = 'first place';

> switch (athleteFinalPosition) {
>   case 'first place' :
>   console.log('You get the gold medal!');
>   break;
>   case 'second place' :
>   console.log('You get the silver medal!');
>   break;
>   case 'third place' :
>   console.log('You get the bronze medal!');
>   break;
>   default:
>   console.log('No medal awarded.');
>   break;
> }

