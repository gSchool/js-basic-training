# Leveraging Multiple Functions

**Aim to write small functions that do one thing / enact a single verb. When a single verb involves several smaller actions, house function calls in outer functions.**

## Objectives

By the end of this section you should be able to:

- Attempt solving complicated problems by writing fantasy functions to solve them
- Break fantasy functions into smaller fantasy functions until you are able to use simple operators or built in functions

## The Power of Wishful Thinking

This author feels very strongly that you should aim to write code that reads like English. Assuming that functions are like verbs, and that variables can stand in for noun like values, it is oftentimes an excellent strategy to simply write out a series of function calls reflecting what you wish to do, even if those functions do not yet exist, and then, go back and write the function defintions to accomplish what you are wishing for. A fluency with built in functions and methods available to you tends to facilitate this process.

As an example, imagine that we need to find out if the second word in the sentece contains a certain letter. We can start solving this problem by simply imagining that we have the function we would wish for to solve the problem:

```javascript
let sentence = 'This is a sentence';

let secondWordHasE = doesSecondWordHave('e', sentence);

console.log(secondWordHasE); // should log `false` to the console
```

Now that we have this "fantasy function" `doesSecondWordHave` we should set out to define it. Similar to our main problem, we can very much imagine having even more fantasy functions to help us with our larger task:

```javascript
function doesSecondWordHave(letter, sentence) {
  let words = makeIntoWords(sentence);       // `makeIntoWords` does not yet exist
  let secondWord = getSecondWordFrom(words); // `getSecondWordFrom` does not yet exist
  return hasLetter(secondWord, letter);      // `hasLetter` does not yet exist

  return hasLetter;
}
```

Let's continue by defining the functions that we wish we had, starting with `makeIntoWords`:

```javascript
function makeIntoWords(sentence) {
  return sentence.split(' ');
}
```

Already we see that familiarity with built in methods will serve me in making the functions I need. Let's continue now in making the `getSecondWordFrom` function:

```javascript
function getSecondWordFrom(words) {
  return words[1];
}
```

And lastly, the `hasLetter` function:

```javascript
function hasLetter(word, letter) {
  return word.includes(letter);
}
```

Putting it all together, we know have the following small program:

```javascript
function doesSecondWordHave(letter, sentence) {
  let words = makeIntoWords(sentence);       // `makeIntoWords` does not yet exist
  let secondWord = getSecondWordFrom(words); // `getSecondWordFrom` does not yet exist
  return hasLetter(secondWord, letter);      // `hasLetter` does not yet exist

  return hasLetter;
}

function makeIntoWords(sentence) {
  return sentence.split(' ');
}

function getSecondWordFrom(words) {
  return words[1];
}

function hasLetter(word, letter) {
  return word.includes(letter);
}
```

Now we can actually try to use the function as we originally wished to:

```javascript
let sentence = 'This is a sentence';
let secondWordHasE = doesSecondWordHave('e', sentence);

console.log(secondWordHasE); // logs `false` to the console

function doesSecondWordHave(letter, sentence) {
  let words = makeIntoWords(sentence);       // `makeIntoWords` does not yet exist
  let secondWord = getSecondWordFrom(words); // `getSecondWordFrom` does not yet exist
  return hasLetter(secondWord, letter);      // `hasLetter` does not yet exist

  return hasLetter;
}

function makeIntoWords(sentence) {
  return sentence.split(' ');
}

function getSecondWordFrom(words) {
  return words[1];
}

function hasLetter(word, letter) {
  return word.includes(letter);
}
```

It may seem at a first glance that this methodology for writing functions was more effort than it was worth, but there are several very important reasons why it is a good idea to write code in this manner when it is possible:

- As a programmer, I never had to think about more than 1 thing at a time, and each thought was not much more than coming up with an accurate sentence to reflect what I wanted to do
- As the code base grew, I continued only to have to think about one relatively small thing at a time
- I know have a code base where the action part of the program (at the top where we call functions) reads like English and is very clear about what we are doing
- Future developers can find out what the program is doing at a glance, and can dig into details as they wish
- It will be easy to know where to look for details given how each function is so small
- It will be more likely that we can reuse these functions since they each only do one small thing well

## Conclusion

Only allowing yourself to think about complicated problems in the context of making easy statements will turn you into an incredible programmer.

Before continuing, be sure that you can:

- Attempt solving complicated problems by writing fantasy functions to solve them
- Break fantasy functions into smaller fantasy functions until you are able to use simple operators or built in functions

## Table of Contents

### Basic Training Materials

- [Introduction](../README.md)
- [JavaScript and Modern Web Development](modern_web_development.md)
- [Basic Use of Functions](basic_use_of_functions.md)
- [Functions that Make Values](functions_that_make_values.md)
- [JavaScript Types Crash Course](type_crash_course.md)
- [Variables](variables.md)
- [String Methods](string_methods.md)
- [Introduction to Arrays](intro_to_arrays.md)
- [Defining Functions](defining_functions.md)
- *Leveraging Multiple Functions*
- [Next Steps](next_steps.md)

### Advanced Content

- [Passing Functions as Arguments](passing_functions_as_arguments.md)
- [Higher Order Array Methods](higher_order_array_methods.md)

### Appendix

- [Reference and Further Study](reference.md)
