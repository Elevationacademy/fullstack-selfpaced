# Dot Notation vs. Bracket Notation

There are a couple of way to **access object properties** (properties are the same as keys):

What we saw up to now is called **dot notation** - that is using the variable `name`, `person`, a dot, and then the property we want.

So to get "Mariah" we just do `person.name`

The other way is similar, but with different syntax: `person["name"]`

The result is exactly the same, but don't worry too much about which to use when right now.

----------

Whether you use dot or bracket notation, if you try to access a key that doesn't exist in the object, then you will get `undefined`:
```js
const table = {
  numLegs: 4,
  color: "Wood brown"
}

console.log(table.yearPurchased) // prints undefined
console.log(table["yearPurchased"]) // still undefined
``` 

This is similar to trying to access an index that doesn't exist in an array - it's not yet defined!

----------

#### **ADDING VALUES**
To add values to an existing object, there is no special method like with arrays. See this example:
```js
const animalCounts = {
  lion: 2,
  zebra: 11,
  ostrich: 1,
  tortoise: 4
}

//Suddenly the zoo acquired two dozen eagles

animalCounts.eagle = 24
//or
animalCounts["eagle"] = 24
```
The reason we must have quotes in the second version is because otherwise JS would think that `eagles` is a variable, which it isn't. So this is one case where bracket notation is required.

Generally speaking, **we don't usually add key-values to an existing object**.

We modify them all the time, but usually we'll set an object up with whatever properties it needs, and that's it.

This makes sense, because usually objects represent certain entities in our application (like a User), and those entities don't usually change.

For instance, a User will always have a name, email, and birthday - but if we decided that's all the data we want about a user, then that's usually it.

----------

**Spot check:** given the following code:
```js
const human = {
    age: 0
}

const babyNameKey = "name"
const babyNameValue = "Goojibear"
```  

Write some code that gives human the key-value pair of `name: "Goojibear"`, _using the variables above_.


You can see the solution [here](https://codepen.io/ElevationPen/pen/XwwQWz?editors=0010) .