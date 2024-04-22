## 1) <u>Project Setup</u>

<b>This section explains how to setup my project at the start</b> 

Using the VSCode command line : 

1. Run **npm init -y** => command is going to setup basic package.json file, this is where we are gonna install all the different libraries we're going to use (express, mongoDB)

2. Run **npm i express** => command is going to install the express library

3.   3.1-To make development easier, install nodemon (**run npm i --save-dev nodemon**) => allows  us to easily restart our server anytime we make changes
	3.2- To finish setting it up, inside "scripts" create a "devStart" : "**nodemon** server.js"

4. Create a server.js file wich is the file that contains all of our server code (to run it use **npm run** devStart)

## 2) <u>Server Setup</u>

<b>This section explains how to setup my server using express and have it listening for requests </b>

To create the express server : 
1. Import the Express Framework : const express = **require**('express');

2. Create an Express application (server). The express() function is a top-level function exported by the express module : const app = **express()**;

3.  To make our server listen : app.**listen**(3000); // In this example we are saying that our app (server) is listening on port 3000 for request


Now that we have an instance of the express application (server), app provides methods to define routes, handle HTTP requests, and perform various other server-related tasks.

## 3) <u>Basic Routing</u>

<b>This section will cover the basics of creating routes</b>

We can create routes for our server, the syntax of creating routes is the following : 

![[Screenshot 2024-04-16 130607.png]]

## 4) <u>Sending Data</u>

**This section will cover sending various types of data as a response**

As seen in the section above, the syntax for creating routes is clear 

	name_of_server.get('URL_path' , (req,res)=>{
			res.send("Hi");
			})

However, the .send will not be used often when developing, instead here are some more useful methods to use when generating a response : 
- res.**json()** : sends a JSON response
- res.**status**(400).**send**("Message to be displayed")
- res.**send**() : sends a response of various types
- res.redirect() : Redirect a request.
- res.render("path_of_file") : 




## 5) <u>Rendering HTML</u>

**This section will cover how to render html as a response from accessing a route**
Refer to youtube video : https://youtu.be/SccSCuHhOw0?si=UwHg0FHyXLPr4ipZ



## 6) <u>Routers</u>

<b> This section will cover what are routers and how do we create them </b>


If we have a large number of routes it would be impractical to define all these routes in the main server file. Instead, we can create a separate "routes" folder and in it we create different .js files that each contain their own routes.
ex : user.js ==> inside this file, we define all routes related to user, like /user, /user/info ...

We use **routers** in order to create our own mini independent application that is separate from our main server application, however we have to link every route file to the main server.


Steps to create and link a Router in every route file : 
- We have to import express framework : const express = require('express');
- We have to create our router : const router = express.**Router**();
- We have to define our routes in the file using the new defined router  : 
	router.get('/user/data' , (req,res)=>{
			..........})
- We have to export the router in order to link it to our main server file : **module.exports** = router;
- In the main server file we have to :
	- Import our router from the file : const userRouter = require('./routes/user'); [use local path]
	- Link the routes to our main server (use the basic path, so we don't explicitly write it every time in routes folder) : **app.use**('/user' , userRouter)


## 7) <u>Advanced Routing</u>

<b> This section will cover advanced routing concepts </b>

<u>Dynamic Parameters</u>
If we want to create a route where the action is dynamically determined by the URL  ( we're creating a dynamic parameter, a parameter that is parsed from the URL) we have to use the key : 
**/:** name_of_param

router.get('/user/:id' , (req,res)=>{
// To parse the data from the URL we use **req.params.name_of_var
res.send("Hello User" + req.params.id)
})

<u>.route Method</u>
The .route method can be used when we have multiple routes defined to the same path and each one responds to a different request (get, put, delete ...). The .route method is used to clean up the code in the following : 

instead of : 
router.get("/id",(req,res)=>{
/////
});
router.put("/id",(req,res)=>{
/////
})

using .route method : 
router.route("/id")
.get((req,res)=>{
/////
})
.put((req,res)=>{
/////
})