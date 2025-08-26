# Recipes Project - Step 1

Welcome to this incremental server API project. Each week as we learn and expand our backend development capabilities we will add them to this on-going incremental project. 

## Step 1 Focus

In this first step we will build a Recipe CRUD API using Express.js with proper middleware, validation, and routing. This week focuses on the fundamentals of backend development without database integration.

- Set up an Express.js server
- Implement RESTful API routes
- Create middleware for validation and error handling
- Structure our project based on SoC and MVC principles

## Data Model

The recipe data structure with the following fields:
```js
{
  id: "unique-id",
  title: "Recipe Title",
  description: "Brief description",
  ingredients: ["ingredient 1", "ingredient 2"],
  instructions: ["step 1", "step 2"],
  cookingTime: 30, // in minutes
  servings: 4,
  difficulty: "easy", // easy, medium, hard
  rating: 4.5,
  createdAt: "2025-01-01T00:00:00.000Z"
}
```

## API Endpoints

### GET /api/recipes
- Retrieve all recipes
- Support query parameters for filtering:
  - `difficulty` (easy, medium, hard)
  - `maxCookingTime` (number in minutes)
  - `search` (search in title and description)
- Return recipes with proper HTTP status codes

### GET /api/recipes/:id
- Retrieve a single recipe by ID
- Return 404 if recipe not found
- Return proper error messages

### POST /api/recipes
- Create a new recipe
- Validate all required fields
- Generate unique ID using `uuid`
- Add creation timestamp
- Return created recipe with 201 status

### PUT /api/recipes/:id
- Update an existing recipe
- Validate the updated data
- Return 404 if recipe not found
- Return updated recipe

### DELETE /api/recipes/:id
- Delete a recipe by ID
- Return 404 if recipe not found
- Return 204 status on successful deletion

### GET /api/recipes/stats
Return recipe statistics:
- Total number of recipes
- Average cooking time
- Recipes by difficulty level
- Most common ingredients (bonus)

## Middleware Requirements

### Validation Middleware
Create middleware to validate recipe data:
- `title`: Required, string, 3-100 characters
- `description`: Required, string, 10-500 characters
- `ingredients`: Required, array with at least 1 item
- `instructions`: Required, array with at least 1 item
- `cookingTime`: Required, positive number
- `servings`: Required, positive integer
- `difficulty`: Required, one of: "easy", "medium", "hard"

### Error Handling Middleware
- Catch and format all errors
- Return consistent error response format:
  ```javascript
  {
    error: true,
    message: "Error description",
    statusCode: 400
  }
  ```

### Logging Middleware
- Use `morgan` for request logging
- Log all incoming requests with timestamp

## Data Persistence

- Store recipes in a JSON file (`data/recipes.json`)
- Implement helper functions to read/write JSON file
- Include error handling for file operations

## Testing

Be sure to have many request endpoints in Postman each testing something specific, for example:

1. Create a new recipe with valid data
2. Try to create a recipe with invalid data (missing fields, wrong types)
3. Retrieve all recipes
4. Retrieve a specific recipe
5. Update an existing recipe
6. Delete a recipe
7. Test filtering and search functionality
8. Test error scenarios (invalid IDs, malformed JSON)

## Extensions

- Recipe rating system (allow rating updates)
- Recipe search with multiple criteria
- Recipe sorting (by date, rating, cooking time)
- Request rate limiting