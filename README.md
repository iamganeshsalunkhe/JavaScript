# JavaScript
"Enter our JavaScript repository at your own risk - where 'this' is always a mystery, and debugging feels like trying to catch a unicorn with a fishing net."
t

### JavaScript is a high-level, often just-in-time compiled language that conforms to the ECMAScript standard. It has dynamic typing, prototype-based object-orientation, and first-class functions. It is multi-paradigm, supporting event-driven, functional, and imperative programming styles.

## Here are some important functionality of JavaScript
### 1. DataTypes
1. number:  for both floating-point and integer numbers,
2. bigint for integer numbers of arbitrary:  length,
3. string:  for strings,
4. boolean: for logical values: true/false,
5. null: a type with a single value null, meaning “empty” or “does not exist”,
6. undefined :  a type with a single value undefined, meaning “not assigned”,
7. object and symbol : for complex data structures and unique identifiers.
 ### 2. Variables
Can be declared using:

#### 1) let
#### 2) const (constant, can’t be changed)
#### 3) var (old-style, will see later)
##### A variable name can include:

Letters and digits, but the first character may not be a digit.
Characters $ and _ are normal, on par with letters.
Non-Latin alphabets and hieroglyphs are also allowed, but commonly not used.
#####Variables are dynamically typed.




### 3. Functions
We can define a function in JS in three Types.
1) Function Declaration:

function showMessage() {
  alert( 'Hello everyone!');
};


2) Function Expression :

let sayHi = function() {
  alert( "Hello eveyone!");
};

3) Arrow Function(This is also a function expression)

let sayHi = () => alert("Hello everyone!)

#### Difference between Declaration and Expression
1) Functions are values. They can be assigned, copied or declared in any place of the code.
2) If the function is declared as a separate statement in the main code flow, that’s called a “Function Declaration”.
3) If the function is created as a part of an expression, it’s called a “Function Expression”.
4) Function Declarations are processed before the code block is executed. They are visible everywhere in the block.
5) Function Expressions are created when the execution flow reaches them.


### 4. Conditional Operator(?)
Sometimes, we need to assign a variable depending on a condition.

The so-called “conditional” or “question mark” operator lets us do that in a shorter and simpler way.

The operator is represented by a question mark ?. Sometimes it’s called “ternary”, because the operator has three operands. It is actually the one and only operator in JavaScript which has that many.
#### The synatx is :

let result = condition ? value1 : value2;

The condition is evaluated: if it’s truthy then value1 is returned, otherwise – value2.

### 5. Try , Catch and Finally  

No matter how great we are at programming, sometimes our scripts have errors. They may occur because of our mistakes, an unexpected user input, an erroneous server response, and for a thousand other reasons.

Usually, a script “dies” (immediately stops) in case of an error, printing it to console.

But there’s a syntax construct try...catch that allows us to “catch” errors so the script can, instead of dying, do something more reasonable.
try {

  // code...

} catch (err) {

  // error handling

}
It works like this:

First, the code in try {...} is executed.
If there were no errors, then catch (err) is ignored: the execution reaches the end of try and goes on, skipping catch.
If an error occurs, then the try execution is stopped, and control flows to the beginning of catch (err). The err variable (we can use any name for it) will contain an error object with details about what happened.

#### So, an error inside the try {...} block does not kill the script – we have a chance to handle it in catch.


The try...catch construct may have one more code clause: 
 ### finally.

#### If it exists, it runs in all cases:

after try, if there were no errors,
after catch, if there were errors.


The code has two ways of execution:

If you answer “Yes” to “Make an error?”, then try -> catch -> finally.
If you say “No”, then try -> finally.

##### The finally clause is often used when we start doing something and want to finalize it in any case of outcome.

### 6. Promise
A “producing code” that does something and takes time. For instance, some code that loads the data over a network.

A “consuming code” that wants the result of the “producing code” once it’s ready. Many functions may need that result.

