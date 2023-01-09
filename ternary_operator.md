# ES6 concept
---
## JavaScript Ternary Operator

A ternary operator can be used to replace an if..else statement in certain situations.

### What is a Ternary operator?

A ternary operator evaluates a condition and executes a block of code based on the condition.

Its syntax is:

```
condition ? expression1 : expression2
```
The ternary operator evaluates the test condition.

- If the condition is ```true```, **expression1** is executed.
- If the condition is ```false```, **expression2** is executed.

The ternary operator takes **three** operands, hence, the name ternary operator. It is also known as a conditional operator.

---

Let's write a program to determine if a student passed or failed in the exam based on marks obtained.

### Example: JavaScript Ternary Operator

```js
// program to check pass or fail

let marks = prompt('Enter your marks :');

// check the condition
let result = (marks >= 40) ? 'pass' : 'fail';

console.log(`You ${result} the exam.`);
```

**Output 1**

```
Enter your marks: 78
You pass the exam.
```

Suppose the user enters **78**. Then the condition ```marks >= 40``` is checked which evaluates to ```true```. So the first expression pass is assigned to the ```result``` variable.

---

### Ternary Operator Used Instead of if...else

In JavaScript, a ternary operator can be used to replace certain types of ```if..else``` statements. For example,

You can replace this code

```js
// check the age to determine the eligibility to vote
let age = 15;
let result;

if (age >= 18) {
      result = "You are eligible to vote.";
} else {
      result = "You are not eligible to vote yet.";
}

console.log(result);
```

with

```js
// ternary operator to check the eligibility to vote
let age = 15;
let result =
    (age >= 18) ? "You are eligible to vote." : "You are not eligible to vote yet";
console.log(result);
```

The output of both programs will be the same.

**Output**

```
You are not eligible to vote yet.
```

---

### Nested ternary operators

You can also nest one ternary operator as an expression inside another ternary operator. For example,

```js
// program to check if number is positive, negative or zero
let a = 3;
let result = (a >= 0) ? (a == 0 ? "zero" : "positive") : "negative";
console.log(`The number is ${result}.`);
```

**Output**

```
The number is positive.
```

```
Note: You should try to avoid nested ternary operators whenever possible as they make your code hard to read.
```











