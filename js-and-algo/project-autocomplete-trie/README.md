# AutoComplete Trie Project

## Overview

Build a **console-based autocomplete application** using a Trie (prefix tree) data structure. Your app will suggest word completions based on user input, similar to how search engines work.

## What is a Trie?

A **Trie** (pronounced "try") is a tree-like data structure that stores strings efficiently:

- Each node represents a single character
- Root node is empty
- Each path from root to leaf forms a complete word
- Perfect for prefix-based searches

### Example Trie Structure
![](./img/trie.jpg ':size=50%')

As you can see, our root is a blank node - from it will link the first letters of every word of our dictionary. Any path followed down should consist of a word when the values are added together.

One of the most common applications for Tries are auto complete or predictive text programs, which is why we'll be using it to build our auto complete.

This is because the search for a word is quite quick - in a worst case scenario searching for a word has an **O(m)** time complexity - where m is the length of the word.

## AutoCompleteTrie Requirements

Create an `AutoCompleteTrie` class with:

### Properties
- `value`: Character stored in this node
- `children`: Object containing child nodes
- `endOfWord`: Boolean flag marking complete words

### Methods

#### `addWord(word)`
- Adds a word to the trie
- Creates nodes for each character
- Reuses existing paths when possible
- Sets `endOfWord = true` at the final character

**Example**: Adding "run" then "running"
- "running" reuses existing "r-u-n" path
- Only creates new nodes for "n-i-n-g"

#### `findWord(word)`
- Returns `true` if word exists in trie
- Returns `false` if word doesn't exist

#### `predictWords(prefix)`
- Takes a word prefix (e.g., "ca")
- Returns array of all possible completions
- Example: prefix "ca" might return ["cat", "car", "card", "care"]

### Helper Methods (Recommended)

#### `_getRemainingTree(prefix, node)`
- Navigates to the last node of the given prefix
- Returns the node where the prefix ends
- Used by `predictWords` to find starting point

#### `_allWordsHelper(prefix, node, allWords)`
- Recursively collects all words from a given node
- Builds complete words by concatenating characters
- Adds words to `allWords` array when `endOfWord = true`

## Console Interface Requirements

Your application should:

1. **Display a welcome message**
2. **Show available commands**:
   - `add <word>` - Add a word to the dictionary
   - `find <word>` - Check if word exists
   - `complete <prefix>` - Show all completions for prefix
   - `help` - Show commands
   - `exit` - Quit the application
3. **Handle user input in a loop**
4. **Provide clear feedback for each operation**

### Example Console Session
```
=== AutoComplete Trie Console ===
Type 'help' for commands

> add cat
✓ Added 'cat' to dictionary

> add car
✓ Added 'car' to dictionary

> add card
✓ Added 'card' to dictionary

> complete ca
Suggestions for 'ca': cat, car, card

> find cat
✓ 'cat' exists in dictionary

> find dog
✗ 'dog' not found in dictionary

> help
Commands:
  add <word>      - Add word to dictionary
  find <word>     - Check if word exists
  complete <prefix> - Get completions
  help           - Show this message
  exit           - Quit program

> exit
Goodbye!
```

## Other Requirements

- Create full unit testing for the `AutoCompleteTrie` class
- Start with creating 3 tests for each method on your own
- Complete the unit testing using AI
- GitHub - Commit a lot!! we want to see your progress with your commits

## Suggested Flow

1. Create the `AutoCompleteTrie` class with basic structure
1. Implement `addWord` method first
1. Add unit testing for `addWord`
1. Implement `findWord` method
1. Add unit testing for `findWord`
1. Implement the helper methods
1. Add unit testing for helper methods
1. Implement `predictWords` method
1. Add unit testing for `predictWords` 
1. Add unit testing for the whole flow
1. Build the console interface
1. Test with various scenarios

## Tips

- Start simple - get basic functionality working first
- Use `console.log()` to debug your trie structure
- Test each method individually before building the console interface
- Remember that JavaScript objects work well for the `children` property
- Handle case sensitivity consistently (consider converting to lowercase)
