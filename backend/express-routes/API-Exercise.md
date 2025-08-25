# API Exercise - Extension

In this exercise you will build your own API using data from: https://jsonplaceholder.typicode.com

1. Create a new express app and keep the files separated according to the MVC principles (routes, controllers and model)

1. When the server starts it should grab all the posts from https://jsonplaceholder.typicode.com/posts and store them in an object called postObjects. The key should be the post id and the value should be the post object.

1. Use https://jsonplaceholder.typicode.com/comments to get all of the comments for the posts. Save all the comments in the corresponding postObjects for that comments postId. Add a key `comments` in the postObjects for storing all the comments for that post.

1. Create a GET request that takes an id and returns the post object for that id.

1. Create a GET request that will return all the comments for a specific post based on the id of the post.

1. Create a PUT request that will update a specific comment on a post based on the id of the post and id of the comment. Can take the following fields: name, email, body in the PUT body.

1. Create a POST request that will add a new post object. It should have all the same properties as the other post objects and it’s ID should be one higher than the last post ID. It should take userId,title and body key/values in the POST body.

1. Create a DELETE request to remove an entire post object by ID.

1. Create a DELETE request to remove a comment by the post ID and comment ID.

## Extensions for the Extension

1. Create a GET request that will let you find a specific post based on query parameters. 
    - All posts made by a certain userId
    - Posts by a specific title
    - Posts with body length greater than X

1. Create a GET request to find a comment based on specific query parameters
    - All comments with an email of a certain domain extension (.com, .org)
    - Only comments with a body less than X

1. Create a POST request for creating a new comment. The new comment should be able to be added to a specific post with the regular key/value pairs of a comment. The comment ID should be one greater than the highest comment ID. 

1. Add on a new HTTP method with a feature of your choosing.
