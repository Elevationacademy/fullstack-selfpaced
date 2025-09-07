# App Configuration

For the most part, our app is ready for production. Find `app.listen` in your `server.js` (or `app.js,` or whatever you called your server file). You'll see this (or something like it):

```js
const PORT = 8080
app.listen(PORT);
```
  

Change it by adding `process.env.PORT`, like this:

```js
const PORT = 8080
app.listen(process.env.PORT || PORT);
```
  

`process.env` is a variable that refers to where your app is being run. You've now made sure that the app will listen to the port that is allocated by Render, or your local port if you don't have a `process.ev` because you're running locally.

  

Next, change your `mongoose.connect` line by adding the following configuration key:


```js
mongoose.connect(process.env.MONGODB_URI||'mongodb://localhost/yourDB');
```
  

Render will replace `MONGODB_URI` with a value it has created for you - your own unique connection string with a username and password that is now hidden in the code.

  

Next, make sure that in your `package.json` file, there is a `"scripts"` property with the key-value pair of `"start": "n`ode server.js`"` inside it. It should look something like this:

  

(The dependencies might change according to the project)

```js
{
  "name": "render_test",
  "version": "1.0.0",
  "description": "",
  "main": "server.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node server.js"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "body-parser": "^1.15.2",
    "express": "^4.14.0",
    "mongoose": "^4.6.0"
  }
}
```
  
Now, simply pushing your app to the branch configured in Render (main branch is the default), you app will be automatically deployed to render.