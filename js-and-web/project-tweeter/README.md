# Tweeter Project - Complete Guide

## Overview

This project will help you practice DOM manipulation, events and modular JavaScript development by building a simplified Twitter-like application called "Tweeter". You'll implement the MVC (Model-View-Controller) architecture pattern using three separate modules:

- **Model** (Logic Module): Handles data operations for posts and comments
- **View** (Render Module): Manages the display and rendering of posts
- **Controller** (Main Module): Handles user interactions and connects Model and View

By the end of this project, you'll have a working Tweeter application that allows users to:
- Create new posts ("twits")
- Add comments to posts
- Delete posts and comments
- View all posts and their comments in a dynamic interface

Eventually, our Tweeter will look something like this:
![](./image.png ':size=75%')

Follow the steps below - once a step is finalized add a clear commit to GitHub with "Step X finalized"

## Step 1: Project Setup

1. Create a new folder called `tweeter`
2. Set up a GitHub repository (optional but recommended)
3. Create the following files in your `tweeter` folder:
   - `index.html`
   - `style.css`
   - `model.js` (for the logic module)
   - `render.js` (for the rendering module)
   - `main.js` (for the controller)

## Step 2: Create the Tweeter Logic Module (Model)

In your `model.js` file, create a `Tweeter` module that handles all data operations. This module should be completely independent and not know about the UI.

### Requirements:

Your Tweeter module should include:

- **Private array of posts** - Use the dummy data provided below
- **Private variables** for tracking IDs:
  - `postIdCounter` - to count total posts
  - `commentIdCounter` - to count total comments
- **Public functions** (return these from your module):
  - `getPosts()` - returns the posts array
  - `addPost(text)` - adds a new post object to posts
  - `removePost(postID)` - removes a post by ID
  - `addComment(postID, text)` - adds a comment to a specific post
  - `removeComment(postID, commentID)` - removes a comment from a post

### Dummy Data

Use this data structure to start:

```javascript
[
    {
        text: "First post!",
        id: "p1",
        comments: [
            { id: "c1", text: "First comment on first post!" },
            { id: "c2", text: "Second comment on first post!!" },
            { id: "c3", text: "Third comment on first post!!!" }
        ]
    },
    {
        text: "Aw man, I wanted to be first",
        id: "p2",
        comments: [
            { id: "c4", text: "Don't worry second poster, you'll be first one day." },
            { id: "c5", text: "Yeah, believe in yourself!" },
            { id: "c6", text: "Haha second place what a joke." }
        ]
    }
]
```

### Implementation Guidelines:

1. **Post Objects Structure:**
   - `id`: String (format: "p1", "p2", "p3", etc.)
   - `text`: String (the post content)
   - `comments`: Array of comment objects

2. **Comment Objects Structure:**
   - `id`: String (format: "c1", "c2", "c3", etc.)
   - `text`: String (the comment content)

3. **ID Generation:**
   - Posts: Generate IDs like "p4", "p5", "p6", etc.
   - Comments: Generate IDs like "c7", "c8", "c9", etc.

### Testing Your Logic Module

Test your module with this code (you can run it in the browser console):

```javascript
const tweeter = Tweeter();

// Test adding a post
tweeter.addPost("This is my own post!");
console.log(tweeter.getPosts());
// Should add: {text: "This is my own post!", id: "p3", comments: []}

// Test removing a post
tweeter.removePost("p1");
console.log(tweeter.getPosts());
// Should only have two posts left

// Test adding comments
tweeter.addComment("p3", "Damn straight it is!");
tweeter.addComment("p2", "Second the best!");
console.log(tweeter.getPosts());

// Test removing comments
tweeter.removeComment("p2", "c6");
console.log(tweeter.getPosts());
```

## Step 3: Create the Renderer Module (View)

In your `render.js` file, create a `Renderer` module that handles all display logic. This module should only care about rendering and not about data manipulation.

### Requirements:

The Renderer module should expose one function:
- `renderPosts(posts)` - receives an array of posts and renders them to the DOM

### Implementation Guidelines:

