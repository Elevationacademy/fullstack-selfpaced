# Exercises

## Exercise 1

Create and use basic custom middleware functions.

1. Create a simple Express app with the following middleware:
   - A logging middleware that prints: `[TIMESTAMP] METHOD URL`
   - A request counter middleware that adds a `requestCount` property to `req`
   - Apply both middlewares to all routes

2. Create two routes:
   - `GET /` - Returns welcome message and current request count
   - `GET /about` - Returns about message and current request count

**Expected Output:**

```
Console: [2024-01-15T10:30:00Z] GET /
Response: { "message": "Welcome!", "requestCount": 1 }
```

## Exercise 2

Implement route-specific middleware and proper error handling.

1. Create middleware functions:
   - `validateId` - Checks if `:id` parameter is a valid number, throws error if not
   - `checkResourceExists` - Simulates checking if a resource exists (use a simple array)
   - Error handling middleware that catches all errors

2. Create routes:
   - `GET /users` - Returns all users (no middleware needed)
   - `GET /users/:id` - Returns specific user (use both validation middlewares)
   - `POST /users` - Creates a user (no middleware needed)

3. Test data: `const users = [{ id: 1, name: 'John' }, { id: 2, name: 'Jane' }]`

**Expected Behavior:**
- `GET /users/1` → Returns John
- `GET /users/999` → 404 error (user not found)
- `GET /users/abc` → 400 error (invalid ID format)

## Exercise 3

Build a comprehensive API with multiple validation approaches.

1. Create a blog-like API with the following validation approaches:
   - **Posts**: Use AJV with JSON Schema
   - **Comments**: Use express-validator

2. Implement advanced middleware:
   - Request/response logger with execution time
   - Rate limiting simulation (max 10 requests per IP per minute)
   - Content-type validation for POST/PUT requests
   - Response formatter middleware

3. Data Models:
   - **Post**: title (5-100 chars), content (10-1000 chars), tags (array of strings)
   - **Comment**: content (5-500 chars), email (valid email), postId (must reference existing post)

4. Routes with proper validation:
   - `POST /posts` - AJV validation
   - `GET /posts` - No validation
   - `POST /posts/:postId/comments` - express-validator + post exists check
   - `GET /posts/:postId/comments` - ID validation only

**Example API Behavior:**
```bash
# Create post 
POST /posts { 
  "title": "My First Post", 
  "content": "This is the content...", 
  "category": "Technology",
  "tags": ["javascript", "nodejs"]
}

# Add comment
POST /posts/1/comments {
  "content": "Great post!",
  "email": "user@example.com"
}
```

### Extension

Add the following advanced middleware:
1. Request/response logger with execution time
1. Rate limiting simulation (max 10 requests per IP per minute)
1. Content-type validation for POST requests
