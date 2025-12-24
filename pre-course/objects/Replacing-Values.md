# Replacing Values

As with arrays, we can also replace the values in objects, given their keys. For example, in this object:

  

```js
let instructor = {
  age: 27
}
```
 
If we wanted to change `age`'s value to 28 we could do any of the following:

```js
instructor.age += 1
instructor["age"] += 1
instructor.age++
instructor["age"]++
instructor.age = 28
instructor["age"] = 28
```
  

We can do any of these because once you access an object's value, **it's basically a normal variable** - more about that in a second.

  

**Spot check:** modify the `human` object from before - give it a normal name

  

Console log `human` to make sure it worked.