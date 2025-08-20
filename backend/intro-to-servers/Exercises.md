# Exercises


## Exercise 1

Create a simple HTTP server that responds to different routes.

- Create a server that listens on port 3000
- Handle these routes:
  - `GET /` - Return "Welcome to my server!"
  - `GET /about` - Return "This is the about page"
  - `GET /contact` - Return your contact information
  - Any other route - Return "404 - Page not found" with status code 404
- Log each incoming request to the console with method and URL

## Exercise 2

Build a simple REST API server that manages a list of users.

- Create a server on port 3000
- Maintain an in-memory array of users (each user has id, name, email)
- Handle these endpoints:
  - `GET /api/users` - Return all users as JSON
  - `GET /api/users/:id` - Return specific user by ID
  - `POST /api/users` - Add a new user (accept JSON data)
- Set appropriate Content-Type headers
- Handle invalid JSON with proper error responses
- Include basic error handling for missing users

**Sample user data to start with:**
```js
let users = [
  { id: 1, name: "John Doe", email: "john@example.com" },
  { id: 2, name: "Jane Smith", email: "jane@example.com" }
];
```