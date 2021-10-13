```diff
- text in red
+ text in green
! text in orange
# text in gray
```
Markdown syntaxe GitHub vs syntaxe Pandoc plus avancé

En générale :
* ' pour un caractère
* " pour chaîne de caractères

# memo-javascript

## Introduction

### Console

In JavaScript, the console keyword refers to an object, a collection of data and actions.
One action, or method, that is built into the console object is the .log() method. 
```javascript
console.log(5); 
```

### Comments
#### A single line comment 
```javascript
// Prints 5 to the console
console.log(5);
```

#### A multi-line comment 
```javascript
/*
This is all commented, none of this is going to run!
console.log(99);
*/
```

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
```javascript
console.log('front ' + 'space'); 
// Prints 'front space'
console.log('back' + ' space'); 
// Prints 'back space'
console.log('no' + 'space'); 
// Prints 'nospace'
console.log('middle' + ' ' + 'space'); 
// Prints 'middle space'
```


### Properties

When you introduce a new piece of data into a JavaScript program, the browser saves it as an instance of the data type. Every string instance has a property called length.
```javascript
console.log('Hello'.length); // Prints 5
```

### Methods

We call, or use, these methods by appending an instance with:

* a period (the dot operator) (We can access properties and methods by using the ., dot operator)
* the name of the method
* opening and closing parentheses
```javascript
console.log('hello'.toUpperCase()); // Prints 'HELLO'
console.log('Hey'.startsWith('H')); // Prints true
> console.log('    Remove whitespace   '.trim());
```


### Built-in Objects

JavaScript has the built-in Math object or Number object. They are collections of methods and properties that JavaScript provides.
```javascript
console.log(Math.floor(Math.random() * 100)); // Prints a random whole number between 0 and 100
console.log(Number.isInteger(2017));
```

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

The main difference is scoping rules. Variables declared by var keyword are scoped to the immediate function body (hence the function scope) while let variables are scoped to the immediate enclosing block denoted by { } (hence the block scope).
```javascript
function run() {
  var foo = "Foo";
  let bar = "Bar";

  console.log(foo, bar); // Foo Bar

  {
    var moo = "Mooo"
    let baz = "Bazz";
    console.log(moo, baz); // Mooo Bazz
  }

  console.log(moo); // Mooo
  console.log(baz); // ReferenceError
}

run();
```

## CONDITIONAL STATEMENTS

### If Statement
### If...Else Statements
```javascript
if (false) {
 console.log('The code in this block will not run.');
} else {
 console.log('But the code in this block will!');
}
```

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

#### Logical Operators - advanced

ET binaire (&)
```javascript
const a = 5;        // 00000000000000000000000000000101
const b = 3;        // 00000000000000000000000000000011

console.log(a & b); // 00000000000000000000000000000001
// expected output: 1
```

Bitwise NOT (~)
```javascript
const a = 5;     // 00000000000000000000000000000101
const b = -3;    // 11111111111111111111111111111101

console.log(~a); // 11111111111111111111111111111010
// expected output: -6

console.log(~b); // 00000000000000000000000000000010
// expected output: 2
```

OU exclusif binaire (^)
```javascript
const a = 5;        // 00000000000000000000000000000101
const b = 3;        // 00000000000000000000000000000011

console.log(a ^ b); // 00000000000000000000000000000110
// expected output: 6
```


### Truthy and Falsy
The list of falsy values includes:

* 0
* Empty strings like "" or ''
* null which represent when there is no value at all
* undefined which represent when a declared variable lacks a value
* NaN, or Not a Number

### Truthy and Falsy Assignment
```javascript
let defaultName;
if (username) {
 defaultName = username;
} else {
 defaultName = 'Stranger';
}
```

We can use a **short-hand syntax** for the code above:
```javascript
let defaultName = username || 'Stranger';
```

Because || or statements check the left-hand condition first, the variable defaultName will be assigned the actual value of username if it is truthy, and it will be assigned the value of 'Stranger' if username is falsy. This concept is also referred to as **short-circuit evaluation**.

### Ternary Operator
```javascript
let favoritePhrase = 'Love That!';

if (favoritePhrase === 'Love That!') {
  console.log('I love that!');
} else {
  console.log("I don't love that!");
}
```

