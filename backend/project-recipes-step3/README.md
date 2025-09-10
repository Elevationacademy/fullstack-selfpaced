# Recipes Project - Step 3

Enhance your Recipe API with MongoDB for flexible data structures, implement AI-powered features using API and MCP (Model Context Protocol), and create a hybrid database system that leverages both SQL and NoSQL strengths.

- Integrate MongoDB alongside SQL in a hybrid approach
- Design flexible NoSQL schemas
- Create AI-enhanced user experiences

## Hybrid Database Strategy

### SQL (Structured Data)
- Users
- Recipes (core data)
- Authentication data

### MongoDB (Flexible Data)
- Recipe Comments & Reviews
- Recipe Collections
- AI-generated content

## MongoDB Schemas

### Comments Schema
```javascript
{
  _id: ObjectId,
  recipeId: String (references SQL Recipe.id),
  userId: String (references SQL User.id),
  username: String (denormalized for performance),
  comment: String,
  rating: Number (1-5),
  likes: [String], // Array of user IDs who liked
  isEdited: Boolean,
  createdAt: Date,
  updatedAt: Date
}
```

### Recipe Collections Schema
```javascript
{
  _id: ObjectId,
  userId: String,
  title: String,
  description: String,
  recipes: [{
    recipeId: String,
    recipeTitle: String, // denormalized
    addedAt: Date,
    notes: String
  }],
  isPublic: Boolean,
  tags: [String],
  followers: [String], // user IDs
  createdAt: Date,
  updatedAt: Date
}
```

### AI Interactions Schema
```javascript
{
  _id: ObjectId,
  userId: String,
  sessionId: String,
  interactions: [{
    type: String, // suggestion, substitution, weather
    query: String,
    response: String,
    context: Object, // relevant recipe/ingredient data
    timestamp: Date,
    helpful: Boolean // user feedback
  }],
  createdAt: Date
}
```

## New API Endpoints

### Comments & Reviews

#### POST /api/recipes/:id/comments
```javascript
// Request body
{
  comment: "This recipe was amazing!",
  rating: 5
}
```

#### GET /api/recipes/:id/comments
- Returns paginated comments with replies
- Include aggregate rating information

#### PUT /api/comments/:commentId
- Edit own comments only

#### POST /api/comments/:commentId/like
- Toggle like on a comment

### Recipe Collections

#### POST /api/collections
```javascript
{
  title: "Comfort Food Collection",
  description: "My favorite comfort food recipes",
  recipeIds: ["recipe-uuid-1", "recipe-uuid-2"]
}
```

#### GET /api/collections
- List user's collections and public collections

#### POST /api/collections/:id/recipes
- Add recipe to collection

### AI-Powered Features

Implement the below using an API to an LLM (e.g. OpenAI, Claude, etc.)

#### POST /api/ai/recipe-suggestions
```javascript
{
  ingredients: ["chicken", "tomatoes", "basil"],
  dietary_restrictions: ["gluten-free"],
  cuisine_preference: "Italian",
  cooking_time: 30
}

// Response
{
  suggestions: [
    {
      title: "AI-Suggested Chicken Caprese",
      ingredients: [...],
      instructions: [...],
      confidence: 0.85
    }
  ]
}
```

#### POST /api/ai/ingredient-substitutions
```javascript
{
  recipe_id: "recipe-uuid",
  substitute_ingredient: "heavy cream",
  dietary_need: "dairy-free"
}

// Response
{
  substitutions: [
    {
      substitute: "coconut cream",
      ratio: "1:1",
      notes: "Will add slight coconut flavor"
    }
  ]
}
```

### Extension: MCP Integration

Suggest recipes based on current weather conditions.

#### GET /api/recipes/weather-suggestions?city=Tokyo

- In query params send the city to fetch weather conditions
- Integrate with a weather MCP server to get the weather conditions (e.g. `hideya/mcp-server-weather-js`, `cmer81/open-meteo-mcp`)
- Return up to 3 recipes based on the weather conditions

