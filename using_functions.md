# Using Functions

Utilizing functions involves two steps:

1) Defining the function
2) Using the function

A function **must** be defined before it can be used. However, in addition to writing our own function definitions to use, we can also use functions that have already been defined for us. This section will serve as an introduction to using functions by way of using some functions that have already been defined for us anywhere we might choose to write JavaScript code.

## Objectives

## Terminology for Using Functions

Up until this point in time we have talked about "using" functions, but in fact as programmers we tend to avoid using this ambiguous term. Rather, when we want to "use" a function we say one of the following, which are in fact synonymous:

- That we **call** the function
- That we **invoke** the function

Thus the following statements are all true about the next block of code:

- We are **calling** `eat` and then **calling** `drink`
- We are **invoking** `eat` and then **invoking** `drink`
- Here we see the `eat` function being **invoked** before **calling** `drink`
- Here we see 2 function **invocations**, one to `eat` and one to `drink`

```javascript
eat();
drink();
```

> It is worth noting that each of these function calls end with a semicolon `;`. You can think of semicolons in JavaScript as the equivalent to periods in English: they are inteded to signify the end of "a sentence". These semicolons are in fact optional, and there are some rather obscure reasons why you might or might not choose to use them which frankly aren't really worth getting into. Rather than describe all the specifics of how to use them, we will include them throughout our code here and you will learn via immersion when and how to use them in your own code.

Previously we have talked about "giving functions things to affect their behaviour", but the actual term for the "thing we give" a function is an **argument**, which we **pass** to a function.

Thus the following statements are all true about the next block of code. Fluency with the technical jargon often results in leaving out some of the terms altogether:

- On the first line we call `drink`, **passing** `coffee` to it as its only **argument**
- When we call `cleanUp` we do not **pass** it any **arguments**
- First we call `drink` with the `coffee` **argument**, and then with `tea`
- Here we call `drink` with `coffee` and then with `tea`
- We are not calling `cleanUp` with anything

```javascript
drink(coffee);
drink(tea);
cleanUp();
```

## Calling Already Defined Functions

**In order to call a function (assuming it has been defined), add opening and closing parenthesis `()` to its name or definition. If you wish to pass in any arguments, put them inside the parenthesis, separating them by a comma `,` if there are more than one.**

We have already seen this a number of times, but now you have a formal defintion.

To explore this we will call some functions that are already defined for us any place where me might run JavaScript code. These functions are called **built-in** functions, of which there are many.

The first built in function we will explore is called `console.log`, which takes any number of arguments, and prints them all to the developer console, separated by a space. Here we will call `console.log`, passing it a single argument, the number `1`:

```javascript
console.log(1); // Calling this will result in `1` being logged to the developer console
```

If we pass in more than one argument, `console.log` will print them all to the console separated by a space:

```javascript
console.log(1, 2, 3); // Calling this will result in `1 2 3` being logged to the developer console
```

Admittedly, passing numbers into `console.log` is not going to take us very far, but before we can go into more interesting territory, we need to learn more about what it means to pass in a *number*.

## A Crash Course in JavaScript Types

In most programming languages, JavaScript amongst them, programmers have at their disposal different kinds (or **types**) of values that they can utilize in their programs.

In the real world too we have different types of things to build with, and each of these types have their own qualities, and rules for interacting with other types. Here are some real world examples meant to demonstrate how different types of things have their own qualities and rules for interacting with other types:

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

In JavaScript there are 7 types:

- Number
- Boolean
- String
- Undefined
- Null
- Object
- Symbol

Let's deal briefly with each of them in turn.

### Number

**Values of the `number` type look and behave like numbers and can be positive, negative, whole, decimal, zero, or infinity.**

Here are some examples:

```javascript
1
42
0
-888
3.14156
Number.POSITIVE_INFINITY
```

JavaScript comes with a set of **operators** that act on values of the `number` type, resulting in the creation of a new value, also of the `number` type:

- `+` creates a new value of the `number` type that is the sum of two other values of the `number` type
- `-` creates a new value of the `number` type that is the difference of two other values of the `number` type
- `*` creates a new value of the `number` type that is the product of two other values of the `number` type
- `/` creates a new value of the `number` type that is the quotient of two other values of the `number` type
- `%` creates a new value of the `number` type that is the remainder of dividing two other values of the `number` type

Because using these operators creates a new value of the number type, we can pass in **expressions** which use these operators, into `console.log` and see the result of the calculation in the developer console:

```javascript
console.log(80 + 2); // logs `82` to the console
console.log(11 - 3); // logs `8` to the console
console.log(10 * 8); // logs `80` to the console
console.log(25 / 4); // logs `6.25` to the console
console.log(16 % 3); // logs `1` to the console
```

There are also a set of comparison operators that act on values of the `number` type which result in the creation of a new value of the `boolean` type, to which we will now turn our attention.