1. **The renderPosts function should:**
   - Receive one parameter: `posts` (the array from your Tweeter module)
   - First empty the `#posts` element
   - Loop through each post and append HTML to `#posts`
   - Use jQuery to create and add elements
   - Include both post content and comments in the generated HTML

2. **HTML Structure Requirements:**
   - Add each post's ID in a `data-id` attribute
   - Add each comment's ID in a `data-id` attribute
   - Use appropriate CSS classes for styling
   - Include delete buttons for posts and comments

3. **Suggested HTML Structure:**
   ```html
   <div class="post" data-id="p1">
       <div class="post-text">Post content here</div>
       <div class="delete" data-id="p1">Delete Post</div>
       <div class="comments">
           <div class="comment" data-id="c1">Comment text</div>
           <div class="delete-comment" data-id="c1">X</div>
           <!-- More comments... -->
       </div>
       <input type="text" placeholder="Got something to say?" class="comment-input">
       <button class="comment-button">Comment</button>
   </div>
   ```

4. **Best Practices:**
   - Use template literals for cleaner string construction
   - Create helper functions for generating post and comment HTML

### Testing Your Renderer

Test your renderer with this code in `main.js`:

```javascript
const tweeter = Tweeter();
const renderer = Renderer();

// This should render the initial dummy data
renderer.renderPosts(tweeter.getPosts());
```

## Step 4: Create the Controller (Main Module)

In your `main.js` file, create the controller that handles user interactions and connects the Model and View.

### Requirements:

Add event listeners for:
1. **The Twit button** - creates new posts
2. **The Delete Post button** - removes posts
3. **The Comment button** - adds comments
4. **The X next to each comment** - removes comments

### Implementation Guidelines:

1. **Event Listeners Setup:**
   - Most listeners will be on **dynamic elements** (except the main Twit button)

2. **User Interactions:**

   **When Twit button is clicked:**
   - Grab the value from the main input field (`#input`)
   - Call `tweeter.addPost(text)` with the input value
   - Clear the input field
   - Re-render the posts

   **When Delete Post button is clicked:**
   - Use DOM traversal to get the post ID from the `data-id` attribute
   - Call `tweeter.removePost(postID)`
   - Re-render the posts

   **When Comment button is pressed:**
   - Use DOM traversal to get the post ID
   - Get the comment text from the comment input field
   - Call `tweeter.addComment(postID, text)`
   - Clear the comment input field
   - Re-render the posts

   **When X on a comment is pressed:**
   - Use DOM traversal to get both the post ID and comment ID
   - Call `tweeter.removeComment(postID, commentID)`
   - Re-render the posts

3. **Important Notes:**
   - **Always re-render after data changes** - call `renderer.renderPosts(tweeter.getPosts())` after each data modification
   - You may need to add additional CSS classes to your HTML structure for easier element selection

## Step 5: Testing and Debugging

1. **Open your `index.html` in a browser**
2. **Test all functionality:**
   - Creating new posts
   - Deleting posts
   - Adding comments
   - Deleting comments
3. **Check the browser console for errors**
4. **Use browser developer tools to debug issues**

### Common Issues:

- **Event listeners not working**: Make sure you're using event delegation for dynamic elements
- **DOM traversal problems**: See [here](https://medium.com/codex/how-to-traverse-the-dom-in-javascript-7fece4a7751c) on how to traverse the DOM
- **IDs not being captured**: Ensure you're using `data-id` attributes correctly
- **Nothing renders**: Check that all your modules are properly connected and the initial render call is made

## Tweeeeet

Congratulations, you’ve built Tweeter! Revel in the greatness of your app building capabilities.
On a more serious note, you should appreciate the power of modules more
now. You wrote all three parts of Tweeter yourself (logic, render, event-handling)

but because it’s so modular, you could have easily split this task between
three people!

If you define everything correctly ahead of time (what does the renderer
receive, what logical operations are available to the event handlers?) - then
you can break big projects down into sub-tasks and work much more
efficiently.
Think about this. It’s awe-some.