transformé en :
```javascript
favoritePhrase === 'Love That!' ? console.log('I love that!') : console.log("I don't love that!");
```

### Else If Statements
```javascript
let stopLight = 'yellow';
 
if (stopLight === 'red') {
  console.log('Stop!');
} else if (stopLight === 'yellow') {
  console.log('Slow down.');
} else {
  console.log('Caution, unknown!');
}
```

### The switch keyword
```javascript
let athleteFinalPosition = 'first place';

switch (athleteFinalPosition) {
  case 'first place' :
  console.log('You get the gold medal!');
  break;
  case 'second place' :
  console.log('You get the silver medal!');
  break;
  case 'third place' :
  console.log('You get the bronze medal!');
  break;
  default:
  console.log('No medal awarded.');
  break;
}
```

## Functions

### Function Declarations

A function declaration consists of:

The function keyword.
The name of the function, or its **identifier**, followed by parentheses.
A function body, or the block of statements required to perform a specific task, enclosed in the function’s curly brackets, { }.

identifier is greetWorld in the following:
```javascript
function greetWorld() {
  console.log('Hello, World!');
}
```

**Calling a Function**
```javascript
greetWorld(); // Output: Hello, World!
```

Be aware of the **hoisting** feature in JavaScript which allows access to function declarations before they’re defined. Since hoisting isn’t considered good practice, we simply want you to be aware of this feature.
```javascript
greetWorld(); // Output: Hello, World!
 
function greetWorld() {
  console.log('Hello, World!');
}
```

### Parameters and Arguments

When declaring a function, we can specify its parameters. Parameters allow functions to accept input(s) and perform a task using the input(s). 
```javascript
function calculateArea(width, height) {
    console.log(width * height);
}
```

width, height are parameters.

The values that are passed to the function when it is called are called arguments. Arguments can be passed to the function as values or variables.
```javascript
calculateArea(10, 6);

```

10, 6 are arguments as values.

or
```javascript
const rectWidth = 10;
const rectHeight = 6;

calculateArea(rectWidth, rectHeight);
```

rectWidth, rectHeight are arguments as variables.

### Default Parameters
```javascript
function greeting (name = 'stranger') {
  console.log(`Hello, ${name}!`)
}
 
greeting('Nick') // Output: Hello, Nick!
greeting() // Output: Hello, stranger!
```

### Return
```javascript
By default that resulting value is undefined.

function rectangleArea(width, height) {
  let area = width * height;
}
console.log(rectangleArea(5, 7)) // Prints undefined
```

When a return statement is used in a function body, the execution of the function is stopped and the code that follows it will not be executed.
```javascript
function rectangleArea(width, height) {
  if (width < 0 || height < 0) {
    return 'You need positive integers to calculate area!';
  }
  return width * height;
}
```

### Helper Functions

We can use functions to section off small bits of logic or tasks, then use them when we need to. Writing helper functions can help take large and difficult tasks and break them into smaller and more manageable tasks.
```javascript
function multiplyByNineFifths(number) {
  return number * (9/5);
};
 
function getFahrenheit(celsius) {
  return multiplyByNineFifths(celsius) + 32;
};
 
getFahrenheit(15); // Returns 59
```

### Function Expressions

Another way to define a function is to use a function expression. To define a function inside an expression, we can use the function keyword. In a function expression, the function name is usually omitted. A function with no name is called an anonymous function. A function expression is often stored in a variable in order to refer to it.
fonction anonyme https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions

```javascript
const calculateArea = function(width, height) {
    const area = width * height;
    return area;
};
```

To call the function expression:
```javascript
variableName(argument1, argument2)
```

### Arrow Functions

A shorter way to write functions by using the special “fat arrow” () => notation.
```javascript
const rectangleArea = (width, height) => {
  let area = width * height;
  return area;
};
```

#### Concise Body Arrow Functions

If we have a function:
```javascript
const squareNum = (num) => {
  return num * num;
};
```

We can refactor the function to:
```javascript
const squareNum = num => num * num;
```

So for one parameter:
```javascript
const functionName = paramOne => {};
```

For multiple parameters:
```javascript
const functionName = (paramOne, paraTwo) => {};
```

For zero parameter:
```javascript
const functionName = () => {};
```

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

## Array

Let’s take a closer look at the syntax in the array example:
```javascript
['Keep a journal', 10, true];
```

