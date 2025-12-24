# Conditional Statements

Sometimes when we write code, we want to only do things given a certain condition. Just like in real life, where you might want to allow someone into a bar only if they're above the age of 16 (hooray Czech Republic).

To do so, we use **conditional statements**, which in JS are `if`, `else if`, and `else`.

The following shows the anatomy of an `if` statement:

```js
if(someCondition) { //opening curly brace

  //do something if the condition resolves to true

} //closing curly brace
```
  
Everything inside of the curly braces is said to be **inside the if block** - this is code that will execute if and only if `someCondition` resolves to `true`.  

Generally speaking, a **block of code** is enclosed between curly braces - we'll see this in loops, functions, and classes in future lessons.  

Let's look at a simple example:  

```js
if(false){
  console.log("This will never see the light of day")
}
```

In if statements, **whatever the expression inside the parentheses resolves to will determine whether the condition passes or fails.** 

Try out the code above, and you'll notice that the sentence does not print out in the console. That is because `false` - obviously - resolves to `false`, which is a failure of the condition.  

Will we see the following console log?  

```js
if("test" == "test"){
  console.log("Hello?")
}
```
  

We will, because `"test" == "test"` **resolves to true**, so it is as if we had said:
```js
if(true){
  console.log("Hello?")
}
```
  

As far as JS is concerned, the two conditions above are virtually the same.

How about this:

```js
const name = "Elizabeth"
if(name == "Queen"){
  console.log("All hail!")
}
```
<details>
<summary>
  Click here to reveal the answer.
</summary>
Nope, we will not see the above, because the value of `name` is not equal to "Queen", which is the comparison we are making  
</details>
----------

Here is a bar-in-the-Czech-Republic example: let's say we want to allow someone into the bar if they're above 16, but kick them out otherwise. That's where `else` comes in:

```js
let age = 15
const minimumAge = 16

if(age >= minimumAge){
  console.log("Come in, beer's on the house!")
} else {
  console.log("I'm calling the police. You have two minutes to leave.")
}
```
  

In the above code, we have two blocks of code - the first is between the curly braces of the if, and the second block is between the curly braces of the else.

Only the second block will execute because *`age >= 16`* resolves to `false`, i.e. the condition failed: 15 is _not_ greater than or equal to 16.

Remember, **in if-else statements, only one* of the blocks will execute, ever.**

###### *And **always** one


With this basic understanding of conditionals, we can bring back our special falsey expressions and put them to practice 

---------- 

Let's say we're creating a user-login page, and we need the user to input their username to login in. A simple flow could look like this: 

```js
let username

if(username){
  //let the user in
} else {
  alert("You must enter your username")
}
```
  

In the above code, only the `else` block will execute because `username` has not been initialized!


Remember, variables that are defined but not initialized have a default value of `undefined`, and in JS `undefined` resolves to `false`.

###### Say this sentence in an interview and you'll sound like a seasoned developer already

Make sure you understand the above before moving on.

--------- 

Ok, what if the user enters their username, but it's not the right name?

We can add another condition to make sure that there is a username, **and** the username is correct. You can probably guess what it will look like if you think back to what we learned about logical operators.

```js
let username = "serious_cat612"
const correctUsername = "serious_dog612"

if(username && (username == correctUsername)){
  //let the user in
} else {
  alert("You must enter your username")
}
```
  
Remember that with `&&` both sides must resolve to true.

Remember how empty strings resolve to `false`? Well, non-empty strings resolve to `true` - so at least the left side of our `&&` above is good*

###### *`username` is holding the value of "serious_cat612" which is a non-empty string which resolves to true

As for the right side, `username` _does not_ equal `correctUsername`, and therefore the right side of the && resolves to false.

Because `true && false` resolves to `false`, the whole `if` condition fails. Boom, logic.

You'll notice that our logical flow is a little weird. If the user enters the wrong `username`, then the `else` block gets executed, and we tell the user to enter a `username` - even though ze already did!

One solution to this is to use **nested conditions**:
 
```js
let username = "serious_cat612"
const correctUsername = "serious_dog612"

if(username){
  if(username == correctUsername){
    // let user in
  } else {
    console.log("Hey dog, that's the wrong username")
  }
} else {
  alert("You must enter your username")
}
```  

Now the code is getting larger but if you follow the logic it should make sense:
  
-   If there is a username, we want to check that it's correct
-   If the username is correct, we'll let the user in
-   Otherwise, we'll tell the user that their username is wrong
-   Otherwise, we'll tell the user they need to enter their username

Note that the nested if-else only runs if there is a username - that is, we are not going to check whether the username is correct if there isn't a username to begin with!

In general, like we said before, any code inside an if block will only run if its condition resolves to `true`, and the code inside the `else` block will only run if the if's condition resolves to `false`.

Therefore, given the code above, we will see "Hey dog, that's the wrong username" in the console, because the first condition resolved to `true` (there is a username), but the second condition resolved to `false` (usernames didn't match).

Note: **You cannot have an** **`else`** **by itself, it must be coupled with an** **`if`****.** That said, **you do not have to have an** **`else`** **for every** **`if`.**

So try this on for size. Write out an if-else that follows this logic:

-   If there is enough money in the bank, buy a gift
-   Otherwise,
-   If the user has a job, tell the user to go work
-   Otherwise, tell the user to go find a job

You can use the following variables to start off:

```js
let enoughMoneyInBank = false
let hasJob = true
```
  

Think about this, write it out, test it in the browser, then peek at [this solution](https://codepen.io/ElevationPen/pen/wbZYex?editors=0010).

You can nest `if`s without end, but eventually it becomes very ugly and hard to maintain - avoid nesting too deep in general.

----------

Final concept before you get to practice: `else if`.

Sometimes, between the `if` and the `else`, we want to test other conditions. For instance, think of a self-driving car that's looking at a traffic like. It needs to know what to do at each color:
```js
let color = "orange"

if(color == "green"){
  console.log("Vroom.")
} else if(color == "orange"){
  console.log("Release breaks")
} else {
  console.log("Slam breaks and jump out of car")
}
``` 

Note a few things about the above, and conditionals in general:
 
-   Again, **only one block will ever execute** - that's just how conditional statements work
-   We didn't have to check for "red" specifically because it's the default
-   More generally, **the** **`else`** **block will always execute if none of the previous conditions are met**
-   Like `else`, `else if` must come _after_ an `if`
-   The final `else` is still not required
-   If you _do_ have an else, it **must be the last block**
