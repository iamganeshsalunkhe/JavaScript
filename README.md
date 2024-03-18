# JavaScript
"Enter our JavaScript repository at your own risk - where 'this' is always a mystery, and debugging feels like trying to catch a unicorn with a fishing net."
t

### JavaScript is a high-level, often just-in-time compiled language that conforms to the ECMAScript standard. It has dynamic typing, prototype-based object-orientation, and first-class functions. It is multi-paradigm, supporting event-driven, functional, and imperative programming styles.

## Here are some important functionality of JavaScript
### 1. DataTypes
1. number for both floating-point and integer numbers,
2. bigint for integer numbers of arbitrary length,
3. string for strings,
4. boolean for logical values: true/false,
5. null – a type with a single value null, meaning “empty” or “does not exist”,
6. undefined – a type with a single value undefined, meaning “not assigned”,
7. object and symbol – for complex data structures and unique identifiers, we haven’t learnt them yet.
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

