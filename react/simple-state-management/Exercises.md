# Exercises

Exercises here practice the use of Context to replace prop drilling and useReducer as an alternative for useState.

## Exercise 1

You have a shopping cart with useState that's getting complex. Migrate it to useReducer.

### Starting Code (useState):
```javascript
function ShoppingCart() {
  const [items, setItems] = useState([]);
  const [total, setTotal] = useState(0);
  const [itemCount, setItemCount] = useState(0);

  const addItem = (product) => {
    const newItems = [...items, { ...product, id: Date.now() }];
    setItems(newItems);
    setTotal(total + product.price);
    setItemCount(itemCount + 1);
  };

  const removeItem = (id) => {
    const newItems = items.filter(item => item.id !== id);
    const removedItem = items.find(item => item.id === id);
    setItems(newItems);
    setTotal(total - removedItem.price);
    setItemCount(itemCount - 1);
  };

  return (
    <div>
      <h2>Shopping Cart ({itemCount} items) - Total: ${total}</h2>
      {/* Render items */}
    </div>
  );
}
```
### Your Task:
1. Convert the shopping cart to use useReducer
1. Create actions: ADD_ITEM, REMOVE_ITEM, CLEAR_CART
1. Calculate total and itemCount in the reducer
1. Handle edge cases (removing non-existent items)

### Expected Actions:
```javascript
// dispatch({ type: 'ADD_ITEM', data: { name: 'Laptop', price: 999 } })
// dispatch({ type: 'REMOVE_ITEM', data: itemId })
// dispatch({ type: 'CLEAR_CART' })
```

---

## Exercise 2

You have a theme that needs to be accessed by deeply nested components across your app. Use React Context to eliminate prop drilling in a theme system

### Starting Code (Prop Drilling):
```javascript
function App() {
  const [theme, setTheme] = useState('light');
  const [fontSize, setFontSize] = useState('medium');
  
  return <Layout theme={theme} setTheme={setTheme} fontSize={fontSize} setFontSize={setFontSize} />;
}

function Layout({ theme, setTheme, fontSize, setFontSize }) {
  const bgColor = theme === 'light' ? '#ffffff' : '#1a1a1a';
  const color = theme === 'light' ? '#000000' : '#ffffff';
  
  return (
    <div style={{ backgroundColor: bgColor, color, minHeight: '100vh', padding: '20px' }}>
      <Header theme={theme} setTheme={setTheme} fontSize={fontSize} setFontSize={setFontSize} />
      <Content theme={theme} fontSize={fontSize} />
    </div>
  );
}

function Header({ theme, setTheme, fontSize, setFontSize }) {
  return (
    <header style={{ marginBottom: '20px' }}>
      <Navigation theme={theme} fontSize={fontSize} />
      <Controls theme={theme} setTheme={setTheme} fontSize={fontSize} setFontSize={setFontSize} />
    </header>
  );
}

function Navigation({ theme, fontSize }) {
  const size = fontSize === 'small' ? '14px' : fontSize === 'large' ? '20px' : '16px';
  
  return (
    <nav style={{ fontSize: size, marginBottom: '10px' }}>
      <a href="#home">Home</a> | <a href="#about">About</a> | <a href="#contact">Contact</a>
    </nav>
  );
}

function Controls({ theme, setTheme, fontSize, setFontSize }) {
  return (
    <div>
      <ThemeToggle theme={theme} setTheme={setTheme} />
      <FontControl fontSize={fontSize} setFontSize={setFontSize} />
    </div>
  );
}

function ThemeToggle({ theme, setTheme }) {
  return (
    <button onClick={() => setTheme(theme === 'light' ? 'dark' : 'light')}>
      {theme === 'light' ? 'Dark' : 'Light'} Mode
    </button>
  );
}

function FontControl({ fontSize, setFontSize }) {
  return (
    <select value={fontSize} onChange={(e) => setFontSize(e.target.value)}>
      <option value="small">Small</option>
      <option value="medium">Medium</option>
      <option value="large">Large</option>
    </select>
  );
}

function Content({ theme, fontSize }) {
  const size = fontSize === 'small' ? '14px' : fontSize === 'large' ? '20px' : '16px';
  
  return (
    <main style={{ fontSize: size }}>
      <Article theme={theme} />
      <Sidebar theme={theme} />
    </main>
  );
}

function Article({ theme }) {
  return (
    <article>
      <h1>Article Title</h1>
      <p>This content uses the {theme} theme. Notice how theme props are passed through every component!</p>
    </article>
  );
}

function Sidebar({ theme }) {
  return (
    <aside style={{ marginTop: '20px', padding: '10px', border: '1px solid #ccc' }}>
      <h3>Sidebar</h3>
      <p>Current theme: {theme}</p>
    </aside>
  );
}
```

### Your Task:
1. Create a ThemeContext with createContext
2. Create a ThemeProvider component that manages theme and fontSize state
3. Replace all prop drilling with useContext
4. Create a custom hook `useTheme()` for cleaner access
5. Add error handling for components used outside the provider

### Expected Structure:
```javascript
// ThemeContext.js
const ThemeContext = createContext();

export function ThemeProvider({ children }) {
  // Manage theme and fontSize state here
  // Provide value with { theme, setTheme, fontSize, setFontSize }
}

export function useTheme() {
  // Custom hook with error handling
  // Return context value or throw error if used outside provider
}

```

### Requirements:
- Remove ALL theme/fontSize props from component signatures
- All components should get theme values from context
- Implement proper error handling in useTheme hook
- Extension: Add localStorage persistence for theme preferences

---

## Exercise 3 - EXTENSION

Build a multi-step form wizard with validation, navigation, and data persistence using useReducer.

### Requirements:
Create a 3-step registration form with useReducer that handles:

1. **Step 1:** Personal info (name, email, age)
2. **Step 2:** Account details (username, password, confirm password)  
3. **Step 3:** Preferences (newsletter, notifications, theme)

### Your Task:
```javascript
// Define your initial state
const initialState = {
  currentStep: 1,
  formData: {
    // Step 1
    name: '',
    email: '',
    age: '',
    // Step 2  
    username: '',
    password: '',
    confirmPassword: '',
    // Step 3
    newsletter: false,
    notifications: true,
    theme: 'light'
  },
  errors: {},
  isSubmitting: false,
  isCompleted: false
};

// Create reducer that handles:
function formReducer(state, action) {
  switch (action.type) {
    case 'UPDATE_FIELD':
      // Update a single form field
    case 'SET_ERRORS':
      // Set validation errors
    case 'NEXT_STEP':
      // Move to next step (with validation)
    case 'PREV_STEP':
      // Move to previous step
    case 'SUBMIT_FORM':
      // Handle form submission
    case 'RESET_FORM':
      // Reset to initial state
    default:
      return state;
  }
}
```

### Actions to implement:
```javascript
// dispatch({ type: 'UPDATE_FIELD', data: { field: 'name', value: 'John' } })
// dispatch({ type: 'NEXT_STEP' })
// dispatch({ type: 'PREV_STEP' })
// dispatch({ type: 'SET_ERRORS', data: { email: 'Invalid email' } })
// dispatch({ type: 'SUBMIT_FORM' })
```

### Validation Rules:
- Step 1: Name required, email format, age 18+
- Step 2: Username 3+ chars, password 6+ chars, passwords match
- Step 3: No validation required
- Cannot proceed to next step with errors

