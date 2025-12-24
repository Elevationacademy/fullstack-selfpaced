# Operators

Operators are used to assign values, perform mathematical operations, compare values, and more. You've already seen two operators in action: `=` and `+` 


## Comparison Operators

When we want to compare equality, we have a few choices:
  
```js
console.log(3 < 5) // will output true
console.log(3 > 5) // will output false
console.log(2 >= 2) // will output true
console.log(1 <= -1) // will output  false
console.log("this string" == "that string") // will output false
``` 

In the order from above: less than, greater than, greater or equal to, less or equal to, equals.  

Notice that **to compare equality we use two equal signs** - not one! We use one for _assignment_.  

Also, when we compare strings, JS compares them _with_ case-sensitivity; "Cat" is **different** from "cat".  

We can also compare strings using the greater/less symbols - but that involves [ASCII values](http://www.asciitable.com/), which we won't go into right now.  

There is another way to check for equality, and that is - no joke - the triple equals sign: `===`  

Check this out:

```js
console.log(1 == "1")// prints true
console.log(1 === "1")// prints false 
``` 

**When we check equality with two equal signs JavaScript first converts the two values to a common type** behind the scenes - in the above case, it will convert `"1"`to `1`, and therefore it will be equal.  

However when **we use the triple equals, JavaScript checks for equality in both value and type**, without converting anything. Hence `1` does not equal `"1"`, because the former is a **number** and the latter a **string.**
  

Sometimes we want to be more strict with our checks, and we'll opt for the triple-equal signs. This is not a hard-and-fast rule, though; just good practice. Here's [a good resource](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness) on equality comparison in JavaScript if you're curious.


## Mathematical Operators
  

We have our four standard math operations: plus, minus, multiply, divide. In JS (and most languages) the symbols are `+`, `-`, `*` ,`/`. 

Yes, multiplication is signified with an asterisk, and division with a forward slash.  

For the most part (with concatenation being the main exception), we can only use these mathematical operators with numbers:

```js
console.log(27 + 15)
console.log(81 / 9)
console.log(3.14 * 10)
```  

JS knows how to handle all of these. Of course, we can also do the same with variables:


```js
const num1 = 17
const num2 = 3
console.log(num1 + num2) // will print 20
```
  

Note that we can use parentheses the same way we use them in normal mathematics:
  
```js
console.log( (3 + 5) * 2 ) // same as 8*2, which will print 16
```  

**Word of warning**: if you try to do something illegal like the following:


```js
let num
console.log(3 + num)
```  

Then the console will log a special expressions called **`NaN`** **- short for Not a Number**.

This happens because we didn't initialize `num` with some number, and JS doesn't know how to do `3 + undefined` - it doesn't make sense. 


## Modulo

**Modulo** is a special operator that gives us the **remainder** of a division operation. We use the `%` symbol for modulo:

```js
console.log(14 % 5) // will print 4
```
The above outputs 4 because the number 5 can go into 14 twice, with 4 left over.

This is particularly useful when we want to find even or odd numbers:  

```js
const x = 41223
console.log(x % 2 == 0)
```  

The above will print `false` because 41,223 (which we store in `x`) divided by two does _not_ have a remainder of 0. Because all even numbers are divisible by 2, then we know that any number divided by 2 that doesn't have a remainder of 0 must be an odd number.  

Hence **using** **`% 2`** **we can always know whether numbers are even or false** - this will be useful in later lessons, and in life. 

## Truthy/Falsey  

Take this example that "resolves to true":

```js
console.log(3 < 5)
``` 

When something **resolves to true it means that ultimately its value is the boolean** **`true`** - for instance, `3 < 5` resolves to `true`; it is also known as a **truthy expression**.  

Other examples of "truthy expressions" include:

```js
23 == "23"
41 === 41
"this string" == "this string"
972 % 2 == 0
```

All of those are ultimately, as far as JavaScript is concerned, just `true`.  

There are also, of course, "falsey expressions". **Falsey expressions are those that JavaScript ultimately converts to false**.  

The following are simple examples of `falsey` expressions:

```js
23 == 22
"home" == "house"
```  

There are also other `falsey` expressions in JS, such as:  

-   `0` - yes, JavasScript sees the number zero as falsey if it's used as a number
-   `""` or `''` - an empty string value is also falsey
-   `undefined`
-   `NaN`
-   null - this is a special expression that we'll talk more about later, but it's a way of saying "no value" that is different from `undefined`
  

If you console log any of the above by themselves, you'll see exactly what you put in: 


```js
console.log(NaN) // prints NaN
console.log(null) // prints null
//etc..
```

But later we'll see how we can use these expressions in **conditional statements**.  

## Logical Operators
  

We have three main operators to help us control flow in JavaScript:  

-   `&&` - the **and** operator - both sides must resolve to `true`
-   `||` - the **or** operator - at least one side must resolve to `true`
-   `!` - the **not** operator - flips a boolean from `true` to `false` or the other way around
  

Let's look at the `&&` for a second:

```js
console.log(true && false)
```  

The above will print `false` - that is because the right side of the `&&` does not resolve to `true` - obviously since it is just false - and `&&` dictates that **both** sides must resolve to `true`.  

So when we use logical operators like `&&` and `||`, that's what we mean when we say "resolve to true". Let's look at a few more examples:

```js
console.log((3 < 2) ||  (1 > 0)) // prints true because the right side resolves to true, even though the left side resolves to false

console.log(("a" == "a") && (32 === "32")) // prints false because the right side resolves to false

console.log(!(10 > 5)) // prints false, because the 10 IS greater than 5 (true), but the ! flips the true to a false
```  

If the last one is a little confusing, break it down:  

```js
console.log( !(10 > 5) )
// is the same as...
console.log( !(true) )
//is the same as...
console.log(!true)
//which resolves to false, since the ! flips booleans
```

Smells like high school math ~

We can also combine the `!` and `=`, by the way, to do something like this:

```js
console.log(3 != 5)
```  

We read the above as "3 not equal five" - which is true, hence the above will print `true`

What do you think "51" `!== 52` will resolve to?  

Test out what you think the answer is.  

----------

There is a nice trick you can do with the `||` operator when assigning variables. Check out this code:

```js
let startPosition
let newPosition = (startPosition || 0) + 10

console.log(newPosition) //prints 10
```

In other words, **we can use the** **`||`** **(or) operator to assign a value _conditionally_**. This is useful when we have some "starter" value that might or might not be initialized.

Notice that the above would not work without the `... || 0` because you cannot add `10` to `startPosition` while it's `undefined`

----------

**++**

Say we have a variable which represents the amount of goals we've accomplished, and at first it's 3. We're very proud of ourselves, but then we go and achieve another goal. Now we have to reset our variable to be 4, like this:

```js
let numGoalsAchieved = 3
//achieve another goal
numGoalsAchieved = 4
```

That's a bit problematic because then we always have to remember the number of goals. We can, instead, just add 1 to the variable, like this:

```js
let numGoalsAchieved = 3
//achieve another goal
numGoalsAchieved = numGoalsAchieved + 1
```

What the above does is still **overwrite** the variable, but it says "`numGoalsAchieved` is now equal to itself plus 1" - which is exactly what we want. The new value of the variable will still be 4.

Of course, we can change that 1 to any number - try it out and test the new value of `numGoalsAchieved` with a console log to see for yourself.

To save ourselves the hassle of writing the same variable again, we can also write the above like this:
  
```js
let numGoalsAchieved = 3
//achieve another goal
numGoalsAchieved += 1
```			
  
Very much like the short-hand concatenation we learned earlier in this lesson!

Again, the `+=` expression is saying "you are equal to yourself plus..." 1 in this case, but again we could do it with any number - try this out too.

Finally, we can reduce this even more to the friendliest of all:

```js
let numGoalsAchieved = 3
//achieve another goal
numGoalsAchieved++
```
  
The above has the exact same effect as `+=1` - except it's a cool shortcut that most languages, including JS, allow.

We read it as "plus plus", it only works with numbers, and it's saying "add one to yourself".

 In general when we add to the value of a number, it's called **incrementing the value**, and `++` specifically always _increments by 1._

That is the catch: `++` only ever adds **one**, one at a time. So if we want to add 3 achievements using the `++` syntax, we would have to do this:

```js
let numGoalsAchieved = 3
//achieve another goal
numGoalsAchieved++
numGoalsAchieved++
numGoalsAchieved++
```
  
Of course, in this case it's simpler to just write `numGoalsAchieved += 3`

Keep these in mind. They're all nice.