* The array is represented by the square brackets [] and the content inside.
* Each content item inside an array is called an element.
* There are three different elements inside the array.
* Each element inside the array is a different data type.

### Accessing Elements

Arrays in JavaScript are zero-indexed, meaning the positions start counting from 0 rather than 1.

You can also access individual characters in a string using bracket notation and the index:
```javascript
const hello = 'Hello World';
console.log(hello[6]);
// Output: W
```

### Update Elements
```javascript
let seasons = ['Winter', 'Spring', 'Summer', 'Fall'];
 
seasons[3] = 'Autumn';
console.log(seasons); 
//Output: ['Winter', 'Spring', 'Summer', 'Autumn']
```

### Arrays with let and const

Elements in an array declared with const remain mutable.
```javascript
let condiments = ['Ketchup', 'Mustard', 'Soy Sauce', 'Sriracha'];
console.log(condiments[0] = 'Mayo');
console.log(condiments = ['Mayo']);
```

### The .length property
```javascript
const newYearsResolutions = ['Keep a journal', 'Take a falconry class'];
 
console.log(newYearsResolutions.length);
// Output: 2
```
### The .push() Method
```javascript
const itemTracker = ['item 0', 'item 1', 'item 2'];
 
itemTracker.push('item 3', 'item 4');
 
console.log(itemTracker); 
// Output: ['item 0', 'item 1', 'item 2', 'item 3', 'item 4'];
```

### The .pop() Method
```javascript
const newItemTracker = ['item 0', 'item 1', 'item 2'];
 
const removed = newItemTracker.pop();
 
console.log(newItemTracker); 
// Output: [ 'item 0', 'item 1' ]
console.log(removed);
// Output: item 2
```

### More Array Methods

Some arrays methods that are available to JavaScript developers include: .join(), .slice(), .splice(), .shift(), .unshift(), and .concat()

*  the .shift() method to remove the first item from the array
*  .unshift() method to add 'popcorn' to the beginning of your array
*  .slice()
To take a portion from an array:
```javascript
const groceryList = ['orange juice', 'bananas', 'coffee beans', 'brown rice', 'pasta', 'coconut oil', 'plantains'];
console.log(groceryList.slice(1, 4));
// result [ 'bananas', 'coffee beans', 'brown rice' ]
```
*  .indexOf()
To find the index of an element:
```javascript
const groceryList = ['orange juice', 'bananas', 'coffee beans', 'brown rice', 'pasta', 'coconut oil', 'plantains'];
const pastaIndex = groceryList.indexOf('pasta');

console.log(pastaIndex);
```

### Arrays and Functions

What happens if we try to change an array inside a function? Does the array keep the change after the function call or is it scoped to inside the function? Yes:
```javascript
const flowers = ['peony', 'daffodil', 'marigold'];
 
function addFlower(arr) {
  arr.push('lily');
}
 
addFlower(flowers);
 
console.log(flowers); // Output: ['peony', 'daffodil', 'marigold', 'lily']
```

### Nested Arrays
```javascript
const nestedArr = [[1], [2, 3]];
 
console.log(nestedArr[1]); // Output: [2, 3]
console.log(nestedArr[1][0]); // Output: 2
```

## Loop

### The For Loop

A for loop contains three expressions separated by ; inside the parentheses:

1. an *initialization* starts the loop and can also be used to declare the iterator variable.
2. a *stopping condition* is the condition that the iterator variable is evaluated against— if the condition evaluates to true the code block will run, and if it evaluates to false the code will stop.
3. an *iteration statement* is used to update the iterator variable on each loop.
```javascript
for (let counter = 0; counter < 4; counter++) {
  console.log(counter);
}
```

### Looping in Reverse
```javascript
// The loop below loops from 0 to 3. Edit it to loop backwards from 3 to 0
for (let counter = 3; counter >= 0; counter--){
  console.log(counter);
}
```

### Looping through Arrays
```javascript
const animals = ['Grizzly Bear', 'Sloth', 'Sea Lion'];
for (let i = 0; i < animals.length; i++){
  console.log(animals[i]);
}
```

