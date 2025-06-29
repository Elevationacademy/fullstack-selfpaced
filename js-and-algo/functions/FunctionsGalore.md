
# Functions Galore (aka Separation of Concerns)

Let’s say we have the following data about some people:

```js
const people_info = [
  {
    name: "guido",
    profession: "bungalow builder",
    age: 17,
    country: "canaland",
    city: "sydurn",
    catchphrase: "what a piece of wood!"
  },
  {
    name: "petra",
    profession: "jet plane mechanic",
    age: 31,
    country: "greenmark",
    city: "bostork",
    catchphrase: "that's my engine, bub"
  },
  {
    name: "damian",
    profession: "nursery assistant",
    age: 72,
    country: "zimbia",
    city: "bekyo",
    catchphrase: "with great responsibility comes great power"
  }
]
```

Now we want to create a **summary** for each person, but with a few rules.

---

## Summary Rules

1. **Capitalize all proper nouns**  
   (Everything except the age is a proper noun: name, profession, city, country, catchphrase)

2. **Combine city and country**  
   Write them together with a comma: `"City, Country"`

3. **Format the age**:
   - If the person is under 21 → `"Underage"`
   - If the person is older than 55 → `"55+"`
   - Otherwise → show the age as-is

4. **Format the catchphrase**:
   - Put it in **quotes**
   - Capitalize the **first letter**

## Goal

We want to write a function called `getSummary(person)` that returns a string like this:

> `"Guido is an Underage Bungalow Builder from Sydurn, Canaland. Guido loves to say "What a piece of wood!"."`

---

## Step-by-Step Approach

If we put all the logic inside `getSummary`, it will get messy fast.

So instead, we’ll **break the job into smaller functions**, each doing one specific task.

This idea is called **Separation of Concerns**.

## Helper Function: Capitalize

Let's start with a function that capitalizes the first letter of a word:

```js
const capitalize = function(str) {
  let capitalizedStr = ""
  capitalizedStr += str[0].toUpperCase()      // first letter, capitalized
  capitalizedStr += str.slice(1)              // rest of the string
  return capitalizedStr
}
```

You can try it like this:

```js
console.log(capitalize("hello"))  // "Hello"
```

---

## Building the Main Function

Now let’s use this in our `getSummary` function.

```js
const getSummary = function(person){
  let summary = ""
  summary += capitalize(person.name)
  summary += ` is ${getAge(person.age)} ` //Yes - you can put a function call inside the tick quotes!
  summary += //call function for profession
  summary += //call function for country + city
  summary += //call function for catchphrase
  return summary
}
```
Each part calls a helper function — that’s the power of breaking things down.


## Example Outputs

```js
console.log(getSummary(people_info[0]))
```

> `"Guido is an Underage Bungalow Builder from Sydurn, Canaland. Guido loves to say "What a piece of wood!"."`

```js
console.log(getSummary(people_info[1]))
```

> `"Petra is 31 year old Jet Plane Mechanic from Bostork, Greenmark. Petra loves to say "That's my engine, bub"."`

```js
console.log(getSummary(people_info[2]))
```

> `"Damian is a 55+ Nursery Assistant from Bekyo, Zimbia. Damian loves to say "With great responsibility comes great power"."`

---

## Why Write Code This Way?

Because it's:

✅ Easier to read  
✅ Easier to test  
✅ Easier to reuse

This is why we use **Separation of Concerns**: each function should do **just one thing**.
