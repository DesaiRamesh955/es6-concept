# ES6 concept
---
## JavaScript Arrow Function

In this tutorial, you will learn about JavaScript arrow function with the help of examples.

Arrow function is one of the features introduced in the ES6 version of JavaScript. It allows you to create functions in a cleaner way compared to regular functions. For example,

This function
```js
// function expression
let x = function(x, y) {
   return x * y;
}
```
can be written as
```js
// using arrow functions
let x = (x, y) => x * y;
```
using an arrow function.

---
### Arrow Function Syntax

Here,
- myFunction is the name of the function
- arg1, arg2, ...argN are the function arguments
- statement(s) is the function body
- 
If the body has single statement or expression, you can write arrow function as:

```js
let myFunction = (arg1, arg2, ...argN) => expression
```

---

### Example 1: Arrow Function with No Argument

If a function doesn't take any argument, then you should use empty parentheses. For example,

```js
let greet = () => console.log('Hello');
greet(); // Hello
```

---

### Example 2: Arrow Function with One Argument

If a function has only one argument, you can omit the parentheses. For example,

```js
let greet = x => console.log(x);
greet('Hello'); // Hello 
```

---

### Example 3: Arrow Function as an Expression
You can also dynamically create a function and use it as an expression. For example,

```js
let age = 5;

let welcome = (age < 18) ?
  () => console.log('Baby') :
  () => console.log('Adult');

welcome(); // Baby
```

### Example 4: Multiline Arrow Functions
If a function body has multiple statements, you need to put them inside curly brackets ```{}```. For example,

```js
let sum = (a, b) => {
    let result = a + b;
    return result;
}

let result1 = sum(5,7);
console.log(result1); // 12
```

---

### this with Arrow Function

Inside a regular function, ==this keyword== refers to the function where it is called.

However, ```this``` is not associated with arrow functions. Arrow function does not have its own ```this```. So whenever you call ```this```, it refers to its parent scope. For example,

***Inside a regular function***

```js
function Person() {
    this.name = 'Jack',
    this.age = 25,
    this.sayName = function () {

        // this is accessible
        console.log(this.age);

        function innerFunc() {

            // this refers to the global object
            console.log(this.age);
            console.log(this);
        }

        innerFunc();

    }
}

let x = new Person();
x.sayName();
```

***Output***

```25
undefined
Window {}
```

Here, ```this.age``` inside ```this.sayName()``` is accessible because ```this.sayName()``` is the method of an object.

However, ```innerFunc()``` is a normal function and ```this.age``` is not accessible because ```this``` refers to the global object (Window object in the browser). Hence, ```this.age``` inside the ```innerFunc()``` function gives ```undefined```.

***Inside an arrow function***

```js
function Person() {
    this.name = 'Jack',
    this.age = 25,
    this.sayName = function () {

        console.log(this.age);
        let innerFunc = () => {
            console.log(this.age);
        }

        innerFunc();
    }
}

const x = new Person();
x.sayName();
```

***Output***

```
25
25
```

Here, the ```innerFunc()``` function is defined using the arrow function. And inside the arrow function, ```this``` refers to the parent's scope. Hence, ```this.age``` gives 25.

---

### Arguments Binding

Regular functions have arguments binding. That's why when you pass arguments to a regular function, you can access them using the ```arguments``` keyword. For example,

```js
let x = function () {
    console.log(arguments);
}
x(4,6,7); // Arguments [4, 6, 7]
```

Arrow functions do not have arguments binding.

When you try to access an argument using the arrow function, it will give an error. For example,

```js
let x = () => {
    console.log(arguments);
}

x(4,6,7); 
// ReferenceError: Can't find variable: arguments
```

To solve this issue, you can use the ```spread``` syntax. For example,

```js
let x = (...n) => {
    console.log(n);
}

x(4,6,7); // [4, 6, 7]
```

---

### Arrow Function with Promises and Callbacks

Arrow functions provide better syntax to write promises and callbacks. For example,

```js
// ES5
asyncFunction().then(function() {
    return asyncFunction1();
}).then(function() {
    return asyncFunction2();
}).then(function() {
    finish;
});
```

can be written as

```js
// ES6
asyncFunction()
.then(() => asyncFunction1())
.then(() => asyncFunction2())
.then(() => finish);
```

---

### Things You Should Avoid With Arrow Functions

1. You should not use arrow functions to create methods inside objects.

```js
let person = {
    name: 'Jack',
    age: 25,
    sayName: () => {

        // this refers to the global .....
        //
        console.log(this.age);
    }
}

person.sayName(); // undefined
```

2. You cannot use an arrow function as a constructor. For example,

```js
let Foo = () => {};
let foo = new Foo(); // TypeError: Foo is not a constructor
```






