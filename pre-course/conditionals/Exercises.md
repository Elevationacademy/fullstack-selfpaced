# Exercises

## Exercise 1

-   Initialize a number variable called `numChildren` (if you're using `prompt`, you can let the value of `numChildren` come from user input).

  

-   Initialize another variable, a boolean, called `isCareful`.

  

-   Write an if statement with the following logic:

  

-   If the person is **not** careful, then increment `numChildren` by 1

  

-   Console log `numChildren` to see that your code worked correctly

  

Check your work in the console first.


## Exercise 2

-   Initialize a number variable silverwareCount

  

-   Write an if statement that checks whether there is an even or odd silverwareCount

  

-   If it isn't even, console log that there is something missing


## Exercise 3

Given the following variables:

  
```js
let performance = "stellar"
let salary = 10000
const goodBonus = 1000
const stellarBonus = 3000
```
  

Write some code that increases the salary by either goodBonus or stellarBonus depending on the performance. Use the += operator.


## Exercise 4

Given the following variables:

  
```js
const isVIP = false
let cash = 500
```
  

Write some code that determines whether someone can enter the club or not.

The conditions to enter the club are either to be a VIP, **or** to have more than 300 in cash.

  

If the person can enter the club, welcome them with a nice greeting. Otherwise, make a snide remark in the console.


## Exercise 5

What will be the values of a, b, c, and d in the end? Think through this (write it out) before you test with code:

  
```js
const a = 3
let b = 2
let c = 0 || 12
let d

b = c
b++
if(d){
  b = a
}

d = a + (b * c)
d++
b += 2
```

## Exercise 6

Given the following variables:

  
```js
const gender = null
let profession = "business"
```
  

Write some code that completes the profession to "businessman", "businesswoman", or "businessperson" depending on whether `gender` is "male", "female", or `null`.

  

You should use concatenation ;)

  

Console log the result to test your code

  

There are other ways to write this code, different from the solution above - probably different from the solution you wrote, too; see if you can use `!` somewhere in there.

## Exercise 7

Tesla (the electric car company) is building a prototype for an AI salesperson. To do this, it needs _you_ to code part of the flow of the initial conversation with the customer. The rules of the flow are as follow:

  

-   If the customer has previously bought a Tesla, and the customer is a US citizen, the AI should check how long ago the customer bought their Tesla
-   If the Tesla was bought four or more years ago, the AI should ask (console log) whether the customer would like an upgrade
-   Otherwise, it should ask whether the customer is satisfied with the car
-   If the customer is not as US citizen but has bought a Tesla, the AI should ask whether the customer would like to move to the US
-   If the customer has not bought a Tesla, the AI should ask whether they are interested in buying one

  

For the following task you are given these inputs from each customer:

  
```js
let boughtTesla = true
const yearOfTeslaPurchase = 2014
let isUSCitizen = true
let currentYear = 2018
```
  

For your tests, change the values to make sure all the cases are working. For the above inputs, your AI prototype should output "Would you like an upgrade?"

  

Please only look at the solution after you've tried for a good 10 minutes, if you're stuck and have asked someone and you still can't get it.
