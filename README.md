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

https://medium.com/@vincent.bocquet/var-let-const-en-js-quelles-diff%C3%A9rences-b0f14caa2049

* L’instruction let 
  * pas obligatoire de déclarer une variable avec sa valeur initiale
  * on peut modifier sa valeur après sa déclaration
  * Sa principale caractéristique est sa portée : elle est limité à celle du bloc courant (un bloc en Javascript, c’est ce qu’on retrouve entre accolades : une comparaison en if, une boucle while etc.), pour la rendre globale, il faut simplement la définir hors de toute fonction.
* L’instruction const 
  * portée bloc, pour la rendre globale, il faut simplement la définir hors de toute fonction.
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

## Functions

### Function Declarations

A function declaration consists of:

The function keyword.
The name of the function, or its **identifier**, followed by parentheses.
A function body, or the block of statements required to perform a specific task, enclosed in the function’s curly brackets, { }.

identifier is greetWorld in the following:

> function greetWorld() {
>   console.log('Hello, World!');
> }

**Calling a Function**

> greetWorld(); // Output: Hello, World!

Be aware of the **hoisting** feature in JavaScript which allows access to function declarations before they’re defined. Since hoisting isn’t considered good practice, we simply want you to be aware of this feature.

> greetWorld(); // Output: Hello, World!
 
> function greetWorld() {
>   console.log('Hello, World!');
> }

### Parameters and Arguments

When declaring a function, we can specify its parameters. Parameters allow functions to accept input(s) and perform a task using the input(s). 

> function calculateArea(width, height) {
>     console.log(width * height);
> }

width, height are parameters.

The values that are passed to the function when it is called are called arguments. Arguments can be passed to the function as values or variables.

> calculateArea(10, 6);

10, 6 are arguments as values.

or

> const rectWidth = 10;
> const rectHeight = 6;

> calculateArea(rectWidth, rectHeight);

rectWidth, rectHeight are arguments as variables.

### Default Parameters

> function greeting (name = 'stranger') {
>   console.log(`Hello, ${name}!`)
> }
 
> greeting('Nick') // Output: Hello, Nick!
> greeting() // Output: Hello, stranger!

### Return

> By default that resulting value is undefined.

> function rectangleArea(width, height) {
>   let area = width * height;
> }
> console.log(rectangleArea(5, 7)) // Prints undefined

When a return statement is used in a function body, the execution of the function is stopped and the code that follows it will not be executed.

> function rectangleArea(width, height) {
>   if (width < 0 || height < 0) {
>     return 'You need positive integers to calculate area!';
>   }
>   return width * height;
> }

### Helper Functions

We can use functions to section off small bits of logic or tasks, then use them when we need to. Writing helper functions can help take large and difficult tasks and break them into smaller and more manageable tasks.

> function multiplyByNineFifths(number) {
>   return number * (9/5);
> };
 
> function getFahrenheit(celsius) {
>   return multiplyByNineFifths(celsius) + 32;
> };
 
> getFahrenheit(15); // Returns 59

### Function Expressions

Another way to define a function is to use a function expression. To define a function inside an expression, we can use the function keyword. In a function expression, the function name is usually omitted. A function with no name is called an anonymous function. A function expression is often stored in a variable in order to refer to it.

> const calculateArea = function(width, height) {
>     const area = width * height;
>     return area;
> };

To call the function expression:
> variableName(argument1, argument2)

### Arrow Functions

A shorter way to write functions by using the special “fat arrow” () => notation.

> const rectangleArea = (width, height) => {
>   let area = width * height;
>   return area;
> };

#### Concise Body Arrow Functions

If we have a function:

> const squareNum = (num) => {
>   return num * num;
> };

We can refactor the function to:

> const squareNum = num => num * num;

So for one parameter:
> const functionName = paramOne => {};

For multiple parameters:
> const functionName = (paramOne, paraTwo) => {};

For zero parameter:
> const functionName = () => {};

https://www.codecademy.com/courses/introduction-to-javascript/lessons/functions/exercises/concise-body-arrow

## Scope

### Global Scope
In global scope, variables are declared outside of blocks, they are global variables.

### Block Scope
When a variable is defined inside a block, it is only accessible to the code within the curly braces {}. Variables that are declared with block scope are known as local variables. Blocks are statements that exist within curly braces {}.

### Scope Pollution

Scope pollution is when we have too many global variables that exist in the global namespace.
When you declare global variables, they go to the global namespace. The global namespace allows the variables to be accessible from anywhere in the program.
Global namespace is the space in our code that contains globally scoped information.

### Practice Good Scoping

We should follow best practices for scoping our variables as tightly as possible using block scope.
* It’s easier to maintain your code, since your code will be modular.
* It makes your code more understandable
* It will save memory in your code because it will cease to exist after the block finishes running.

En informatique, la programmation modulaire reprend l'idée de fabriquer un produit (le programme) à partir de composants (les modules). Ce style de programmation facilite grandement l'amélioration progressive, la ré-utilisabilité et le partage du code, et est particulièrement utile pour la réalisation de bibliothèques.



' caractère
" chaine de caractère
typage de variable
