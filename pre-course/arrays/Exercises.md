# Exercises

We'll get to some more exercises with arrays at the end of the lesson, but try this out for now:

  

You are a Doctor who studies genetics, and you have some data about a patient's genes. The following array is a list of one strand of the patient's DNA, which you know is problematic:

  
```js
const genes = ["ACADM", "GLMN", "RLF", "AZIN2", "CRYZ"]
```
  

You have a tool called CRUD which you can use to manipulate the above array. Here are your instructions for healing your patient:

  

Create a new strand of genes (a new array) based off the `genes` strand above. You **cannot create new genes***, only copy the existing ones above.

  

That means that if you want to access the `"GLMN"` gene, you must access `genes[1]`, for example.

###### *Except for "FXT", explained below

  

The new strand should be built like this:

  

-   The first two genes should be the same as those in `genes`
-   Replace `"RLF"` with `"CRYZ"` and `"CRYZ"` with `"RLF"` (swap their places)
-   Remove `"AZIN2"` from where it is, and insert two of these `"AZIN2"`s at the end of the strand
-   Once you've done all of the above, add the gene `"FXT"` to the _beginning_ of the strand
	-   The `"FXT"` gene is unstable so you may only add it _once the other genes are in place!_

  

**Hint:** Start with an empty array, and then use the methods you learned so far to complete this procedure.

  

Good luck, the patient is waiting.

  

If you've done it right, your new array should look like this:

  
```js
[ 'FXT', 'ACADM', 'GLMN', 'CRYZ', 'RLF', 'AZIN2', 'AZIN2' ]
```
