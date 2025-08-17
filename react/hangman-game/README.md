# React Hangman Game

## Project Overview

You'll build a classic Hangman game using React fundamentals. The game will be bare-bones to focus on learning React concepts rather than styling.

Ultimately - once you're done with the fundamentals (before you design it) - your game will look something like [this](https://drive.google.com/file/d/1r_DxgRZ1I94o-tn29_CJT9526ZKDtKZu/view?usp=sharing).

### Game Rules
- There is a secret word with a hint
- User sees blank lines representing each letter
- User selects letters from the alphabet
- Correct letters fill in the blanks
- Wrong letters are crossed out
- Game ends when word is guessed or score reaches 0


![](./img/image.png ':size=50%')

## Component Architecture

Your app will need these components:

### Component Hierarchy
```
<App>
  <Score />
  <Solution />
  <Letters>
    <Letter></Letter>
    <Letter></Letter>
    ...
  </Letters>
  <EndGame /> (conditional)
</App>
```

### Component Responsibilities

- **App**: Main component, manages all state
- **Score**: Displays remaining guesses/points
- **Solution**: Shows word blanks and hint, fills in correct letters
- **Letters**: Container for all available letters
- **Letter**: Individual letter button
- **EndGame**: Win/lose screen (added later)

## Part 1: Basic Component Structure

### Step 1: Create Components

Create the following component files in your `components` folder:
- `Score.js`
- `Solution.js` 
- `Letters.js`
- `Letter.js`

### Step 2: Initial Component Implementation

**Score Component**
- Render a hard-coded number for now
- Will eventually track remaining guesses

**Solution Component** 
- Display 4 underscores using an array: `['_', '_', '_', '_']`
- Use `.map()` to render each underscore
- Display a hard-coded hint
- Don't load Letter component yet

**Letters Component**
- Render a simple string like "Available Letters"
- Load the Letter component
- Will eventually display A-Z

**Letter Component**
- Render a single hard-coded letter
- Will become dynamic later

**App Component**
- Import and render Score, Solution, and Letters components

### Expected Output
Your page should display:
- A number (score)
- Four underscores with a hint
- "Available Letters" text with a single letter

![](./img/part-1.png ':size=50%')

## Part 2: Adding Props and State

### Step 1: Set Up App State

In your App component, add the following state:

```javascript
// Letter tracking object
const [letterStatus, setLetterStatus] = useState(generateLetterStatuses());

// Game solution
const [solution, setSolution] = useState({
  word: "CALM", // or any 4-letter word
  hint: "Your ideal mood when coding"
});

// Game score
const [score, setScore] = useState(100);
```

### Step 2: Generate Letter Status Object

Create a `generateLetterStatuses` function that returns:
```javascript
{
  "A": false,
  "B": false,
  "C": false,
  // ... all letters A-Z set to false
}
```

**Hint**: Use ASCII character codes (65 = "A", 66 = "B", etc.)

### Step 3: Pass Props Down

- Pass `letterStatus` to both Letters and Solution components
- Pass `solution` to Solution component  
- Pass `score` to Score component

### Step 4: Update Components to Use Props

**Score Component**
- Display score from props instead of hard-coded number

**Solution Component**
- Display all letters of the word from props
- Use Letter component for each letter
- Display hint from props

**Letters Component**
- Use `Object.keys(letterStatus)` to get all letters
- Render each letter using Letter component

**Letter Component**
- Accept letter as prop
- Render in a `<span>` element

### Expected Output
Your page should show:
- Score: 100
- All letters of your secret word (temporarily visible)
- Hint text
- All letters A-Z displayed

## Part 3: Conditional Display

### Step 1: Solution Display Logic

In Solution component:
- Show letter if `letterStatus[letter]` is `true`
- Show underscore if `letterStatus[letter]` is `false`
- Pass the letter OR underscore down to Letter component

### Step 2: Letters Display Logic  

In Letters component:
- Always pass the letter to Letter component
- Pass different `className` based on letter status:
  - `className="selected"` if letter status is `true`
  - No className if letter status is `false`

### Step 3: Add CSS Styling

```css
.selected {
  text-decoration: line-through;
}
```

### Step 4: Test with Sample Data

Temporarily set this letterStatus in your App state for testing:
```javascript
{
  A: false, B: false, C: false, D: false, E: true,
  F: false, G: false, H: false, I: false, J: false,
  K: false, L: false, M: false, N: false, O: false,
  P: false, Q: false, R: false, S: true, T: false,
  U: false, V: false, W: false, X: false, Y: true, Z: false
}
```

With secret word "BYTES", you should see only Y, E, S in the solution, with the same letters crossed out in available letters.

![alt text](./img/part-3.png ':size=50%')


## Part 4: Adding Interactivity

### Step 1: Create selectLetter Function

In App component, create:
```javascript
const selectLetter = (letter) => {
  setLetterStatus(prev => ({
    ...prev,
    [letter]: true
  }));
  
  // Update score based on whether letter is in word
  if (solution.word.includes(letter)) {
    setScore(prev => prev + 5);
  } else {
    setScore(prev => prev - 20);
  }
};
```

### Step 2: Pass Function to Letter Component

- Pass `selectLetter` function down through Letters to Letter
- In Letter component, add `onClick` handler that calls `selectLetter(letter)`

### Step 3: Test Interactivity

- Click letters to see them get crossed out
- Letters in the secret word should appear in solution
- Score should update accordingly

## Part 5: Score Styling

Add conditional CSS classes based on score:
- 80+ points: `high-score` (green)
- 50-79 points: `medium-score` (yellow)  
- Below 50: `low-score` (red)

## Part 6: End Game Logic

### Step 1: Create EndGame Component

Display different messages based on game outcome:
- Win: "Congratulations!"
- Lose: "Game Over! The word was: [SECRET_WORD]"

### Step 2: Add Game End Detection

Game ends when:
- All letters in secret word have `letterStatus = true` (WIN)
- Score reaches 0 or below (LOSE)

### Step 3: Conditional Rendering

In App component, show EndGame instead of game components when game is over.

## Extension: Restart Functionality

Add a restart button in EndGame component that:
- Resets letterStatus to all false
- Picks a new word and hint
- Resets score to 100
- Returns to game view

## Final App Structure

Your completed app will demonstrate:
- Component composition and hierarchy
- Props passing and state management
- Conditional rendering
- Event handling
- State updates and re-rendering