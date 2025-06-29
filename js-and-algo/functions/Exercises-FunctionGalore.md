
# Exercises: Functions Galore

## Exercise 1

1. Finish writing the helper functions (`getAge`, `capitalizeProfession`, `capitalizeCatchphrase`, etc.).
2. Write a loop that calls `getSummary` for each person in `people_info`.

---

## Exercise 2

You are given the following setup:

```js
const story = "In the beginning there was light. Then there were wolves. Finally there was a big fire. Ultimately, Shelob the wolf-master put out the fire with her feet. But until then, the fire caused one heck of a lot of damage."
const specialChars = [",", ".", "'", '"', "?", "!", ";"]
const wordCounts = {}
```

Write a program that:

- Counts each unique word in the `story`  
- Ignores case (make everything lowercase)  
- Removes special characters  
- Stores the result in the `wordCounts` object

### Output Example

After running your code, `console.log(wordCounts)` should return something like:

```js
{
  in: 1,
  the: 4,
  beginning: 1,
  there: 3,
  was: 2,
  light: 1,
  '': 6,
  then: 2,
  were: 1,
  wolves: 1,
  finally: 1,
  a: 2,
  big: 1,
  fire: 3,
  ultimately: 1,
  shelob: 1,
  'wolf-master': 1,
  put: 1,
  out: 1,
  with: 1,
  her: 1,
  feet: 1,
  but: 1,
  until: 1,
  caused: 1,
  one: 1,
  heck: 1,
  of: 2,
  lot: 1,
  damage: 1
}
```

### Requirements

- Use at least **3 functions**, for example:
  - `cleanText(sentence)` → returns an array of cleaned, lowercase words
  - `addToCounter(word)` → updates the `wordCounts` object
  - `countWords(sentence)` → main function that coordinates everything

### Guidelines & Hints

- Plan your functions first!
- Work step-by-step:
  - Write and test each helper function separately.
  - Then connect them together.
- Use loops!
- To remove characters:  
  `str = str.split(",").join(" ")`  
  You can do this for each character in `specialChars`.
- To split text into words:  
  `"this is a sentence".split(" ")` → `["this", "is", "a", "sentence"]`

---

## Stuck? Here's a Hint

<details><summary>Click to reveal a detailed hint</summary>

- Create a `countWords(sentence)` function.
- Inside it:
  - Call `cleanText(sentence)` → returns an array of cleaned words
  - Loop through the array and call `addToCounter(word)` for each word

- `addToCounter(word)` checks if the word exists in `wordCounts`:
  - If yes, increment it
  - If not, set it to 1

Need structure? Use this [starter code](https://codepen.io/ElevationPen/pen/NZRqqg?editors=0010)

</details>

---

✅ **Done? Awesome!**  
Keep practicing — organizing your code into small, testable functions is a superpower.
