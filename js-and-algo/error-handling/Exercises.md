# Exercises

## Exercise 1

Create a JSON parser that handles invalid JSON gracefully.

- Take a string input (could be valid or invalid JSON)
- Use try-catch to handle JSON.parse() errors
- Return parsed object on success, or error message on failure
- Test with both valid and invalid JSON strings

```js
console.log(safeJsonParse('{"name": "John"}')); 
// Output: { name: "John" }

console.log(safeJsonParse('invalid json')); 
// Output: "Invalid JSON format"
```

## Exercise 2

Create a file reader function `readFileWithErrorHandling` that handles different file system errors.

- Use fs.readFile() with callback pattern
- Make sure to handle at least the following: existing file, non-existing file, directory instead of file
- Provide specific error messages for each error type
- Return success message with file size on successful read

Example:

```js
readFileWithErrorHandling('existing.txt', (result) => {
  console.log(result);
  // Success: "File read successfully. Size: 150 bytes"
  // Or error: "File not found: existing.txt"
});
```

