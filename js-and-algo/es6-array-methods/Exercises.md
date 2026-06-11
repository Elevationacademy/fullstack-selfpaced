# Exercises


**For the following exercises (until ex. 7),** use [this array](https://jsonplaceholder.typicode.com/users) of user information. You should at no point be using any loops. Use arrow functions when appropriate.

Remember, JSON is valid JS, so you can just copy-paste it into a variable `let users = [...`

## Exercise 1
  
Map the data differently so you are left with an array of each user's `email` and their company's `name`. Your resulting array should look like this:
  
```js
[
  {email: "Sincere@april.biz", companyName: "Romaguera-Crona"},
  {email: "Shanna@melissa.tv", companyName: "Deckow-Crist"}, 
  ...
]
```

## Exercise 2

Create an array with user objects that have a zip-code that starts with "5".

You should be left with the objects whose IDs are 3, 4, and 7.


## Exercise 3

Modify your code from **Exercise 2** so that your resulting array only has the IDs of the matching users. You should chain your `filter` with a `map`. Ultimately, you should just have this array: `[3, 4, 7]`


## Exercise 4

Create an array of only `name`s, then only keep the names that [start with](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith) with the letter "C".

  

You should be left with `["Clementine Bauch", "Chelsey Dietrich", "Clementia DuBuque"]`


## Exercise 5

Determine whether all of the users live in the city of  "South Christy" - you should find the answer to be false in a single, beautiful line of code.


## Exercise 6

Find the user who's `suite` is "Apt. 950" - console log her company's name.

Your code should print out "Considine-Lockman".


## Exercise 7

Write a named function that receives a single parameter, `user`.

Using `forEach` and the named function you just wrote, console log "NAME lives in CITY, and owns the company COMPANY_NAME" for each user.

---

**From this point on the exercises are not using the users array anymore.**

## Exercise 8

Use `.reduce()` to calculate the total value of all inventory (price × quantity for each item, then sum them all up).

Input example:
```js
let inventory = [
    { name: "Laptop", price: 899.99, quantity: 5 },
    { name: "Mouse", price: 24.99, quantity: 12 },
    { name: "Keyboard", price: 79.99, quantity: 8 },
    { name: "Monitor", price: 249.99, quantity: 3 },
    { name: "Headphones", price: 149.99, quantity: 6 }
]
```
Expected Output: `7089.66`

## Exercise 9

Use `.reduce()` to create an object that counts how many students received each letter grade.

Grading scale:
- A: 90-100
- B: 80-89
- C: 70-79
- F: Below 70

Input example:
```js
let studentScores = [92, 87, 76, 95, 88, 72, 91, 83, 79, 96, 85, 74, 89, 93, 81]
```

Expected Output: `{ A: 5, B: 7, C: 3, F: 0 }`

## Exercise 10

Use `.reduce()` to calculate the final total cost including tax for all items in the cart.

Input example:
```js
let cartItems = [
    { name: "T-shirt", price: 19.99, category: "clothing", quantity: 2 },
    { name: "Laptop", price: 1299.99, category: "electronics", quantity: 1 },
    { name: "Coffee Beans", price: 12.99, category: "food", quantity: 3 },
    { name: "Headphones", price: 89.99, category: "electronics", quantity: 1 },
    { name: "Jeans", price: 59.99, category: "clothing", quantity: 1 }
]

let taxRates = {
    clothing: 0.08,    // 8% tax
    electronics: 0.10, // 10% tax  
    food: 0.05        // 5% tax
}
```
Expected Output: `1,677.87`
_Should return a single number representing the total cost with tax included._