##### A promise is a special JavaScript object that links the “producing code” and the “consuming code” together.

The function passed to new Promise is called the executor.


##### let promise = new Promise(function(resolve, reject){// executor (the producing code)});

When the executor obtains the result, be it soon or late, doesn’t matter, it should call one of these callbacks:

resolve(value) — if the job is finished successfully, with result value.
reject(error) — if an error has occurred, error is the error object.

##### So to summarize: the executor runs automatically and attempts to perform a job. When it is finished with the attempt, it calls resolve if it was successful or reject if there was an error.



##### The promise object returned by the new Promise constructor has these internal properties:

state — initially "pending", then changes to either "fulfilled" when resolve is called or "rejected" when reject is called.
result — initially undefined, then changes to value when resolve(value) is called or error when reject(error) is called.

### 7. Async/ Await

There’s a special syntax to work with promises in a more comfortable fashion, called “async/await”. It’s surprisingly easy to understand and use.

##### Async functions
Let’s start with the async keyword. It can be placed before a function, like this:

async function f() {
  return 1;
  }

The word “async” before a function means one simple thing: a function always returns a promise. Other values are wrapped in a resolved promise automatically.

So, async ensures that the function returns a promise, and wraps non-promises in it. Simple enough, right? But not only that. There’s another keyword, await, that works only inside async functions, and it’s pretty cool.


##### Await
The syntax:

// works only inside async functions
let value = await promise;

The keyword await makes JavaScript wait until that promise settles and returns its result.

Let’s emphasize: await literally suspends the function execution until the promise settles, and then resumes it with the promise result. That doesn’t cost any CPU resources, because the JavaScript engine can do other jobs in the meantime: execute other scripts, handle events, etc.

It’s just a more elegant syntax of getting the promise result than promise.then. And, it’s easier to read and write.

The async keyword before a function has two effects:

Makes it always return a promise.
Allows await to be used in it.
The await keyword before a promise makes JavaScript wait until that promise settles, and then:

If it’s an error, an exception is generated — same as if throw error were called at that very place.
Otherwise, it returns the result.
Together they provide a great framework to write asynchronous code that is easy to both read and write.

##### With async/await we rarely need to write promise.then/catch, but we still shouldn’t forget that they are based on promises, because sometimes (e.g. in the outermost scope) we have to use these methods. Also Promise.all is nice when we are waiting for many tasks simultaneously.


### 8.Modules
As our application grows bigger, we want to split it into multiple files, so called “modules”. A module may contain a class or a library of functions for a specific purpose.

For a long time, JavaScript existed without a language-level module syntax. That wasn’t a problem, because initially scripts were small and simple, so there was no need.

But eventually scripts became more and more complex, so the community invented a variety of ways to organize code into modules, special libraries to load modules on demand.


##### What is a module?
A module is just a file. One script is one module. As simple as that.

Modules can load each other and use special directives export and import to interchange functionality, call functions of one module from another one:

export keyword labels variables and functions that should be accessible from outside the current module.
import allows the import of functionality from other modules.


For instance, if we have a file sayHi.js exporting a function:

// 📁 sayHi.js
export function sayHi(user) {
  alert(`Hello, ${user}!`);
}

…Then another file may import and use it:

// 📁 main.js
import {sayHi} from './sayHi.js';

alert(sayHi); // function...
sayHi('John'); // Hello, John!

The import directive loads the module by path ./sayHi.js relative to the current file, and assigns exported function sayHi to the corresponding variable.

##### Always “use strict”.
Modules always work in strict mode. E.g. assigning to an undeclared variable will give an error.

##### Module-level scope

Each module has its own top-level scope. In other words, top-level variables and functions from a module are not seen in other scripts.

###### Modules should export what they want to be accessible from outside and import what they need.




##### In a module, top-level 'this' is undefined.

<img width="287" alt="module" src="https://github.com/iamganeshsalunkhe/JavaScript/assets/143490640/df7565e8-24cd-4d74-95af-c5080d833858">

