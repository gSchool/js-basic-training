# A Crash Course in JavaScript Types

In most programming languages, JavaScript amongst them, programmers have at their disposal different kinds (or **types**) of values that they can utilize in their programs. These are also commonly called **data types**.

## Objectives   

By the end of this section you should be able to:

- Understand that values of different types can be used to do different kinds of operations
- Be able to identify values of the `number`, `string`, `boolean`, `undefined`, and `null` types
- Be able to perform basic operations on values of the `number`, `string`, `boolean`, `undefined` and `null` types

## Different Types of Things in the Real World

In the real world we have different types of things to build with, and each of these types have their own qualities, and rules for interacting with other types. Here are some real world examples meant to demonstrate how different types of things have their own qualities and rules for interacting with other types:

**Legos**

- The unit of a lego is a piece
- Pieces can connect to other pieces in some clearly specified ways, and be disconnected
  - It's pretty clear, even if pieces are connected, where one piece starts and another begins
- There are different sizes, shapes and colors of lego pieces

**Play-doh**

- The unit of a play-doh is a chunk
- You can form a single chunk of play-doh into all kinds of shapes
- You can break a single chunk of play-doh into many smaller chunks
- You can join more than one chunk into a single larger chunk
  - It may be impossible to get your original chunks back once you've joined chunks together
- You could embed lego pieces in play-doh chunks
- You can eat play-doh, but probably shouldn't

**Time**

- The unit of time is time
- Everything else happens in the context of time
- We can't do anything with time, it just passes of its own accord in a way totally outside our influence (maybe)

**Boxes**

- The unit of boxes is a box
- Boxes can be different sizes, shapes, colors, materials
- Boxes can be opened or closed
- You can stack boxes if they are certain sizes, and closed
- You can put legos or play-doh inside of boxes
- You can label boxes, accurately or inaccurately
- You can take things out of boxes, and put different things in them, with our without updating its label

## The 7 JavaScript Types

**In JavaScript, every value is one (and exactly one) of 7 possible types**:

- Number
- Boolean
- String
- Undefined
- Null
- Object
- Symbol

Let's deal briefly with each of them in turn.

## Number

**Values of the `number` type look and behave like numbers and can be positive, negative, whole, decimal, zero, or infinity.**

Here are some examples:

```javascript
console.log(1);                        // logs `1` to the console
console.log(42);                       // logs `42` to the console
console.log(0);                        // logs `0` to the console
console.log(-888);                     // logs `-888` to the console
console.log(3.14156);                  // logs `3.14156` to the console
console.log(Number.POSITIVE_INFINITY); // logs `Infinity` to the console
```

### Numerical Operators

JavaScript comes with a set of **operators** that act on values of the `number` type, resulting in the creation of a new value, also of the `number` type:

- `+` creates a new value of the `number` type that is the sum of two other values of the `number` type
- `-` creates a new value of the `number` type that is the difference of two other values of the `number` type
- `*` creates a new value of the `number` type that is the product of two other values of the `number` type
- `/` creates a new value of the `number` type that is the quotient of two other values of the `number` type
- `%` creates a new value of the `number` type that is the remainder of dividing two other values of the `number` type

Because using these operators creates a new value of the `number` type, we can pass in **expressions** using these operators, into `console.log` and see the result of the calculation in the developer console:

```javascript
console.log(80 + 2); // logs `82` to the console
console.log(11 - 3); // logs `8` to the console
console.log(10 * 8); // logs `80` to the console
console.log(25 / 4); // logs `6.25` to the console
console.log(16 % 3); // logs `1` to the console
```

## Boolean

**Values of the `boolean` type are one of two values: `true` or `false`.**

The two values of the `boolean` type (`true` and `false`) are often created by using the following comparison operators, which (in addition to others) compares values of both the `number` and `boolean` types:

### Comparison Operators

- `>` creates a new value of the `boolean` type depending on whether to value to the left of the operator is greater than that to the right
- `<` creates a new value of the `boolean` type depending on whether to value to the left of the operator is less than that to the right
- `>=` creates a new value of the `boolean` type depending on whether to value to the left of the operator is greater than or equal to that to the right
- `<=` creates a new value of the `boolean` type depending on whether to value to the left of the operator is less than or equal to that to the right
- `===` creates a new value of the `boolean` type depending on whether to value to the left of the operator is the same as that to the right
- `!==` creates a new value of the `boolean` type depending on whether to value to the left of the operator is not the same as that to the right

```javascript
console.log(1 > 2);          // logs `false` to the console
console.log(60 < 160);       // logs `true` to the console
console.log(42 <= 42);       // logs `true` to the console
console.log(9 === 9);        // logs `true` to the console
console.log(4 !== 40);       // logs `true` to the console
console.log(7 !== 7);        // logs `false` to the console
console.log(true === true);  // logs `true`
console.log(true === false); // logs `false`
```

## String

**Values of the `string` type are intended to represent text values that should be read or spoken by humans. Values of the `string` type are always surrounded by either single quotes `''`, double quotes `""`, or backticks ``.**

Given that our programs so frequently interact with humans, it only makes sense that we need a data type to represent the way humans interact with each other through language. In JavaScript (and in many other languages), this data type is called `string` as in **a string of characters.**

