# Setup

To run our JavaScript code, we will use **Node.js** directly within our IDE (like Antigravity or VS Code). This allows us to see the output of our code right in our terminal.

## Create a File

First, create a new file named `main.js`. You can do this by right-clicking in your file explorer and selecting "New File".

## Write Some Code

Add the following code to your `main.js` file:

```javascript
console.log("Hello, world!")
```

## Run Your Code

To execute the code, you need to use the **terminal**.

1.  Open the terminal in your IDE.
2.  Make sure you are in the same directory as your `main.js` file.
3.  Type the following command and press Enter:

```bash
node main.js
```

You should see the output `Hello, world!` printed directly in your terminal.

## Comments

Just like in other languages, you can write notes inside your JS code that the computer will ignore.

You can use `//` for single-line comments:

```javascript
console.log( ( (4 + 5) > 10) && !("a" == "b")) // we'll see what all this means soon
// This entire line is a comment
```

You can also comment bigger blocks of text by wrapping them with `/*` in the beginning, and `*/` in the end:

```javascript
/*
const greet = function() {
  console.log("hello, don't panic")
}
*/
```

Node.js will totally ignore all of that commented code.
