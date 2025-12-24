# For...Of

Now there are instances where we would like to use an index on each iteration, but in the example above this syntax would be friendlier:
 

```js
for(let company of companies){
  console.log(company)
}
```
  
Again, you should see all your companies printed out, one line after the other.

  

What's the difference? Here we don't get an index on each iteration - instead, **for...of gives us the element itself**! - Notice that we're not doing `companies[..]` anymore.

  

And where does it give us the element? Again, we're defining a variable using `let company`.

  

Talk about convenience.

  

With this knowledge, write a loop that runs through your companies and prints out "One day I will work at X" - where X is the name of each company. You'll have to use **concatenation** for this ;)

  

Try it out first before peeking [here](https://codepen.io/ElevationPen/pen/mYYYop?editors=0010)