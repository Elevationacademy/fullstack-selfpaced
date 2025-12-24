# Arrays

In JS, an **array** is just a fancy term for a list of items. The syntax looks like this:  

```js
let companies = ["Tesla", "Amazon", "Google", "Microsoft"]
```
  -   Like with variables, we start with an identifier, in this case a `let`
-   Again like a variable, we have to give a name to our array - here we've called this array `companies`, since it is a list of companies
-   Next we use `=` for **assignment**, again nothing new here
-   And finally we actually define the array
-   We start with an opening bracket, `[`
-   Then our **comma-separated** items (in this case a few strings)
-   And finally our closing bracket, `]`

You can have arrays with any amount of items. We can determine the number of items in the array using `.length`, like so:

```js
console.log(companies.length) // will print 4, because there are four companies in this array
```
An array that has no items is called an **empty array** - its length will be zero.
```js
let myFriends = [] // an empty array
```  

The `companies` array from before is known as an **array of strings** - because all of its values are strings. That said, arrays in JS can have multiple types:
```js
let infoAboutTesla = ["Tesla", 5000, true, "best"]
```
  

**That said** - we generally want to limit our arrays to one type.

Since arrays have many elements, we need a way to **access** this data. To do this, we need to understand the concept of array **indexes**.

## Indexes & Accessing Arrays

Let's look at `companies` again:

```js
let companies = ["Tesla", "Amazon", "Google", "Microsoft"]
```  

Here, the value `Tesla` is in the **0th index**, `Amazon` is in the **1st index**, etc.

An **index** is the position of an item in the array, from left to right, starting at 0.

The system of counting from 0 is known as **zero-based indexing** and is prevalent in virtually all programming languages, including JS.

Knowing this, we can print out the value of `Microsoft` by doing this:
```js
console.log(companies[3]);
```
I've just **accessed** the element in the **3rd index** of the array, which if we're counting 0..1..2..3 is exactly where `Microsoft` is. Try and see!

That's the syntax for accessing certain elements - but of course we can put anything in those square brackets `[ ]` so long as it **evaluates** to a number. For instance:
```js
console.log(companies[6-4]);
```
The expression `6 - 4` evaluates to `2`, so the above is virtually the same as `companies[2]`, which is...?

If, however, you try to access an index that does not exist, you will receive `undefined`:  
```js
console.log(companies[4]) // prints undefined
```

This should make sense because at the 4th index we _haven't yet defined_ any values for `companies`.


## Spot Check 1

Create an array called `myStuff` containing 3 strings inside of it. Then, console log the second item in the array.

check [this codepen](https://codepen.io/ElevationPen/pen/oROVpM?editors=0010) for the solution