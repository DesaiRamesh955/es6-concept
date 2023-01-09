# ES6 concept
---
## JavaScript Destructuring Assignment

The destructuring assignment introduced in ES6 makes it easy to assign array values and object properties to distinct variables. For example,

#### Before ES6:

```js
// assigning object attributes to variables
const person = {
    name: 'Sara',
    age: 25,
    gender: 'female'    
}

let name = person.name;
let age = person.age;
let gender = person.gender;

console.log(name); // Sara
console.log(age); // 25
console.log(gender); // female
```

#### From ES6:

```js
// assigning object attributes to variables
const person = {
    name: 'Sara',
    age: 25,
    gender: 'female'    
}

// destructuring assignment
let { name, age, gender } = person;

console.log(name); // Sara
console.log(age); // 25
console.log(gender); // female
```

```
Note: The order of the name does not matter in object destructuring.
```

For example, you could write the above program as:

```js
let { age, gender, name } = person;
console.log(name); // Sara
```

```
Note: When destructuring objects, you should use the same name for the variable as the corresponding object key.
```

For example,

```js
let {name1, age, gender} = person;
console.log(name1); // undefined
```

If you want to assign different variable names for the object key, you can use:

```js
const person = {
    name: 'Sara',
    age: 25,
    gender: 'female'    
}

// destructuring assignment
// using different variable names
let { name: name1, age: age1, gender:gender1 } = person;

console.log(name1); // Sara
console.log(age1); // 25
console.log(gender1); // female
```

---

### Array Destructuring

You can also perform array destructuring in a similar way. For example,

```js
const arrValue = ['one', 'two', 'three'];

// destructuring assignment in arrays
const [x, y, z] = arrValue;

console.log(x); // one
console.log(y); // two
console.log(z); // three
```

---

### Assign Default Values

You can assign the default values for variables while using destructuring. For example,

```js
let arrValue = [10];

// assigning default value 5 and 7
let [x = 5,  y = 7] = arrValue;

console.log(x); // 10
console.log(y); // 7
```

In the above program, ```arrValue``` has only one element. Hence,

- the ```x``` variable will be **10**
- the ```y``` variable takes the default value **7**

In object destructuring, you can pass default values in a similar way. For example,

```js
const person = {
    name: 'Jack',
}

// assign default value 26 to age if undefined
const { name, age = 26} = person;

console.log(name); // Jack
console.log(age); // 26
```

---

### Swapping Variables

In this example, two variables are swapped using the destructuring assignment syntax.

```js
// program to swap variables

let x = 4;
let y = 7;

// swapping variables
[x, y] = [y, x];

console.log(x); // 7
console.log(y); // 4
```

---

### Skip Items

You can skip unwanted items in an array without assigning them to local variables. For example,

```js
const arrValue = ['one', 'two', 'three'];

// destructuring assignment in arrays
const [x, , z] = arrValue;

console.log(x); // one
console.log(z); // three
```

In the above program, the second element is omitted by using the comma separator ```,``` .

---

### Assign Remaining Elements to a Single Variable

You can assign the remaining elements of an array to a variable using the spread syntax ```...``` . For example,

```js
const arrValue = ['one', 'two', 'three', 'four'];

// destructuring assignment in arrays
// assigning remaining elements to y
const [x, ...y] = arrValue;

console.log(x); // one
console.log(y); // ["two", "three", "four"]
```

Here, ```one``` is assigned to the ```x``` variable. And the rest of the array elements are assigned to ```y``` variable.

You can also assign the rest of the object properties to a single variable. For example,

```js
const person = {
    name: 'Sara',
    age: 25,
    gender: 'female'    
}

// destructuring assignment
// assigning remaining properties to rest
let { name, ...rest } = person;

console.log(name); // Sara
console.log(rest); // {age: 25, gender: "female"}
```


```
Note: The variable with the spread syntax cannot have a trailing comma ,. You should use this rest element (variable with spread syntax) as the last variable.
```

For example,
```js
const arrValue = ['one', 'two', 'three', 'four'];

// throws an error
const [ ...x, y] = arrValue;

console.log(x); // eror
```

---

### Nested Destructuring Assignment

You can perform nested destructuring for array elements. For example,

```js
// nested array elements
const arrValue = ['one', ['two', 'three']];

// nested destructuring assignment in arrays
const [x, [y, z]] = arrValue;

console.log(x); // one
console.log(y); // two
console.log(z); // three
```

Here, the variable ```y``` and ```z``` are assigned nested elements ```two``` and ```three``` .

In order to execute the nested destructuring assignment, you have to enclose the variables in an array structure (by enclosing inside ```[]```).

You can also perform nested destructuring for object properties. For example,

```js
const person = {
    name: 'Jack',
    age: 26,
    hobbies: {
        read: true,
        playGame: true
    }
}
// nested destructuring 
const {name, hobbies: {read, playGame}} = person;

console.log(name); // Jack
console.log(read); // true
console.log(playGame); // true
```

In order to execute the nested destructuring assignment for objects, you have to enclose the variables in an object structure (by enclosing inside ```{}```).

---







