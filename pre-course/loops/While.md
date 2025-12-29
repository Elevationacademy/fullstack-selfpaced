# While

As for `while` loops, the syntax is even simpler:
```js
while(someCondition){
  //do something
}
``` 

In this case we're not telling the loop to run over a certain array, but rather **run until a certain condition is met**.

The condition can be anything from testing the length of an array, or using a counter - so long as it _resolves to a boolean_.

  And remember, the condition **has** to break somehow - otherwise the loop will run forever. For instance:
```js
let timer = 0;

while(timer < 10){
  console.log(timer);
}
```
**↑ Do not run that code! ↑**

That code above is saying "while timer is less than 10, console log the timer."
  
Sounds good, but the value of `timer` is 0 - and it never changes! Therefore this loop will run forever (and freeze/crash your terminal if you try it)

Instead, to **break the loop**, the code should look like this:

```js
let timer = 0;

while(timer < 10){
  console.log(timer);
  timer++;
}
```  

Now we've added Line 5, which **increments** our timer by 1 with each iteration.

So the flow is like this:
  
-   `timer` starts off at 0
-   Check condition: is `timer` less than 10?
-   Yes, 0 is less than 10
-   Enter the `while` block
-   Console log the `timer`, increment the `timer`
-   timer is now 1
-   Check condition: is `timer` less than 10?
-   Yes, 1 is less than 10
-   Enter the `while` block
-   Console log the `timer`, increment the `timer`
-   `timer` is now 2
-   Check condition...etc
  

Once the condition is _not_ met - in this case, `timer` is not less than 10 - then the `while` ends, and the next line of code (if any) executes.

Remember, **the expression inside the** **while****'s parentheses** **`( )`** **is just a small** **`if`** **statement** - and the condition must resolve to a boolean!

----------

Given the `companies` array from before, can you figure out what this does?

```js
while(companies.length > 0){
    companies.splice(0, 1)
}
```  

Make sure you understand the above. Ask a friend if you don't get it. Then ask the instructor if you're still stumped. But make sure you get it!
<details><summary>
  Click here to reveal the answer.
</summary>

The condition says: so long as the `length` of `companies` is greater than 0, keep **splicing** - remember that `splice` removes item(s) from an array. In the above, we're splicing the first, the **0th**, index each time.
</details>

----
Therefore, eventually, we will have spliced all of the elements, and `company`'s length will be 0, and so the condition `companies.length > 0` will resolve to `false`, which breaks the loop!