### Nested Loops
```javascript
const bobsFollowers = ['John', 'Pierre', 'Charles', 'Chris'];
const tinasFollowers = ['Mary', 'Pierre', 'Charles'];
var mutualFollowers = [];

for (let i = 0; i < bobsFollowers.length; i++){
  for (let j = 0; j < tinasFollowers.length; j++){
    if (bobsFollowers[i] === tinasFollowers[j]) {
        mutualFollowers.push(tinasFollowers[j])
    } 
  }
};
```
### The While Loop

The syntax of a for loop is ideal when we know how many times the loop should run, but we don’t always know this in advance.

Be careful of infinite loop if there is no iteration statement.

```javascript
// A while loop that prints 1, 2, and 3
let counterTwo = 1;
while (counterTwo < 4) {
  console.log(counterTwo);
  counterTwo++;
}
```

### Do...While Statements

A do...while statement says to do a task once and then keep doing it until a specified condition is no longer met.

```javascript
const firstMessage = 'I will print!';
const secondMessage = 'I will not print!'; 

// A do while with a stopping condition that evaluates to false
do {
 console.log(firstMessage)
} while (true === false);
// print 'I will print!'
 
// A while loop with a stopping condition that evaluates to false
while (true === false){
  console.log(secondMessage)
};
// print nothing
```

### The break Keyword
```javascript
for (let i = 0; i < 99; i++) {
  if (i > 2 ) {
     break;
  }
  console.log('Banana.');
}
 
console.log('Orange you glad I broke out the loop!');
```
This is the output for the above code:
```javascript
Banana.
Banana.
Banana.
Orange you glad I broke out the loop!
```

### for of

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of

itère sur les valeurs

for in, itère sur les index

## Iterators

### Functions as Data

JavaScript functions behave like any other data type in the language; we can assign functions to variables, and we can reassign them to new variables.
If we wanted to rename this function without sacrificing the source code? We can re-assign the function to a variable with a suitably short name:
```javascript
const checkThatTwoPlusTwoEqualsFourAMillionTimes = () => {
  for(let i = 1; i <= 1000000; i++) {
    if ( (2 + 2) != 4) {
      console.log('Something has gone very wrong :( ');
    }
  }
}

// Write your code below

let is2p2 = checkThatTwoPlusTwoEqualsFourAMillionTimes;

is2p2();
```
Since functions are a type of object, they have properties such as .length and .name and methods such as .toString().
```javascript
console.log(is2p2.name);
```

### Functions as Parameters

A higher-order function is a function that either accepts functions as parameters, returns a function, or both!
We call the functions that get passed in as parameters and invoked callback functions because they get called during the execution of the higher-order function.

On parle de récursivité.

With callbacks, we pass in the function itself by typing the function name without the parentheses (that would evaluate to the result of calling the function):
```javascript
const timeFuncRuntime = funcParameter => {
   let t1 = Date.now();
   funcParameter();
   let t2 = Date.now();
   return t2 - t1;
}
 
const addOneToOne = () => 1 + 1;
 
timeFuncRuntime(addOneToOne);
```
In this example, we invoked timeFuncRuntime() with an anonymous function 
```javascript
timeFuncRuntime(() => {
  for (let i = 10; i>0; i--){
    console.log(i);
  }
});
```

## Objects

### Creating Object Literals

We use curly braces, {}, to designate an object literal:
```javascript
let spaceship = {}; // spaceship is an empty object
```
We fill an object with unordered data. This data is organized into *key-value* pairs.
Keys are strings, but when we have a key that does not have any special characters in it, JavaScript allows us to omit the quotation marks:
```javascript
// An object literal with two key-value pairs
let spaceship = {
  'Fuel Type': 'diesel',
  color: 'silver'
};
```

### Accessing Properties
```javascript
let spaceship = {
  homePlanet: 'Earth',
  color: 'silver'
};
spaceship.homePlanet; // Returns 'Earth',
spaceship.color; // Returns 'silver',
spaceship.favoriteIcecream; // Returns undefined
```

### Bracket Notation

We must use bracket notation when accessing keys that have numbers, spaces, or special characters in them. Without bracket notation in these situations, our code would throw an error.
```javascript
let spaceship = {
  'Fuel Type': 'Turbo Fuel',
  'Active Duty': true,
  homePlanet: 'Earth',
  numCrew: 5
};
spaceship['Active Duty'];   // Returns true
spaceship['Fuel Type'];   // Returns  'Turbo Fuel'
spaceship['numCrew'];   // Returns 5
spaceship['!!!!!!!!!!!!!!!'];   // Returns undefined
```
With bracket notation you can also use a variable inside the brackets to select the keys of an object. 
```javascript
let returnAnyProp = (objectName, propName) => objectName[propName];
 
returnAnyProp(spaceship, 'homePlanet'); // Returns 'Earth'
```

