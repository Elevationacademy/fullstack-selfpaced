# Variables

Variables are the most fundamental part of any programming language. They let us store small bits of information, like this:

  

```js
const country = "Djibouti"
```
  

There are four parts to the above:

  

1.  `const` - this is an identifier, we'll learn about these in a sec
2.  `country` - this is the **name** of our variable - we can call our variables **whatever we want**, we just have to be consistent
3.  `=` - we use a single equals sign to **assign** values; this is _different_ from how we use equal signs in mathematics
4.  "Djibouti" - this is the **value** of our variable

  

One way to describe what we've done above is that we have **assigned** the value of "Djibouti" to the variable `country`.

  

If you write the above code in your **main.js** file, then write this on the next line:

  

```js
console.log(country)
```
  

Then when take a look at the terminal, you will see "Djibouti" in the output.

  

This is because `country` is now just a representation of the value "Djibouti". We can now use `country` anywhere instead of writing out "Djibouti" - which is a pain to write and hard to remember how to spell.

  

Just to underscore the fact that the variable name doesn't mean anything, write this code out, and check the console:

  

```js
const shoobeedoo = "Djibouti"
console.log(shoobeedoo)
```
  

The result is exactly the same! JS doesn't care or know.

  

What `shoobeedoo` or `country` are - it just knows they hold some value.

  

By the way, what we did above is called **defining** a variable. You can define a variable with (called **initializing**) or without a value. We'll see in the future why you would want to do the latter. Examples:

  


```js
const name = "Taylor" //initialized with the value of "Taylor"
let shoppingCartItems //not initialized, only defined - we'll learn about let in a second
```
  

The act of creating a variable without initializing it is called **defining a variable** - that means we are telling JS this variable exists, but we are not yet giving it a value.

###### Sidenote: Also notice that we **use camelCase** when we want our variable names to be longer - first word lowercase, and each subsequent word hasUpperCasedFirstLetter.

  

**Note:** if you do not initialize a variable, then its default value will be **`undefined`** **- this is a special expression in JavaScript** that means exactly what it says "this variable is undefined (so far)."

  

Try it out, console log `shoppingCartItems` after defining it with `let`, and see that the output is `undefined`.

  

----------

  

In JS, there is a difference between something that is _un_defined, and something that is _not_ defined.

Consider the following code, assume it is our entire file:

  


```js
let userResponse

console.log(userResponse) // prints undefined
console.log(userName) // throws an error
```
  

We _have_ defined that `userResponse` exists by saying let `userResponse`, we just haven't defined its value (i.e. we haven't initialized it) - hence this is `undefined`.

  

As for `userName` - it doesn't exist anywhere!

As such, you will see this error:

  

    Uncaught ReferenceError: userName is not defined

  

Important difference. Note it well.

  

## Identifiers

  

We have three main identifiers in JS:

  

-   var - you might see this every now and then (online or otherwise), but it's old and you shouldn't use it anymore
-   const - variables whose values will never change should be defined as const. This should be your default
-   Notice that when we use const we **must** initialize our variables since they can't change!
-   let - variables whose values can change should be defined as let

  

What we mean by "changing a value" is simple. Take this, for example:

  

```js
let age = 24
age = 25
```
  

First, notice that we don't (and can't) use `let` again on the same variable name* - we've already defined it.

###### *For both `let` and `const`, once we define a variable with a certain name, we **cannot** use that same variable name again!

  

But if we want to change it, we can just use the `=` sign again to **overwrite** its value. That easy.

  

Try doing the same with a `const` - go ahead, create a `const` variable, assign a value to it, then change it on the next line. Save your file, refresh the page, and look at your console - you should see an error!

  

    Uncaught TypeError: Assignment to constant variable.

  

Exactly what it sounds like - JS will not allow you to change the value of `consts` - they're constant!



## Types

  

Variables can hold pretty much anything. Text, numbers, booleans, objects, functions - we'll learn about all of these eventually. For now we'll focus on **strings**, **numbers**, and **booleans**.

  

Strings are any text. The text can have numbers, symbols, letters, whatever - we represent strings by wrapping something with quotes, like so:

  


```js
const sentence = "this is definitely; DEFINITELY a string!"
```
  

Remember, **anything that is in quotes is a string** - so if you do `console.log("sentence")` by mistake, you'll see "`sentence`" in the output, _not_ the value of the sentencevariable.

  

----------

  

Next we have **numbers** - these can be with or without decimals, but they **should not have quotes** around them.

  

```js
let moneyInBank = 600
```
  

Now I can do something like `console.log(moneyInBank + 300)`, and the output will be 900 - again, remember that `moneyInBank` is just holding some value for us (in this case, 600). Try it out for yourself ~

  

If you do wrap a number in quotes, then it is a string and arithmetic operations like the one above will not work as expected. It's like trying to say "Hello" + 3 - what does that even mean?

  

----------

  

Finally, we have **booleans** - these can have one of two values: `true` or `false` - there are **no quotes** here either:

  

```js
const instructorIsFunny = true
let enoughJokesInClass = false
```
  

We'll see later where we use booleans, but for now know that they exist and how to initialize them.

  

## Primitive Types

  

The variable types we've just talked about are called **primitive types**.

  

This has to do with how JS "remembers" the variables we create. We won't go too deep into it right now, but check this out:

  
```js
let a = 6
let b = a

console.log(a) //prints 6
console.log(b) //prints 6

b = 2

console.log(a) //prints 6
console.log(b) //prints 2
```
  

This may not seem exciting right now, but notice that the value of `a` is unaffected by the change in `b`, even though originally we set `b` to be equal to `a`. Again, this may seem obvious and natural - why should a change anyway? It's fine to think like this.

  

For now it's enough to understand that **whenever we initialize a primitive type variable, JS will create a new space in its memory to remember that variable**.

  

In other words, each primitive type variable is unique as far as JS is concerned. When we get into **arrays** and **objects**, we'll see how that's different.

  

## Concatenation

  

So far we know how to create variables, initialize them, change their values, and their different types. Now we will learn to **concatenate** variables.

  

Concatenation means to link or chain things together. If we have two strings, "car" and "pet", and we concatenate them, we will get "carpet". Isn't that crazy how unrelated those two words are and yet together they make something related to both?

  

Anyway.

  

In JS we generally concatenate strings, and the simplest way to do this is using the `+` operator:

  


```js
const firstString = "car"
const secondString = "pet"
const bothStrings = firstString + secondString
```
  

If you `console.log(bothStrings)`, you will see "carpet" in the output.

  

By the way, if you concatenate a string and a number, JS will join them into a string. Try it out and see what that means.

  

Another way to concatenate strings is using `+=` - we say "plus equals" - like this:

  


```js
let firstString = "bar"
firstString += "man"
console.log(firstString) // will print "barman"
```
  

When we use `+=`, we are modifying the variable's _own_ value. Literally, we are saying "you are now equal to yourself _plus_ this next thing."

  

Notice, therefore, that we must use a `let` since we are changing the value of `firstString`!

  

This works with number-string combinations, too:

  

```js
let galaxyVersion = "S"
galaxyVersion += 7
console.log(galaxyVersion) // will print "S7"
```
  

In the above we:

  

1.  Define the `let` variable `galaxyVersion` with a value of "S"
2.  Concatenate the number 7 (which will be converted to a string) to `galaxyVersion`
3.  Console log the result