# Core JavaScript (ES6+)

JavaScript is the backbone of React, and interviewers expect a solid understanding of its core concepts. Below is a concise overview of key topics to master.

## Variables & Scope

- **`var`**: Function-scoped, hoisted (accessible before declaration), can be redeclared.
- **`let`**: Block-scoped, not hoisted in the same way, can be reassigned but not redeclared.
- **`const`**: Block-scoped, cannot be reassigned after declaration.
- **Scope**: Defines where variables are accessible:
  - **Global**: Accessible everywhere.
  - **Function**: Limited to a function.
  - **Block**: Limited to a block (e.g., inside `{}`).

**Example**:
```javascript
if (true) {
  let x = 10; // Only accessible inside this block
}
console.log(x); // ReferenceError: x is not defined

```javascript

Data Types & Operators

Primitive Types:

string
number
boolean
null
undefined
symbol
bigint


Reference Types:

Objects, arrays, functions (stored by reference, not value).


Equality Operators:

Loose equality (==): Performs type coercion.
Strict equality (===): Checks both type and value.

Example:

0 == '0'  // true (type coercion)
0 === '0' // false (different types)

Functions

Arrow Functions: Concise syntax, lexically bind this to the parent scope.

const add = (a, b) => a + b;

Default Parameters:

function greet(name = 'Guest') {
  console.log(`Hello ${name}`);
}

Rest Parameters: Collect arguments into an array.

function sum(...nums) {
  return nums.reduce((a, b) => a + b, 0);
}

Spread Operator: Expands arrays or objects.

const arr = [1, 2, 3];
const arr2 = [...arr, 4]; // [1, 2, 3, 4]

Destructuring & Template Literals

Destructuring: Extract values from objects or arrays.

const person = { name: 'Alice', age: 25 };
const { name, age } = person;
const array = ['first', 'second'];
const [first, second] = array;

Template Literals: String interpolation with backticks.

const message = `Hi ${name}, you are ${age}`;

this and Closures

this: Determined by the call-site. Arrow functions inherit this from their parent scope.
Closure: A function that retains access to variables from its creation scope, even after the outer function finishes.

Example:

function counter() {
  let count = 0;
  return () => ++count;
}
const inc = counter();
console.log(inc()); // 1
console.log(inc()); // 2


Async JavaScript

Event Loop: JavaScript is single-threaded. Tasks are processed in:

Call Stack: Synchronous tasks.
Callback/Microtask Queue: Async tasks (e.g., promises, setTimeout).


Promises:
fetch('/data')
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));

  Async/Await: Syntactic sugar for promises, making async code look synchronous.
async function loadData() {
  try {
    const res = await fetch('/data');
    const data = await res.json();
    console.log(data);
  } catch (e) {
    console.error(e);
  }
}


DOM & Browser APIs

DOM Manipulation:

Select elements: document.querySelector()
Add listeners: element.addEventListener()


Event Bubbling/Capturing:

Bubbling: Events propagate from child to parent.
Capturing: Events propagate from parent to child.


Event Delegation: Attach a single event listener to a parent element to handle events for multiple children, improving performance.

Example:
document.querySelector('.parent').addEventListener('click', (e) => {
  if (e.target.classList.contains('child')) {
    console.log('Child clicked!');
  }
});