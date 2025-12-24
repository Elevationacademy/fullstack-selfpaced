# Exercises

## Exercise 1

Create two arrays of the same length. One with names, and one with ages.

  

Using **one** `for` loop, print out "X is Y years old" for each pair.

  

**Hint**: since you want to access items from different arrays at the same **index**... which `for` loop should you use? Also, you'll be **concatenating** again.

-----------

## Exercise 2

Create an array of numbers.

  

Write a loop that adds up all the numbers in the array.

  

Print out the final sum.

  

**Hint 1:** start with a variable `let sum = 0`  **before** your loop.

**Hint 2:** remember that you can add to a number using `+=`


## Exercise 3

Using the same array of numbers above, write some code that calculates the average of the numbers.


## Exercise 4

Create an empty array called `nums`.

  

Write a loop that adds the numbers 1, 2, 3,..., 100 to the array

Think about which loop you want to use.


## Exercise 5

Loop through the array `nums` from the previous exercise, and print (console log) all the _odd_ numbers. Remember our friend modulo `%?`


## Exercise 6

Using this array:

  
```js
let nums = [773, 414, 213, 374, 434, 700, 506, 495, 852, 585, 271, 198, 689, 248, 708, 197, 96, 260, 921, 834, 258, 662, 501, 632, 715, 503, 538, 289, 596, 381, 817, 280, 968, 877, 431, 146, 491, 724, 83, 841, 174, 21, 460, 25, 785, 539, 291, 404, 903, 278, 159, 229, 216, 683, 84, 87, 879, 406, 661, 537, 890, 394, 382, 477, 271, 373, 82, 104, 709, 723, 333, 958, 95, 983, 732, 917, 324, 785, 754, 23, 659, 551, 408, 442, 766, 242, 611, 846, 802, 866, 817, 848, 227, 349, 243, 837, 21, 954, 146, 11]
```
  

Use a loop to find the index of the number 709. You should find it to be 68.

## Exercise 7

Given the following setup:

  
```js
const names = ["Ashley", "Donovan", "Lucas"]
const ages = [23, 47, 18]
const people = []
```
  

Write a loop that populates (adds to) people with objects that look like this:

  

{name: "Ashley", age: 23} - for each pair in names and ages

  

Ultimately, when you console log people, it should look like this:

  
```js
[
  {name: "Ashley", age: 23},
  {name: "Donovan", age: 47},
  {name: "Lucas", age: 18}
]
```

## Exercise 8

Based off the `people` array from before, write a loop that prints out "Ashley is 23 years old", "Donovan is 47 years old", etc.

  

Again, consider which loop is most appropriate.

  

Note that this is _different_ from Exercise 1 ;)

## Exercise 9

**==≡==** The following exercises are a little more challenging - but this is a good chance to practice your programmer's mind. **==≡==**

  

Given this array:

  
```js
const posts = [
  {id: 1, text: "Love this product"},
  {id: 2, text: "This is the worst. DON'T BUY!"},
  {id: 3, text: "So glad I found this. Bought four already!"}
]
```
  

Write some code that removes the post with an `id` of 2 from the `posts` array. Can't have any negative reviews of our product!

  

Obviously, do not do `posts.splice(1, 1)` - you have to _find_ the post to remove! (Of course, you _will_ use `splice` - just not hard coded!)

## Exercise 10

Given this array:

  
```js
const posts = [
  {
    id: 1, 
    text: "Love this product",
    comments: []
  },
  { 
    id: 2, 
    text: "This is the worst. DON'T BUY!", 
    comments: [
                {id: 1, text: "Idiot has no idea"}, 
                {id: 2, text:"Fool!"}, 
                {id: 3, text: "I agree!"}
              ]
   },
   {
    id: 3, 
    text: "So glad I found this. Bought four already!",
    comments: []
   }
]
```
  

You are given `2` as the ID of a _post_. Write some code that finds the _comment_ with an ID of `3` (inside of a _post_ with an ID of `2`), and remove just that one comment.

## Extension

There is something called [Object.keys](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys) - read about this, and then do the following exercise:

  

Given the object below:

  
```js
const dictionary = {
  "A": ["Aardvark", "Abacus", "Actually", "Atomic"],
  "B": ["Banana", "Bonkers", "Brain", "Bump"],
  "C": ["Callous", "Chain", "Coil", "Czech"]
}
```
  

Write some code that prints out the following:

  
```js
Words that begin with  A:
    Aardvark
    Abacus
    Actually
    Atomic
Words that begin with  B:
    Banana
    Bonkers
    Brain
    Bump
Words that begin with  C:
    Callous
    Chain
    Coil
    Czech
```
  

**Hint 1:** You will have to use what's known as a **double for loop** - that means a for loop _within_ a for loop.

  

**Hint 2:** Start small; only print out "Words that begin with..." at first, then keep going

  

----------

  

### **DONE**
```js
while(!done){

  while(headHurts){
    // massage your head
  }

  // keep going for another 20 minutes
}

// celebrate
```
