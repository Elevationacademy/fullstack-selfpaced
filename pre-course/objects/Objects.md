# Objects

Let's look at a simple example:

```js
let person = {
  name: "Mariah",
  occupation: "Gangster"
}
```

The syntax of an object, as you can see, is straightforward:

-   Declare a variable
-   Give it a name
-   Wrap it in **curly braces**
-   Add **key**-**value** pairs
-   Keys don't have to have quotes around them (unless you have special characters)
-   Values do (if they are strings)

In the above example, our **keys** are `name` and `occupation`, and their corresponding values are `Mariah` and `Gangster`

So if we wanted to access `person`'s `occupation`, we would do:
```js
console.log(person.occupation) // prints "Gangster"
``` 

That's nice.

Objects help us store information that should be together in a coherent way. Imagine we had to use an **array** to store this information. we would have something like this:
```js
const names = ["Mariah", "James", "Luke"]
const occupations = ["Gangster", "Preacher", "Hero"]
```
Let's say we wanted to print "Mariah is a Gangster". With the arrays, we'd have to do this:
```js
console.log(names[0] + " is a " + occupations[0])
```
  
-   We have to access two separate arrays
-   We have to make sure that all of the elements are in matching indexes
-   The code is bloated by brackets
-   If someone else comes and reads this code, they have no idea what is in `names[0]` or `occupations[0]`

Not bueno. However with this object:
```js
let person = {
  name: "Mariah",
  occupation: "Gangster"
}
```
We could just do the following:
```js
console.log(person.name + " is a " + person.occupation)
```  

This is more readable, and we don't have to worry about the position of anything! **Objects have no order** - they just have keys and values.

----------


Note that the **value** of any key can be _anything_. Strings, numbers, booleans, _arrays_, _other objects_, even functions*!

###### *We'll go over this in another lesson

Let's look at an object with an array inside:
```js
const bag = {
  weight: 10,
  owner: "Larissa",
  items: ["Pen", "Bottle", "Book"]
}
```

If we want to access all the items in the array, simple:

```js
console.log(bag.items) // prints ["Pen", "Bottle", "Book"]
```  

Now say we wanted to get the bottle:

```js
console.log(bag.items[1]) // "Bottle"
```
By accessing `bag.items`, it's as if we now have an array with all of the items. Therefore, we can access it the same way we access arrays - with an index!

We'll see a more in depth example of this later in the lesson.