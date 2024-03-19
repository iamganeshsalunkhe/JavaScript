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
###### Variables are dynamically typed.




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


The try...catch construct may have one more code clause:   # finally.

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
