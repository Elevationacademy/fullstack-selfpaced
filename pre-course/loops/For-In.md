# For...In

To learn basic syntax, let's say we have our good ol' `companies` array again:
```js
let companies = ["Tesla", "Amazon", "Google", "Microsoft"]
```
  

Now say we want to console log all of them. We could do this...

```js
console.log(companies[0])
console.log(companies[1])
///...
```
  

But that's no fun; copy+pasting is a bummer. Instead, we can use `for...in`, like this:

```js
for(let companyIndex in companies){
  console.log(companies[companyIndex])
}
```
  

Try that out and see that it produces the exact same result.

  
Now let's talk about the syntax here. We've got three **reserved words** - these are words that JS reserves for itself, and have a special meaning in the language.

Above, the words are:

-   `for` - this starts the loop
-   `let` - we know this one already
-   `in` - let's talk about this

We already know the `arrayName[index]` syntax - and that's exactly what's going on here.

What `for...in` does for us is it **gives us each index, in order, of the array we're looping**.

Where does it give us the index? Inside `companyIndex`!

The `let companyIndex` is basically us saying "_use this variable to hold some value for each_ **_iteration_** _of the loop_" - that variable is each index, one after the other.

Try this out:
```js
for(let companyIndex in companies){
  console.log(companyIndex)
}
```
  

Write that out, then look at your console, and you'll see all the indexes of the `companies` array! Since `companies` has 4 items, you should see 0, 1, 2, 3.

  In other words, we can say that **the loop generates an** **`index`** **for each item** **`in`** **our** **`companies`** **array.**

  Bam.