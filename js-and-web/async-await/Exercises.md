# Exercises

## Exercise 1

1. Convert the function to use `async/await` syntax
2. Use `try/catch` for error handling
3. Maintain the same functionality (logging and return values)
4. Test with both valid (1-10) and invalid (999) user IDs

```js
// Given Promise-based code:
function getUserById(userId) {
  return fetch(`https://jsonplaceholder.typicode.com/users/${userId}`)
    .then(response => {
      if (!response.ok) {
        throw new Error('User not found');
      }
      return response.json();
    })
    .then(user => {
      console.log(`Found user: ${user.name} (${user.email})`);
      return user;
    })
    .catch(error => {
      console.error('Error fetching user:', error.message);
      return null;
    });
}
```
## Exercise 2


1. Create a function that fetches a user and then fetches all posts by that user.
1. Return an object containing both user info and their posts.
1. Handle errors at each step with meaningful messages.
1. If user doesn't exist, don't attempt to fetch posts.

```js
// Starter code structure:
async function getUserWithPosts(userId) {
  // Your implementation here
  // 1. Fetch user from: https://jsonplaceholder.typicode.com/users/${userId}
  // 2. Fetch posts from: https://jsonplaceholder.typicode.com/posts?userId=${userId}
  // 3. Return combined data
}
```

## Exercise 3

Create a dashboard function that fetches multiple types of data simultaneously and aggregates them.

Fetch these data sources **in parallel**:
1. All users: `https://jsonplaceholder.typicode.com/users`
2. All posts: `https://jsonplaceholder.typicode.com/posts`
3. All comments: `https://jsonplaceholder.typicode.com/comments`

Then process the data to create a summary dashboard.

### Expected Return Format
```javascript
{
  summary: {
    totalUsers: 10,
    totalPosts: 100,
    totalComments: 500,
    avgPostsPerUser: 10,
    avgCommentsPerPost: 5
  },
  topUsers: [
    {
      name: "Leanne Graham",
      postCount: 10,
      commentCount: 15  // comments on their posts
    }
    // ... top 3 users by post count
  ],
  recentPosts: [
    // Last 5 posts (highest IDs)
  ]
}
```
