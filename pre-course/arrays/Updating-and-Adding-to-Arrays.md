# Updating and Adding to Arrays

Now that we have this knowledge of indexes, we can do something else too. We can update or **overwrite** values in an array. What do you think this will do? 

```js
companies[1] = "Twitter";
console.log(companies[1]);
```
<details>
<summary>
  Click here to reveal the answer.
</summary>
It will print out "Twitter" - that's because "Amazon" **was** in the first index, but now we overwrote it.
</details>

---
In fact, `console.log` the whole array and you should see that it's changed altogether!

We can also reset the entire array*, as we would with a variable, like this:

###### *Only if the array has a `let` identifier

```js
companies = ["Samsung", "Kellogg", "Coca-Cola", "J.P Morgan"]
```  

Now our entire `companies` array is different. The original "`Tesla`", "`Amazon`", etc are all gone entirely.

----------
#### **PUSH (ADDING TO AN ARRAY)**

What about adding new items to an array? That's where the `push` method comes in. Like this:
```js
companies.push("Blizzard Entertainment");
``` 

Syntax is straight forward: `nameOfArray` followed by `.push(..)` - and add whatever you want inside the parentheses.

Now check out `console.log(companies[4])` (assuming you haven't changed anything else in the array).

Remember that **`push`** **always adds the element to the end of the array**.

To add to the beginning of an array, use `unshift` - same syntax as `push`.

**Spot check:** Using your `myStuff` array, add the last item to the beginning, and the first item to the end.

If your array was `["a", "b", "c"]`, then now it should be `["c", "a", "b", "c", "a"]`

Check out the [solution here](https://codepen.io/ElevationPen/pen/byJZyp?editors=0010)
  
----------
 
You can also add several items with this (albeit uncommon) syntax:
```js
companies.push("Fox Entertainment", "Marvel Studios", "Rolex");
```
  
We again use commas to separate our items, but in this case notice there are no brackets. The above would add those three strings to the end of `companies`; try it out yourself and see.

This is uncommon syntax because generally we don't want to add groups of individual items. However, we do sometimes want to add one array to another. Say we had these two arrays:
```js
let employees = ["DeMarcus", "Kai", "Christina"]
let candidates = ["Tiffany", "Elana", "Carl"]
```  

Say that after their interviews, all of the `candidates` passed with flying colors and we want to add them to the `employees` array. Here's a cool way that **ECMAScript 2015, also known as ES6** (a version of JS that came out in 2015) gives us:
```js
employees.push(...candidates)
```

This is called **spread syntax**, or the spread operator, and what it does* is expand arrays in-place, so that the following two are virtually the same:

###### *among other things we'll learn about in the future
```js
employees.push(...candidates)
employees.push(candidates[0], candidates[1], candidates[2])
```

This _is_ useful because we often deal with arrays, and combining arrays is a common task.

**Spot check:** Duplicate your `myStuff` array using ...

For instance, if it was `["a", "b", "c"]`, it should now be `["a", "b", "c", "a", "b", "c"]`

 

Check out the solution [here](https://codepen.io/ElevationPen/pen/QRPoed?editors=0010)
