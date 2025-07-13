# Pair Exercise - Contact Manager

Today is your first major exercise in pairs! 🎉 

You were trained hard to get to this major milestone! 💪

Create a command-line contact manager that focuses on error handling fundamentals.

- File operations: Load/save contacts to JSON file with error handling
- Input validation: Validate contact data with custom errors
- Command parsing: Handle invalid commands and arguments
  - supported commands are: `add`, `delete`, `list`, `search` and `help` (see examples below)
- Error recovery: Handle corrupted files, missing data, write failures
- Work in a modular way. Separate logic from UI. Make functions as specific as possible (see below an example)
- Look and examine closely the below Example output. You can learn about the exact requirements from this example. 

## Example output

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

$ node contacts.js delete "jane@example.com"
Loading contacts from contacts.json...
✓ Loaded 2 contacts
✓ Contact deleted: Jane Smith
✓ Contacts saved to contacts.json

$ node contacts.js delete "nonexistent@example.com"
Loading contacts from contacts.json...
✓ Loaded 1 contacts
✗ Error: No contact found with email: nonexistent@example.com

$ node contacts.js add "Bad User" "john@example.com" "555-9999"
Loading contacts from contacts.json...
✓ Loaded 1 contacts
✗ Error: Contact with this email already exists

$ node contacts.js help
Usage: node contacts.js [command] [arguments]

Commands:
  add "name" "email" "phone"  - Add a new contact
  list                        - List all contacts
  search "query"              - Search contacts by name or email
  delete "email"              - Delete contact by email
  help                        - Show this help message

Examples:
  node contacts.js add "John Doe" "john@example.com" "555-123-4567"
  node contacts.js search "john"
  node contacts.js delete "john@example.com"

$ node contacts.js invalidcommand
✗ Error: Unknown command 'invalidcommand'
Usage: node contacts.js [add|list|search|delete|help] [arguments]

$ node contacts.js add
✗ Error: Missing arguments for add command
Usage: node contacts.js add "name" "email" "phone"
```

## Modular Structure Example

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