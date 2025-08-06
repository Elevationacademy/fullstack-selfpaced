# Tweeter 2.0 Project

## Technical Notes

1. The high level design is provided through images, feel free to follow it or change it to your design (making it responsive is a bonus)
2. Make meaningful commits (they should be small and with feature/bug specification), and push them to the repo.
3. Keep an organized folder structure - components in "components" folder, pages in another folder and reusable code in lib folder.

## Step 1 - Mock up (local data)

- Main screen with two parts: create tweet, and tweets list
- Create tweet should block the tweet creation if there are more than 140 chars (need to make the button disabled)
- The tweets should be saved locally, so if I refresh the page they won't be deleted
- The tweet list should be sorted in descending order, the latest tweet should appear first (the order should remain after refreshing the page)
- The username should be saved hard-coded for now (so you will be able to add it to each tweet you create)

![](./img/step-1-1.png)

![](./img/step-1-2.png)


## Step 2 - Server connection

- Fetch (GET) and create (POST) tweets with the following API endpoint: 
```bash
https://uckmgdznnsnusvmyfvsb.supabase.co/rest/v1/Tweets?apikey=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InVja21nZHpubnNudXN2bXlmdnNiIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NTQ0ODU5NjAsImV4cCI6MjA3MDA2MTk2MH0.D82S0DBivlsXCCAdpTRB3YqLqTOIP7MUj-p1R8Lj9Jo
```
- The server has one resource exposed: "/tweet", make requests to presenting the list of tweets, and to create a new tweet
- The tweet object is as follows: { content: string, userName: string, date: string (ISO date) }
- Save the tweet to the server on tweet post, and show the list of tweets from the server
- Show loading indicator, and prevent from adding a new tweet when adding request is in the background
- Do not forget to remove the code from the first step that saves the data locally, you don't want to have them both
- Display server errors to the user if the tweet is not added

## Step 3 - User page

- Add another page that presents the current user username (which should be hard coded until now), and has a form to change the username.
- You should save the new username locally whenever changed, and send it to the server when creating a new tweet.
- Add a navbar to the top of the screen that keeps its position no matter which page you are at, with "Home" and "Profile" links.

![](./img/step-3.png)


## Step 4 - Context

- Instead of using state and props, use context for the tweets list and creating new tweet
- When creating new tweet, do not refresh the list, but add the tweet to the existing local list
- Instead set an interval that gets updates from the server of tweets, in case someone else added a tweet (to keep the list updated)

## Step 5 - Deployment

- Deploy your project to github pages
- Follow this guide: https://levelup.gitconnected.com/deploy-your-vite-app-to-github-pages-a-lazy-devs-guide-37b0b472fa35


## Step 6 - Supabase Basic

Replace the server connection with your own [Supabse](https://supabase.com/) backend 
- Create an account in Supabase
- Create a project in Supabase
- Create a Tweets table in your Supabase project. In the table create the needed columns (date, userName and content)
- For this step make sure the RLS (row level security) is disabled - meaning that your table is read/write accessible to everyone
- Add initial dummy data to your table (use chatGPT for this)
- Update all your API calls to call Supabase JavaScript library. For example (reading all tweets):
```js
let { data, error } = await supabase
  .from('Tweets')
  .select('*')
```
- Check that your app is working as before

## Step 7 - Authentication

In this step we are going to add authentication to our React application and some security measures to Supabase table.

- Enable RLS (row level security) in the Tweets table
- Create 2 policies for read (SELECT) and create (INSERT) so only authenticated users can make the calls
- Now you API calls will return an error until you finalize the following authentication steps
- In your Supabase project explore the authentication module
- In Supabase authentication manually add a user to the Users view
- In your React application implement a login page with basic user password authentication
- Using Supabase API make the login calls
- Only logged in users can see tweets and send tweets. If the user is not logged in - prevent routing to the tweets pages, and redirect the user to the login page
- Add Login/Logout items to the Navbar

## Step 8 - Sign up - EXTENSION

Add a sign up functionality to your application and connect it with Supabase.

## Step 9 - Infinite Scrolling - EXTENSION

Implement infinite scrolling - at the beginning get 10 tweets, and when the user reaches the end of the screen load the next 10 tweets, etc. 
