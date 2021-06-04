# CIT 281 lab 04

## Outcome:

This lab was out intro to webservers and using fastify. 
We created a fastify web server that displayed text on the webpage.       
We were then able to parse the url request parameters to update the webpage text.
## Code: 
**[Here](https://github.com/Myles-P-D/cit281-lab04/blob/main/lab-04.js)** is the full code and below is an excerpt of creating the webserver.
```javascript
const fastify = require("fastify")();
// Handle GET verb for / route using Fastify
// Note use of "chain" dot notation syntax
fastify.get("/", (request, reply) => {
  reply
    .code(200)
    .header("Content-Type", "text/html; charset=utf-8")
    .send("<h1>Hello from Lab 4!</h1>");
});

// Route for /name
fastify.get("/name", (request, reply) => {
    const {first, last} = request.query
    
    const name = first && last ? `${first} ${last}` : `Guest`;
    reply
      .code(200)
      .header("Content-Type", "text/html; charset=utf-8")
      .send(`<h1>Hello, ${name}</h1>`);
  });
  ```

## Images: 
Here is an image of the webpage displaying text for an unidentified user.   
    
    
![guest image](https://github.com/Myles-P-D/cit281-lab04/blob/main/guest.png?raw=true "guest image")