```javascript
console.log('Hello');                                          // logs `'Hello'` to the console
console.log('Hello you.');                                     // logs `Hello you.` to the console
console.log('Someone said "I am worthy."');                    // logs `Someone said "I am worthy"` to the console
console.log("It's realistic to expect learning to take time"); // logs `"It's realistic to expect learning to take time"` to the console
```

Values of the `string` type can be compared with the comparison operators, and just like with values of the `number` and `boolean` types, when compared, result in a new value of the `boolean` type.

```javascript
console.log('this' === 'this');                                         // logs `true` to the console
console.log('this' === 'that');                                         // logs `false` to the console
console.log('This' === 'this');                                         // logs `false` to the console
console.log('This.' === 'This');                                        // logs `false` to the console
console.log('Is this really the same?' === 'Is this really the same?'); // logs `true` to the console
```

Interestingly, values of the `string` type can also use the `+` operator, but unlike values of the `number` type, `string`s when used with `+` are concatenated (joined) together:

```javascript
console.log('Me and ' + 'you.')                                       // logs `'Me and you'` to the console
console.log('Me and ' + 'you... ' + 'your mama and your cousin too.') // logs `'Me and you... your mama and your cousin too.'` to the console
```

## Undefined

**`undefined` is a type with exactly one value: `undefined`. The `undefined` value signifies that there is something here, but we do not presently know what it is.**.

`undefined` is like that currently-unoccupied storefront with a lease sign out in front of it downtown: there's something there, but we don't know what it actually is at this point in time.

`undefined` has very little in the way of operators. You can compare it and that is about it:

```javascript
console.log(undefined === undefined);   // logs `true` to the console
console.log(undefined === 1);           // logs `false` to the console
console.log(undefined === 'undefined'); // logs `false` to the console
```

## Null

**`null` is a type with exactly one value: `null`, which signifies there is nothing here.**

While `undefined` states that there is not something here *presently*, it implies that there might be something here at some point in time. `null` is intended to express **absolutely nothing at all** as in the set of giraffes that have been known to fly to the moon is `null`.

`null` can be compared to other values:

```javascript
console.log(null === null);      // logs `true` to the console
console.log(null === undefined); // logs `false` to the console
console.log(null === 'null');    // logs `false` to the console
```

The difference between `undefined` and `null` in JavaScript can be subtle, especially for newcomers to the language. One way to think about these two flavors of nothing is that `undefined` is when something is unintentionally or passively nothing; `null` is reserved for things that are explicitly and intentionally nothing. For example, look at this code:

```js
let notAssigned;
```

The value of `notAssigned` is `undefined`. We didn't assign any value to the variable, so it defaults to the passive version of nothing: `undefined`. In order for a variable to become `null` it must be actively set to `null`:

```js
let explicitNothing = null;
```

We will revisit this when we discuss variables in an upcoming section.

## Object

In JavaScript, values of the `object` type are a big deal, and rather complicated. Values of the `object` type can (for the most part) be recognized by their opening and closing curly braces: `{}`. They are fundamentally different from the other data types we have seen thus far, to a large degree because every value of the `object` type, even if it looks the same, is in fact a unique value, thus:

```javascript
console.log({} === {}); // logs `false` to the console since every value of the type `object` is distinct and unique
```

It turns out that functions are in fact values of the `object` type, as are arrays, sets, and maps (which we have not talked about at all yet). We will not, at this present time, be covering values of the `object` type in any further detail, though later in this content we will talk about **arrays** which are a certain kind of object, and, you can rest assured you will learn a *ton* about objects in your pursuit of programming greatness. They are so common and important that we felt they **had** to be *mentioned*, even though this article does not set out to illuminate their use.

## Symbol

Symbols were added to the JavaScript language in 2015 largely as a way to add new features to the language without potentially breaking already existing code. There are advanced use cases for them that require a master understanding of objects. We will not cover symbols here, and you will in fact be hard-pressed to find programmers who can talk about them reasonably. Unlike objects, Symbols are not (yet) in wide use.

## Conclusion

JavaScript values can are always one of seven types, and depending on their type, have specific ways that they can be utilized. This short section served as a crash course to the JavaScript types, focusing on some simple operations available on values of the types `number`, `string`, and `boolean`.

Having exposure now to values of different types and how to perform basic operations on them, we will return to our discussion of calling functions.

Before proceeding you should be able to:

- Understand that values of different types can be used to do different kinds of operations
- Be able to identify values of the `number`, `string`, `boolean`, `undefined`, and `null` types
- Be able to perform basic operations on values of the `number`, `string`, and `boolean` types


## Table of Contents

### Basic Training Materials

- [Introduction](../README.md)
- [JavaScript and Modern Web Development](modern_web_development.md)
- [Dev Environment Setup](setup.md)
- [Introduction to Functions](intro_to_javascript_functions.md)
- [Basic Use of Functions](basic_use_of_functions.md)
- *JavaScript Types Crash Course*
- [Functions that Make Values](functions_that_make_values.md)
- [Variables](variables.md)
- [String Methods](string_methods.md)
- [Introduction to Arrays](intro_to_arrays.md)
- [Defining Functions](defining_functions.md)
- [Leveraging Multiple Functions](leveraging_multiple_functions.md)
- [Next Steps](next_steps.md)

### Advanced Content

- [Passing Functions as Arguments](passing_functions_as_arguments.md)
- [Higher Order Array Methods](higher_order_array_methods.md)

### Appendix

- [Reference and Further Study](reference.md)
