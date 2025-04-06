---
author: "Milad"
title: "How I learned Express.js in 1 day, from nothing"
date: "2025-03-27"
description: "Overview of my Steam Connect project"
FAtags: ["javascript", "web", "server"]
FAcategories: ["web"]
FAseries: ["Themes Guide"]
aliases: ["migrate-from-jekyl"]
ShowToc: true
TocOpen: true
weight: 2
---

This blog post outlines my experience with learning http servers in a short time frame. Contains the essentials of Express.js and overall web servers.

<!--more-->

## Why?

This all happened because I was developing my [Steam Connect](https://github.com/MiladGGG/steam-connect) project that needed **Passport.js** authentication. I naively thought that **Passport.js** would just work, on its own.  
After some searching, I found that it required a server, such as an **Express.js** server. After some more searching into HTTP servers, this is when I realised how far I actually was from understanding and implementing a my key authentication feature into my project.  
This is the exact moment where I became determined to teach myself web servers/APIs. I focused on the essentials and used **Express.js** which sped up the learning process and I was confidently able to set one up after a day.




## 1. Initialisation

(You must of course run ```npm install express``` before proceeding and have **node.js**)  

If you google how to make a server, you will probably end up copying and pasting a script that contains this:  

*sever.js*
```js
import express from "express"

const app = express()
const port = 3000

app.listen(port, () => {
  console.log(`Server is live on ${port}`)
})
```

This is everything you need to just initialise the server.  
To run this server on the port specified(3000 in this case), open up a terminal and run ```node server.js```.  

(If the port is already in use, you can ```kill``` it in the terminal, or simply just restart your terminal).


## 2. Interacting with server

Time to make use of the server in a practical way. Here I wanted to call a specific function only accessible from my backend scripts.

```js
app.get('/auth/steam', (request, response) => {
    console.log("Sucessfully Logged in!");
    response.sendStatus(200);
});
```
Add this in your *server.js* script, anywhere before ```app.listen```.
This sets up an endpoint you can call. The request parameter gives you information about the user, the response parameter allows you to return information to the user.

Now, in the frontend I called,  
```const data = await fetch(http://localhost:3000/auth/steam);```  
To call my backend function and return.

There are other important concepts here such as status codes, POST requests and bodies. However, this code by itself is the least you need to have a functional server/API.

## 3. Understanding Middleware

Middleware is essential in understanding web servers.
To summarise, middleware is just code that runs before a request.

To set up middleware with express, add ```app.use(function)``` anywhere before your endpoints.

*Custom Example:*
```js
app.use((request,result, next) => {
    console.log("Inside of middleware");
    next(); //To move on to next middleware/endpoint
});
```

*Imported Example:*
```js
import cors from 'cors';
app.use(cors({
    exampleSetting : true
}));
```

## 4. Challenges Faced

I faced many errors when implementing my express server into my project. Here are most notable.

### CORS:
CORS is a security feature that will undoubtably cause errors. If you disable CORS entirely, then features such as cookies will break. To handle CORS errors, you must import and use the CORS middleware. Finally you can configure the CORS middleware to suit your server.

```js
app.use(cors({
    origin: ["Frontend/URL"], // allow requests
    credentials: true, // enable cookie and sessions
    methods: ['GET', 'POST']
  }));
```

### Server debugging:
Debugging your server by using ```fetch()``` and writing countless ```console.log()``` statements is highly inefficient.

Instead you can use the free [ThunderClient](https://www.thunderclient.com/) VSCode extension. This extension allows you to send GET requests to any local route, and displaying the parsed response. 

It also allows you to send POST requests along with a JSON body. This allows you to send test data from your front-end to your back-end.


## Conclusion
After fully grasping all of this I went on to persue other web server concepts such as:
#### 
-   Passport.js authentication
-   Express sessions
-   Cookies
-   JSON/Cookie parsing
-   Status codes
-   POST request bodies
-   Using a database such as MongoDB

Overall, if you take the time to understand and apply these concepts, you will be able to launch a simple yet functional web server in a short time frame.