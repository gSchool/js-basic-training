# String Methods

**Values in JavaScript, depending on their type, have available to them functions that can be called directly on the value itself.** These functions, called directly on a value, are called **methods**, and in this section we will investigate several of the built in **methods** available on values of the `string` type.

## Objectives

By the time you complete this section you should be able to:

- Describe the syntax for calling methods
- Be able to use several methods for values of the `string` type

## Using Methods With Dot Notation

Values in JavaScript, depending on their type, have available to them functions that can be called directly on the value itself, this is done by adding a dot (`.`) to the value or the variable that the value is assigned to, followed by the function name followed by opening and closing parenthesis `()`, passing any arguments into the parenthesis just as we would do with any other function.

> There is a LOT more going on when we use methods that has to do with how JavaScript objects behave. Here we are most interested in learning how to **use** built in methods above and beyond understanding all the details, which can (and should) be done at a later time in your growth as a JavaScript programmer.

## String Methods: `toUpperCase` and `toLowerCase`

All values of the `string` type have a **method** available to them called `toUpperCase` which will return a new value of the `string` type that is the same as the string it was called on, only with all the characters being converted to upper case:

```javascript
let observation = 'something is going on here.';
let accusation = observation.toUpperCase();

console.log(accusation); // logs `'SOMETHING IS GOING ON HERE.'` to the console
```

You can see from the code above that it is almost like we are passing the string `'something is going on here.'` to the `toUpperCase` invocation.

A similar method is `toLowerCase` which is the inverse of `toUpperCase`:

```javascript
let angryDriver = 'HONK.';
let goose = angryDriver.toLowerCase();
let clownNose = goose.toUpperCase();

console.log(angryDriver === clownNose); // logs `true` to the console
```

## String Methods: `startsWith`, `endsWith` and `includes`

The string methods `startsWith`, `endsWith`, and `includes` all return a value of the `boolean` type depending on whether or not the given string starts with, ends with, or includes the passed in character:

```javascript
let name = 'Rowan';

console.log(name.startsWith('R')); // logs `true` to the console
console.log(name.endsWith('n'));   // logs `true` to the console
console.log(name.includes('o'));   // logs `true` to the console
```

## String Methods: `indexOf` and `lastIndexOf`

Indexing is a way to indicate the position of a value. In JavaScript, whenever we wish to talk about the position of something, we give the first most position the value `0`, and then add `1` for each position following.

For values of the type `string`, the first character in the string is considered to be at index `0`, the second at index `1` and so on. The `indexOf` method on strings returns the index of the first instance of the passed in string for the string the method is called on:

```javascript
let name = 'lil RoRo';
console.log(name.indexOf('l')); // logs `0` to the console
console.log(name.indexOf('R')); // logs `4` to the console
console.log(name.indexOf(' ')); // logs `3` to the console
```

The `lastIndexOf` method on strings returns the index of the last instance of the passed in string for the string the method was called on:

```javascript
let name = 'lil RoRo';
console.log(name.lastIndexOf('l'));                       // logs `2` to the console
console.log(name.lastIndexOf('R'));                       // logs `6` to the console

console.log(name.indexOf('l') === name.lastIndexOf('l')); // logs `false` to the console
console.log(name.indexOf('i') === name.lastIndexOf('i')); // logs `true` to the console
```

## String Method: `substring`

The string method `substring` takes two arguments - the beginning index and the ending index - and returns a substring of the string that it is called on starting with the beginning index, up to but **not** including the ending index. If the second argument is left out, `substring` will return a string starting with the beginning index passed in, until the end of the string.

```javascript
let phrase = 'Sometimes all you can do is practice';

let firstSubstring = phrase.substring(10);
console.log(firstSubstring);                  // logs `'all you can do is practice'` to the console

let some = phrase.substring(0, 4);
console.log(some);                            // logs `'some'` to the console

let indexOfFirstP = phrase.indexOf('p');
console.log(phrase.substring(indexOfFirstP)); // logs `'practice'` to the console
```

## Other String Methods

There are a lot more methods for values of the `string` type and eventually you will want to familiarize yourself with all of them. It is not really worth the time practice and master all of them right away, however, a cursory study of what methods are even available to you will help you to solve problems on account of knowing what methods you have at your disposal.

In the opinion of this author (and many others) **the** source of truth for JavaScript language documentation in the *Mozilla Developer Network* or *MDN* for short. With that in mind, should you wish to familiarize yourself with all of the available methods for values of the `string` type, please refer to, as we say, [the docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Methods_2).

## String Method `split` as a Segue to Arrays

The string method `split` takes a single character and returns an **array** (much more on arrays soon) containing subsections of that string resulting from splitting on the passed in character. For example:

```javascript
let sentence = 'This is a sentence';
let words = sentence.split(' ');

console.log(words); // logs `['This', 'is', 'a', 'sentence']` to the console

let mashup = 'ThisXisXaXmashup';
let mashupWords = mashup.split('X');

console.log(mashupWords); // logs `['This', 'is', 'a', 'mashup']` to the console
```

But what is an array anyhow? We will now turn our attention to answering this question.

## Conclusion

Before continuing, be sure that you can:

- Describe the syntax for calling methods
- Be able to use several methods for values of the `string` type

## Table of Contents

### Basic Training Materials

- [Introduction](../README.md)
- [JavaScript and Modern Web Development](modern_web_development.md)
- [Dev Environment Setup](setup.md)
- [Introduction to Functions](intro_to_javascript_functions.md)
- [Basic Use of Functions](basic_use_of_functions.md)
- [JavaScript Types Crash Course](type_crash_course.md)
- [Functions that Make Values](functions_that_make_values.md)
- [Variables](variables.md)
- *String Methods*
- [Introduction to Arrays](intro_to_arrays.md)
- [Defining Functions](defining_functions.md)
- [Leveraging Multiple Functions](leveraging_multiple_functions.md)
- [Next Steps](next_steps.md)

### Advanced Content

- [Passing Functions as Arguments](passing_functions_as_arguments.md)
- [Higher Order Array Methods](higher_order_array_methods.md)

### Appendix

- [Reference and Further Study](reference.md)
