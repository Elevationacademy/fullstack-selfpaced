# Variables from Arrays

Note that **we can initialize new variables with data accessed from an array**. For instance:
```js
const firstCompany = companies[0]
console.log(firstCompany) // prints "Tesla"
console.log(firstCompany == companies[0]) // prints true
``` 

What we've done here is accessed the value of the first element in ```companies```, then stored it inside a variable called firstCompany - this is a totally legitimate way of initializing variables.

By the way, we can use ```.length``` and a bit of simple math to access the _last_ element of an array.

**Since** **```.length```** **gives us the length of an array, then** **```.length - 1```** **will always be the index of the last element:**
```js
const plants = ["Oak", "Lilly", "Belladonna", "Tulip", "Yew"]
console.log(plants.length) // prints 5

let lastIndex = plants.length - 1 // equal to (5 - 1) = 4
console.log(plants[lastIndex]) // prints "Yew"
console.log(plants[4]) // the same
```

Write a bit of code that, given the plants array, prints out "The first plant is Oak, and the last one is Yew" - you should be able to do this in one line  

<details>
<summary>
  Click here to reveal the answer.
</summary>

```js
console.log("The first plant is " + plants[0] + " and the last plant is " + plants[plants.length - 1])
```
</details>