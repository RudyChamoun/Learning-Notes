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
**/: name_of_param**

router.get('/user/:id' , (req,res)=>{
// To parse the data from the URL we use **req.params.name_of_var
res.send("Hello User" + req.params.id)
})

<u><b>.route</b> Method</u>
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


<u><b>.param</b> Method</u>
  
In Express.js, `router.param()` is a method used to define middleware that will be executed when a specific route parameter (usually dynamic for param) is present in the URL of a request. Let's break down the syntax and its functionality:

router.**param**('id', (**req, res, next, id**) => {
  // Middleware logic here
  **next();**
});

- `router`: This is an instance of the Express router on which you define routes and middleware. It could be either the main router (`app`) or a sub-router (`Router`).
    
- `.param('id', callback)`: This method is used to define middleware that will be executed when the parameter `'id'` is present in any route that uses it. The first argument `'id'` specifies the name of the route parameter to watch for. The second argument is a callback function that defines the middleware logic.
    
- `(req, res, next, id) => { /* Middleware logic here */ }`: This is the callback function passed to `router.param()`. It takes four arguments:
    
    - `req`: Represents the request object, containing information about the HTTP request.
    - `res`: Represents the response object, used to send back the response to the client.
    - `next`: A function that, when called, passes control to the next middleware in the stack. It's used to move to the next middleware function in the request-response cycle.
    - `id`: Represents the value of the route parameter specified in the first argument of `router.param()`. In this case, it represents the value of the `'id'` parameter extracted from the URL.

The purpose of using `router.param()` is often to perform common tasks or pre-processing related to a specific route parameter. For example, you might use it to retrieve data associated with a specific ID from a database and attach it to the request object (`req`) for subsequent middleware or route handlers to use. It's a way to centralize the logic for handling specific route parameters across multiple routes in your application.

ex : 
const users = [{name : 'rudy'} , {name : 'paul'}];

router.get('/user/:id' , (req,res)=>{
	console.log(req.user);
})

router.param('id',(req,res,next,id)=>{
req.user = users[id];
next();
})

We used the middleware function here in order to retrieve the user from the array first and then change the flow of execution back to the route .


## 8) <u>Middleware</u>

<b>This section will cover middleware</b>

- Is is important to know that middleware execute from top to bottom meaning if we created a middleware function and then put it to use using app.use(name_of_midd), anything defined before it (any route ; ex : app.use('/user',userRouter)) , will not be affected by the middleware.
	Likewise, all routes defined after the middleware was put to use will be affected.

ex of middleware function : 
function logger(req,res,next){
console.log("Hey");
next();
}

- If I want to apply a middleware to only one specific route, I can add the defined middleware function as a parameter in the route's definition.

	ex : app.get('/' , logger , (req,res)=>{
	});

- If I want to apply a middleware function to all routes starting with a certain a path, I can go to file containing these routes (user.js, store.js, ...) and in it :
		- define the middleware function : function mid(req,res,next){
														///code 
														next();
														}
		- apply it to the router of this route : router.use(mid);



## 8)<u>Rendering Static Files</u>

<b> This section will cover rendering static files like html (where nothing in content changes) </b>

Create a new folder (by convention name it "Public"), inside this folder you will store all static files to be rendered.

In the server.js file, we have to use a built-in express middleware render the files, using the following line : app.use(**express.static**('public'));
