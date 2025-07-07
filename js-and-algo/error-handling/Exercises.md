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

## Exercise 3

Create a command-line contact manager that focuses on error handling fundamentals.

- File operations: Load/save contacts to JSON file with error handling
- Input validation: Validate contact data with custom errors
- Command parsing: Handle invalid commands and arguments
  - supported commands are: `add`, `list` and `search` (see examples below)
- Error recovery: Handle corrupted files, missing data, write failures
- Work in a modular way. Separate logic from UI. Make functions as specific as possible (see below an example)

Example output:

```bash
$ node contacts.js add "John" "invalid-email" "555-1234"
✗ Error: Email must contain @ symbol

$ node contacts.js add "John Doe" "john@example.com" "555-123-4567"
Loading contacts from contacts.json...
✗ File not found - creating new contact list
✓ Contact added: John Doe
✓ Contacts saved to contacts.json

$ node contacts.js add "Jane Smith" "jane@example.com" "555-987-6543"
Loading contacts from contacts.json...
✓ Loaded 1 contacts
✓ Contact added: Jane Smith
✓ Contacts saved to contacts.json

$ node contacts.js list
Loading contacts from contacts.json...
✓ Loaded 2 contacts

=== All Contacts ===
1. John Doe - john@example.com - 555-123-4567
2. Jane Smith - jane@example.com - 555-987-6543

$ node contacts.js search "john"
Loading contacts from contacts.json...
✓ Loaded 2 contacts

=== Search Results for "john" ===
1. John Doe - john@example.com - 555-123-4567

$ node contacts.js search "bob"
Loading contacts from contacts.json...
✓ Loaded 2 contacts

=== Search Results for "bob" ===
No contacts found matching "bob"

$ node contacts.js add "Bad User" "john@example.com" "555-9999"
Loading contacts from contacts.json...
✓ Loaded 2 contacts
✗ Error: Contact with this email already exists

$ node contacts.js invalidcommand
✗ Error: Unknown command 'invalidcommand'
Usage: node contacts.js [add|list|search|delete] [arguments]

$ node contacts.js add
✗ Error: Missing arguments for add command
Usage: node contacts.js add "name" "email" "phone"
```

Example for modular structure:

```bash
contact-manager/
├── utils/
│   ├── validation.js         
│   └── fileUtils.js        
├── services/
│   └── contactService.js     
├── commands/
│   └── commandHandler.js
└── app.js
```