# Exercises

## Exercise 1

Define four variables:

  

1.  A `const` called `maxCapacity` with the value of 14
2.  A `let` called `surfTime` with the value of true
3.  A `let` called `bestStudent` - do not initialize this
4.  A `const` called `purposeInLife` - do not initialize this
  

For each variable, console log it. What do you see each time? Does it all make sense?

  
<details>
<summary>  
Click here to reveal a hint...  
</summary>

You should see `undefined` for `bestStudent` - because it's not defined

You should get an error when you try to define a `const` without a value - that is not allowed in JS
</details>


## Exercise 2

Define a string variable, then create a new variable called `result` that is the concatenation of your variable and the string `"is the best thing ever"`

  

Console log the new variable and make sure the spacing looks good.

  

Here's an example

```js
const myVariable = "The potential of the future " // notice the space we're leaving at the end

const result = myVariable + "is the best thing ever"﻿

console.log(result) // logs "The potential of the future is the best thing ever"
```
  

Now do the same, but instead of using a new variable, concatenate `"is the best thing ever"` to your variable directly. You might get an error - if you do, you know how to deal with it ;)


## Exercise 3

Define two string variables: `password` and `confirmPassword` and give them both a value - then write some code that compares the equality of the two variables.

## Exercise 4

How would you calculate the following?

  

-   423 X 12
-   802 / 2
-   The sum of 5 and 6, multiplied by 3 (use parentheses)

## Exercise 5

Determine whether the following are truthy or falsey:

  

-   `(5 > 2) && false`
-   `!("knife" === "sword")`

  

-   `(1 < 2) || (-1 > -1) || !false`

  

-   `""`

  

-   `(31 % 5) == "1"`

  

-   `!!true`

  

-   `"5th Avenue" != "5th Avenue"`

  

-   `52 !== "52"`

  

-   `(undefined || null)`

  

Think first before you test it out in code. Ask if you don't understand why certain results are what they are.


## Exercise 6

Bit of a mind-twister: what are the values of a, b, and c in the end?

  
```js
let a = 3
a = 4
let c = 0
let b = a
b = 2
a = b
b = c
c = a
a = b
```


