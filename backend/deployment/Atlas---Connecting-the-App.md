# Atlas & Connecting the App

Now it's time to connect to our App

Lets go back to the Database page, This time we will click on Connect
  
![](./img/Atlas5.png)

Click on ```Connect your Application``` Button.

---

You will be provided with what Driver you need and the connection string

![](./img/Atlas6.png)

**Notice!** you will need to replace the following:
- ```<password>``` -> your actual password 
- ```myFirstDataBase?``` -> your database name

---

In Render, head to the 'Environment' tab and click on the 'Add Environment Variable' button:

![./img/render-env-vars.png](./img/render-env-vars.png)
  

Here you need to add a MONGODB_URI key, and paste the connection string you've been given before:

![./img/render-env-mongo.png](./img/render-env-mongo.png)
  

That's all for the Mongo setup - one last step and you're ready to deploy again!
