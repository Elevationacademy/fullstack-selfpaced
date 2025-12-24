## For...Loop

This last way of doing for loops is similar to `for... in` - that is, it works with indexes; but we get more granular control of the loop. Check out this loop, which just prints the numbers 0, 1, 2...9:

  
```js
for(let i = 0; i < 10; i++){
  console.log(i)
}
```
  

Here we're also not bound to any array, but we do have to give the loop four things:

  

1.  A placeholder variable - in this case it's just `let i`
2.  A **starting index** - that's us setting `i` to 0
3.  An **end condition** - when does the loop end? In the above, it's when `i < 10` resolves to `false`
4.  An **iteration command** - here we've done `i++` - that means that each iteration should increase `i` by 1
	-   We can of course do something else, like `i+=10`

  

We say that this loop gives us more granular control, because we decide where it starts, where it ends, and by how much it increases (or decreases!) each time.

  

So if we want to print all the _even_ numbers between 80 and 100, we could do this:

  

```js
for(let i = 80; i < 100; i+=2){
  console.log(i)
}
```
  
Try it out for yourself and see!
