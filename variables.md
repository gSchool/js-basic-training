# Variables

In JavaScript, a variable stores a value of any type so that we can use it later in our program.

## Objectives

## Declaring Variables

**In JavaScript, a variable stores a value of any type so that we can use it later in our program. In order to use a variable we must ffirst _declare_ it, after which we can _assign_ a value to it.**

In order to **declare** a variable in JavaScript, we use the `let` keyword, followed by the name we would like to give to the variable. In this example we declare a new variable called `name`:

```javascript
let name;
```

You can think of a variable as a box with a label on it. The box can contain any kind of thing, and the label (hopefully, though not necessarily) will help us understand what is inside the box.

When we first **declare** a variable it is automatically **assigned** the value `undefined`:

```javascript
let name;

console.log(name); // logs `undefined` to the console
```

Note that when we pass the **variable** `name` into `console.log` above, we do **not** surround it with quotes of any kind. Remember that values surrounded by quotes refer to **strings**. Variables, on the other hand, might "contain" a value of any type.

```javascript
let name;
console.log(typeof(name));    // logs `'undefined'` to the console
console.log(typeof('name'));  // logs `'string'` to the console
console.log(name === 'name'); // logs `false` to the console
```

> In addition to **declaring** a variable with the `let` keyword, we can also use the `const` or `var` keywords. We will avoid a detailed discussion of the implications for declaring variables with each of these 3 different keywords here, but for now:

> - Use `let` as your default for declaring variables
> - If you know for certain that your variable will never be changed (more on this below) then use `const`
> - Use `var` after you understand what **Global Scope** means, and in the meantime (although this isn't totally accurate) consider it as equivalent to `let`

## Assigning Values to Variables

After **declaring** a variable, we can **assign** a value of any type to it. When **assigning** values to a variable we use the **assignment operator** which is a single equal sign (`=`), placing the variable on the left hand side and the value we wish to "store" in the variable on the right. In the following example, we declare the variable `name` and then assign a value of type `string` to it:

```javascript
let name;
name = 'Rowan';

console.log(name);         // logs `'Rowan'` to the console
console.log(typeof(name)); // logs `'string'` to the console
```

As a matter of convenience, JavaScript allows us to both **declare** and **assign** a variable on the same line, thus:

```javascript
let name = 'Rowan';
let age = 1;
```

## Assigning Values Returned From Functions to Variables

Values returned from calling functions can be assigned to variables, just like any other value.

```javascript
let largestNumber = Math.max(5, 7, 2);
console.log(largestNumber); // logs `7` to the console
```

Storing returned values can be helpful in making our code easy to read and reason about, for example, compare the following two blocks of code:

```javascript
console.log(typeof(String(Math.max(0, 3, 1))) === typeof('number'));
```

Here's a refactor that makes some variable assignements to make the code easier to read and reason about:

```javascript
let largestNumber = math.max(0, 3, 1);
let largestNumberString = string(largestNumber);

console.log(typeof(largestNumberString) === typeof('number')); // logs `true` to the console
```

We *could* make a choice to use even more variables:

```javascript
let largestNumber = Math.max(0, 3, 1);
let largestNumberString = String(largestNumber);
let typeofLargestNumberString = typeof(largestNumberString);

let someString = 'number';
let typeofSomeString = typeof(someString);

let typeofSomeStringIsEqualTotypeofLargestNumberString = typofSomeString === typeofLargestNumberString;
console.log(typeofSomeStringIsEqualTotypeofLargestNumberString); // logs `true` to the console
```

But probably you will agree this last section of code is not so nice. Over time you will develop a keen sense for when to use variables and when not to based on personal experience. In the meantime, this author recommends you aim to write code that reads like English, which means, using descriptive variable names more often than not.

> Don't make the mistake of thinking that short variable names saves you time or makes your code run faster, it doesn't. Cryptic code will cost everyone dearly who has to come back and figure out what your code is doing later. While it is fun at times to write the most dense and elegant solution, **legible is better than clever.**

## Reassigning Values to Variables

Once you 
