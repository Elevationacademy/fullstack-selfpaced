# Objects as Variables

Let's discuss this notion of objects-as-variables again.

Once you create an object - it's just a normal variable. That means you can use it in functions, arrays, in loops, etc. For example:
```js
let apple = {
  color: "red",
  name: "apple"
}

let cheese = {
  color: "yellow",
  name: "cheese"
}

let foods = [apple, cheese]

console.log(foods[0].name) // apple
console.log(foods[1].color) // yellow
```
  

Breaking it down:

  

-   Lines 1-9: creating two objects
-   Line 11: creating an array with some values inside - yes, objects in arrays!
-   Lines 13-14: accessing object values, _from the array_

  

Let's look at line 13 real quick. One step at a time:
```js
console.log(foods[0])
``` 

This is fine, right? It will just print whatever is the first item in the array `foods` - in this case, it is the entire `apple` object. 

Now remember, if we do:
```js
console.log(apple.name)
```  

It's just **accessing** the object's name property.
  

Since `foods[0]` **is the exact same** as `apple`

Then `foods[0].name` **is the exact same** as `apple.name`
  

**Spot check:** how would you extract the color of `apple`, from the `foods` array?
<details>
<summary>
  Click here to reveal the answer.
</summary>
  
```js
foods[0].color
```
</details> 

----------

Great. Now let's go back to our `bag` example from before, and add a twist:
```js
const bag = {
  weight: 10,
  owner: "Larissa",
  items: [                   // an array with objects in it!
    {item: "Pen", count: 2},
    {item: "Bottle", count: 1},
    {item: "Book", count: 3}
  ]
}
```
  
If your mind is a little blown now, no worries. Let's take it one step at a time:
  
-   Line 1: initialize an object called `bag`
-   Line 2: give the bag a key of `weight` with a value of 10
-   We could access this using `bag.weight` - no problem
-   Line 4: give the `bag` a key of `items`, with a value of an **array**
-   If we console log `bag.items` we'll see the whole array which ends on line 8
-   Lines 5-7: instead of inserting numbers/strings into the array, we're inserting **objects**
-   Each object in the array has the same two **keys**, but with different **values**
-   These objects don't have a name. We would access them as we access array elements: `items[0]`

  Say we wanted to know how many books Larissa has in her bag, we'd do this:
 
```js
console.log(bag.items[2].count) // prints 3
```  

Again, take it one step at a time:

```js
bag.items // the whole items array://[{item: "Pen", count: 2}, {...}, {...}]

bag.items[2] // the item at index #2://{item: "Book", count: 3}//remember we access arrays with indexes!

bag.items[2].count // the count of the item at index #2
```  

Boom. Objects.
 

**Spot check:** get the name of the first item in the bag. You should be able to do this no problem ~

<details>
<summary>
  Click here to reveal the answer.
</summary>
  
```js
bag.items[0].item
```
</details> 