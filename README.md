# HackYourFuture

HYF JavaScript 1 / Week 2 classwork

## Topics

• Simple Data Types Recap

• Arrays

• Objects

• Operators

### Simple Data Types Recap

JavaScript has following simple data types or also known as _primitive_ types.

- boolean

- null

- undefined

- number

- string

- symbol

MDN defines a [primitive type](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) as data type that has no methods or properties. This means that a string created like below doesn't have any methods or properties attached to it.

```JavaScript
const str1 = "Wait, what?";
const str2 = "If I don't have any properties how do I get length using str1.length?";
const str3 = "JavaScript is crazy. I want to go home and scream!!";
```

Let's take a deep breath and try to understand what is happening.

1. Apart from `null` and `undefined`, each primitive type(`string`, `number` and `boolean`) has a corresponding wrapper object. Find more info about it [here](https://developer.mozilla.org/nl/docs/Web/JavaScript/Reference/Global_Objects/String), [here](https://developer.mozilla.org/nl/docs/Web/JavaScript/Reference/Global_Objects/Number) and [here](https://developer.mozilla.org/nl/docs/Web/JavaScript/Reference/Global_Objects/Boolean). This means, I can also create a string in JavaScript like below:

    ```JavaScript
    const str1 = new String('Hello World');
    // and is equivalent to
    const str2 = 'Hello World';
    ```

2. JavaScript as a language is weakly typed. This means that whenever your code wants to perform an operation with invalid datatypes(such as find length of a primitive string), JavaScript will try to find a best match for this scenario. This mechanism is also called, as mentioned above, **coercion**.

This is why when we try to find length of a primitive string like below

```JavaScript
const str = 'Hello World';
console.log(str.length);
```

JavaScript will try to do a coercian between primitives and objects. In this case, the primitive string is coerced to the string object in order to access its length property. Type coercian can happens other way round as well. For example, in the below snippet, string objects are coerced to primitives to concatenate them.

```JavaScript
const str1 = new String('Hello ');
const str2 = new String('World');
const str3 = str1 + str2;

console.log(str3);
```

#### Important

All primitives are immutable, i.e., they cannot be altered. It is important not to confuse a primitive itself with a variable assigned a primitive value. The variable may be reassigned a new value, but the existing value can not be changed in the ways that objects, arrays, and functions can be altered. For example,

```JavaScript
let str = 'Hello World';
console.log(str); // Hello World
str.toUpperCase();
console.log(str); // Hello World

str = str.toUpperCase();
console.log(str); // HELLO WORLD
```

### Arrays
