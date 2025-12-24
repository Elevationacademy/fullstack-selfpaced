# Splice (Removing Elements From an Array)

As for removing items from arrays, it's a little more involved but still straightforward.

There is a method called `splice`, and it needs two things:

1.  Where to start removing
2.  How many to remove from that point
```js
companies.splice(1, 1)
```
That's saying "go to the 1st index, and remove 1 item from there". Test it out, then `console.log` your array again and see for yourself what happened.

When you use `splice`, the method will **return*** the item(s) that you removed from the array. See this:

###### *We'll learn about what **return** means exactly when we get to functions

```js
let fridge = ["Milk", "Eggplant", "Truffle", "Edible shoe"]
let removedItem = fridge.splice(3, 1)

console.log(removedItem) // prints ["Edible shoe"]
console.log(fridge) // prints ["Milk", "Eggplant", "Truffle"] 
```  

So not only does `splice` remove from an array, it also gives you the value(s) of the item(s) you removed. No matter how many items you remove, **you will receive an array in return**. Try this out for yourself.

Another note about **splicing**, if you do not indicate the second input (i.e. how many items to remove), then `splice` will remove everything from the the start you indicated and onwards:
```js
let badHabbits = ["Pizza", "Sugars", "White bread"]
let removedHabbits = badHabbits.splice(1)

console.log(removedHabbits) // prints ["Sugars", "White bread"]
console.log(badHabbits)// prints ["Pizza"]... can't get rid of that
```
  
See that? Because we told `splice` to start removing at index 1, but didn't tell it how many to remove, it removed everything from 1 and onward.  

Note that the `badHabbits` array stays as an array, even though we've removed everything except for 1 element.

**Spot check:** remove everything except for the _last_ item from this array: `["clouds", "sky", "birds", "worms", "earth", "dirt", "clothes", "human", "life"]`

The array should look like this in the end: `["life"]`

  Check out the solution [here](https://codepen.io/ElevationPen/pen/OYGGJM?editors=0010)

  ----------

The `splice` can also be used to add new elements in the array at a specific index, but you can figure that out by yourself using [this documentation](https://www.w3schools.com/jsref/jsref_splice.asp) ;)

----------

**Note on** **`const`** **vs.** **`let`** **with arrays:** You can still `push`, `splice`, and update certain indexes in arrays no matter the identifier - but if it's a `const` you **cannot** reassign the value of the array entirely. In other words:

```js
const people = ["Fred", "George", "Ron"]

people = ["Roger", "Alan", "Hewitt"] // this will throw an error
people[0] = "Alex" // allowed
people.push("Bellinda") // allowed
people.splice(2, 1) // allowed
```