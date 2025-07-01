# .reduce()

Sometimes, we want to _combine_ or _accumulate_ data from an array into a single value.

For instance, we might have an array of shopping cart prices and want to calculate the total cost. Instead of writing a whole for loop to sum up values, we can use `.reduce`:

```js
let prices = [12.99, 8.50, 23.75, 4.25, 16.00]

let total = prices.reduce((sum, price) => sum + price, 0)
console.log(total) // prints 65.49
```

The reduce method works by taking a callback function and an initial value (called the accumulator). In each iteration, the callback receives the accumulator and the current item, then returns a new accumulator value. It's called "reduce" because we're "reducing" an array down to a single value.

**Spot check:** given the following list of numbers, use reduce to find the largest number.

```js
let scores = [87, 92, 78, 95, 88, 91]
```

        
<details><summary>  
Click here to reveal the answer.  
</summary>

```js
let highestScore = scores.reduce((max, score) => score > max ? score : max, 0)
```

</details>


----------

Note that you can also use `reduce` to build up more complex data structures, like counting occurrences or grouping items:

```js
let votes = ["pizza", "tacos", "pizza", "burgers", "pizza", "tacos", "salad"]
```

Say we want to count how many votes each food item received. We could **reduce** the array into an object with counts:

```js
let voteCounts = votes.reduce((counts, vote) => {
    counts[vote] = (counts[vote] || 0) + 1
    return counts
}, {})
// Result: { pizza: 3, tacos: 2, burgers: 1, salad: 1 }
```

Notice that in this case we're starting with an empty object `{}` as our initial accumulator value, and we're modifying the accumulator object in each iteration before returning it.

**Common reduce patterns:**

- **Sum/Total:** `arr.reduce((sum, num) => sum + num, 0)`
- **Find maximum:** `arr.reduce((max, num) => num > max ? num : max, -Infinity)`
- **Count occurrences:** `arr.reduce((counts, item) => { counts[item] = (counts[item] || 0) + 1; return counts }, {})`
- **Group by property:** `arr.reduce((groups, item) => { groups[item.category] = groups[item.category] || []; groups[item.category].push(item); return groups }, {})`