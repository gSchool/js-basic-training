# JavaScript Functions

JavaScript programs are collections of functions, each function being a smaller program unto itself. The ability to use built-in JavaScript functions, to build our own functions for use, and to organize our code into concise and well-organized functions, is one of the very most central skills to becoming an effective JavaScript programmer.

## Objectives

## Functions are Verbs

Before learning about the specifics of using and creating functions, it will be helpful to spend some time learning how to think about functions.

**Functions _do_ things, and should therefore be thought of as the _verbs_ of your program.**

Consider the following JavaScript code, which runs a series of functions. Don't worry if some of the syntax is unfamiliar at this time:

```javascript
wakeUp();
brewCoffee();
drinkCoffee();
eatBreakfast();
cleanUp();
goToWork();
```

This program **does** several things, and is using several functions to **do** these things. Programmers can name their functions practically whatever they would like, and because the programmer who wrote the code above chose to name their functions as verbs, it makes for a clear and easy to read program.

## Some Functions Make Something

While every function does something, some functions also **make** something. This is reflective of our lives as well where sometimes when we *do* things, we also *make* something:

- When we do the activity of brewing coffee we make coffee
- When we do the activity of going to work we make money

Compare this to things we might do where we don't really make something:

- When we wake up we do something but we don't really make something new (philosophical discussions aside)
- When we drink coffee we do something but we don't really make something new

With this in mind, here's our example program again, but this time, two of the functions *make* things. Again, don't worry about the specific JavaScript language syntax in this program yet, we will be talking about it at great length later. For now we are just clarifying the mental models that will allow us to write code effectively:

```javascript
wakeUp();

let coffee = brewCoffee(); // The act of brewing coffee results in a new thing: coffee

drinkCoffee();
eatBreakfast();
cleanUp();

let money = goToWork();    // The act of going to work results in a new thing: money
```

## Some Functions Can Be Given Things to do Work With
