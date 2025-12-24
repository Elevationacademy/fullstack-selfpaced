# Reference Types

As opposed to **strings**, **numbers**, and **booleans** which are all primitive types, **arrays and objects are reference types**.

Check this code out:

```js
let numbers = [1, 2, 3]
let nums = numbers

nums[0] = 50
```  

No big deal here - now when we print `nums`, we should see `[50, 2, 3]` - right?

And when we `console.log(numbers)`?

  
We will _also_ see `[50, 2, 3]`! Test it out yourself, it's incredible.

  
The reason this happens is that **JS does not create a new space in memory for reference types. Instead, it references an existing space, if possible.**

  
Think about it this way: we defined and initialized a `numbers` array with certain values.

Then we defined a `nums` array _with the value_ _`numbers`__!_
  

JS now says "listen here buddy, arrays can become very long, and I don't want to waste memory on the exact same data!"

  
So instead of creating _new_ memory, JS will just say "hey, I'll just associate between `nums` and `numbers` - whatever you do to one I'll do to the other."
  

Not sure why JS speaks in gold. But there you go.

  

The same applies to objects, which are also reference types. Try something like this out for yourself:

  
```js
let person = {
  firstName: "Dopple",
  lastName: "Ganger"
}

let p = person
p.firstName= "Chappy"

console.log(p)
console.log(person)
```