### Property Assignment

One of two things can happen with property assignment:

*  If the property already exists on the object, whatever value it held before will be replaced with the newly assigned value.
*  If there was no property with that name, a new property will be added to the object.
```javascript
const spaceship = {type: 'shuttle'};
spaceship = {type: 'alien'}; // TypeError: Assignment to constant variable.
spaceship.type = 'alien'; // Changes the value of the type property
spaceship.speed = 'Mach 5'; // Creates a new key of 'speed' with a value of 'Mach 5'
```

You can delete a property from an object with the delete operator.
```javascript
const spaceship = {
  'Fuel Type': 'Turbo Fuel',
  homePlanet: 'Earth',
  mission: 'Explore the universe' 
};
 
delete spaceship.mission;  // Removes the mission property
```

### Methods

Each key-value pair is a property—when a property is a function it is known as a method.

We can include methods in our object literals by creating ordinary, comma-separated key-value pairs. The key serves as our method’s name, while the value is an anonymous function expression.
```javascript
const alienShip = {
  invade: function () { 
    console.log('Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.')
  }
};
```
With the new method syntax introduced in ES6 we can omit the colon and the function keyword.
```javascript
const alienShip = {
  invade () { 
    console.log('Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.')
  }
};
```
Object methods are invoked by appending the object’s name with the dot operator followed by the method name and parentheses:
```javascript
alienShip.invade(); // Prints 'Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.'
```

### Nested Objects
```javascript
let spaceship = {
  passengers: null
};
```
Make one passenger object in the array that has at least one key-value pair on it:
```javascript
spaceship.passengers = [
  {
    firstName: 'John',
    lastName: 'Tree'
  }
];
console.log(spaceship.passengers); // [ { firstName: 'Tree', lastName: 'Tree' } ]
```
Create a variable firstPassenger and assign the first passenger as its value (the element in the 0th index of the spaceship.passengers array you just made):
```javascript
const firstPassenger = (spaceship.passengers[0]);
```

### Pass By Reference
https://www.codecademy.com/courses/introduction-to-javascript/lessons/objects/exercises/pass-by-reference

Objects are passed by reference. This means when we pass a variable assigned to an object into a function as an argument, the computer interprets the parameter name as pointing to the space in memory holding that object.
```javascript
const spaceship = {
  homePlanet : 'Earth',
  color : 'silver'
};
 
let paintIt = obj => {
  obj.color = 'glorious gold'
};
 
paintIt(spaceship);
 
spaceship.color // Returns 'glorious gold'
```

Our function paintIt() permanently changed the color of our spaceship object. However, reassignment of the spaceship variable wouldn’t work in the same way:

```javascript
let spaceship = {
  homePlanet : 'Earth',
  color : 'red'
};
let tryReassignment = obj => {
  obj = {
    identified : false, 
    'transport type' : 'flying'
  }
  console.log(obj) // Prints {'identified': false, 'transport type': 'flying'}
 
};
tryReassignment(spaceship) // The attempt at reassignment does not work.
spaceship // Still returns {homePlanet : 'Earth', color : 'red'};
 
spaceship = {
  identified : false, 
  'transport type': 'flying'
}; // Regular reassignment still works.
```

### Looping Through Objects

*for...in* will execute a given block of code for each property in an object.
```javascript
let spaceship = {
  crew: {
    captain: { 
      name: 'Lily', 
      degree: 'Computer Engineering', 
      cheerTeam() { console.log('You got this!') } 
    },
    'chief officer': { 
      name: 'Dan', 
      degree: 'Aerospace Engineering', 
      agree() { console.log('I agree, captain!') } 
    }
  }
}; 
 
// for...in
for (let crewMember in spaceship.crew) {
  console.log(`${crewMember}: ${spaceship.crew[crewMember].name}`);
}
or
for (let crewMember in spaceship.crew) {
  console.log(crewMember + ': ' + spaceship.crew[crewMember].name)
};

```
