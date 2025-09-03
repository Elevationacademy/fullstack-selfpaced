# Recipes Project - Step 2

Enhance your Recipe API by migrating to MySQL with Sequelize, implementing user authentication, adding file upload capabilities, and deploying to production. This week transforms your basic API into a production-ready application.

- Set up MySQL database and design relational database schemas
- Implement JWT-based authentication and authorization
- Handle file uploads for recipe images
- Deploy application to production with environment management

## Database Schema

### Users Table
```javascript
{
  id: Primary Key (UUID)
  username: String (unique, 3-30 chars)
  email: String (unique, valid email)
  password: String (hashed)
  firstName: String
  lastName: String
  createdAt: Timestamp
  updatedAt: Timestamp
}
```

### Recipes Table (Enhanced)
```javascript
{
  id: Primary Key (UUID)
  title: String (required)
  description: Text
  ingredients: JSON Array
  instructions: JSON Array
  cookingTime: Integer
  servings: Integer
  difficulty: ENUM (easy, medium, hard)
  imageUrl: String (file path)
  isPublic: Boolean (default: true)
  userId: Foreign Key (References Users)
  createdAt: Timestamp
  updatedAt: Timestamp
}
```

### UserFavorites Table (Many-to-Many)
```javascript
{
  id: Primary Key
  userId: Foreign Key
  recipeId: Foreign Key
  createdAt: Timestamp
}
```


## Authentication Routes

### POST /api/auth/register
```javascript
// Request body
{
  username: "johndoe",
  email: "john@example.com",
  password: "password123",
  firstName: "John",
  lastName: "Doe"
}

// Response
{
  success: true,
  status: 201,
  message: "User registered successfully",
  user: { id, username, email, firstName, lastName },
  token: "jwt-token"
}
```

#### POST /api/auth/login
```javascript
// Request body
{
  email: "john@example.com",
  password: "password123"
}

// Response
{
  success: true,
  status: 200,
  message: "Login successful",
  user: { id, username, email, firstName, lastName },
  token: "jwt-token"
}
```

### GET /api/auth/profile
- Protected route (requires JWT token)
- Returns current user's profile information

## Enhanced Recipe Routes

### POST /api/recipes (Protected and image upload)
- Requires authentication
- Associates recipe with authenticated user
- Supports image upload via multipart/form-data
  - Validate image type (jpg, jpeg, png)
  - Limit file size (5MB)
  - Store in `/uploads/recipes/` directory or external storage (e.g. Cloudinary)

### PUT /api/recipes/:id (Protected)
- Users can only edit their own recipes
- Supports image upload and update

### DELETE /api/recipes/:id (Protected)
- Users can only delete their own recipes
- Also deletes associated image file

### GET /api/recipes/my-recipes (Protected)
- Returns recipes created by authenticated user

## User Favorites

### POST /api/users/favorites/:recipeId (Protected)
- Add recipe to user's favorites

### DELETE /api/users/favorites/:recipeId (Protected)
- Remove recipe from favorites

### GET /api/users/favorites (Protected)
- Get user's favorite recipes

## Authorization Logic

### Recipe Ownership
- Users can only edit/delete recipes they created
- Implement ownership check in middleware `checkRecipeOwnership`

## Testing Requirements

Have a specific route request in Postman for each of the following.

### Authentication Testing
- Test user registration with valid/invalid data
- Test login with correct/incorrect credentials
- Test protected routes with/without valid tokens
- Test token expiration

### File Upload Testing
- Test image upload with valid images
- Test upload with invalid file types
- Test upload size limits
- Test recipe creation with and without images

### Database Testing
- Test user-recipe relationships
- Test favorites functionality
- Test cascade deletes

## Deployment Requirements

### Platform Options
- **Render** (Recommended)
- Railway
- Heroku

### Database Hosting
- **Render PostgreSQL** (free tier available)
- AWS RDS
- ElephantSQL

### Deployment Checklist
1. Set up production database
2. Configure environment variables on platform
3. Set up build and start scripts
4. Handle static file serving for uploads
5. Configure CORS for frontend domains
