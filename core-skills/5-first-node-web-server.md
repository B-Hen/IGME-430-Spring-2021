# Skill #5 - First Node Web Server

## I. Overview

- Last time we "imported" - using `require()` - an *external* library (aka "package") named `nanoid`
- this time we will use a *built-in* library called `http` to help us build a simple web server
- the properties and methods that we will use today are: 
  - [`http.createServer(listener)`](https://nodejs.org/api/http.html#http_http_createserver_options_requestlistener) - will create a new http web server for us, and any client requests that come in will be routed to `listener`
  - [`httpServer.listen(port)`](https://nodejs.org/api/http.html#http_server_listen) - the server will begin to listen on the `port` we provide
  - [`ClientRequest.url` and `ClientRequest.headers`](https://nodejs.org/api/http.html#http_class_http_incomingmessage) - incoming requests will have a `clientRequest` and a `httpResponse` object - the `.url` and `.headers` properties give us information about that client request
  - [`httpResponse.writeHead()`](https://nodejs.org/api/http.html#http_response_writehead_statuscode_statusmessage_headers) - where we specify the *http response headers* we want to send back
  - [`httpResponse.write()`](https://nodejs.org/api/http.html#http_response_write_chunk_encoding_callback) - where we specify the *content* we want to send back
  - [`httpResponse.end()`](https://nodejs.org/api/http.html#http_response_end_data_encoding_callback) - close the connection
- some other concepts that may come up:
  - What does a web server do? - *"The primary function of a web server is to store, process and deliver web pages to clients"* -  [Wikipedia - Web server](https://en.wikipedia.org/wiki/Web_server)
  - [Wikipedia - Port (computer networking)](https://en.wikipedia.org/wiki/Port_(computer_networking))
  - [JS Template Literals (Template Strings) - created with backticks (\``)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)
  - [JS Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
  - [Method Chaining in JS](https://medium.com/backticks-tildes/understanding-method-chaining-in-javascript-647a9004bd4f)
 
<hr> 
 
## II. The server

- The complete code for your first node web server is below:
  - Create a folder named **first-web-server**
  - Using a terminal program (GitBash/Powershell/Terminal) make that folder the *cwd* by `cd`ing into it
  - `npm init -y` - let's use the default values this time
  - edit the **package.json** file:
    - under the `"scripts"` key add a `"start"` key with the value of `node ./src/index.js`
  - in the **first-web-server** folder, create a **src** folder
  - create **index.js** and put it in the **src** folder


**src/index.js**

```js
// 1 - pull in the HTTP server module
const http = require('http'); 

// 2 - locally this will be 3000, on Heroku it will be assigned
const port = process.env.PORT || process.env.NODE_PORT || 3000;

// 3 - process.env is an environmental variable
// https://nodejs.org/dist/latest-v8.x/docs/api/process.html#process_process_env
//console.log(process.env);

// 4 - Here is the hard-coded web page we will send back
// note that we enclosed the string of HTML in back-ticks so that we could have a nicely formatted and readable multi-line string
const index = `	
<html>
  <head>
    <title>First Node Page</title>
  </head>
  <body>
    <h1>First Node Page!</h1>
  </body>
</html>`;

// 5 - this is the function that will be called every time a client request comes in
// note that in this course we'll be using arrow functions 100% of the time in our server-side code
const onRequest = (request, response) => {
  console.log(request.url);
  //console.log(request.headers);

  response.writeHead(200, { 'Content-Type': 'text/html' }); // send response headers
  response.write(index); // send content
  response.end(); // close connection
};

// 6 - create the server, hook up the request handling function, and start listening on `port`
http.createServer(onRequest).listen(port); // method chaining!

console.log(`Listening on 127.0.0.1: ${port}`);
```

<hr>

## III. Test the server

- Start up the app and our web server by typing `npm start`
- Check the console to be sure that the app is running on port 3000
- Head to `http://localhost:3000` - this will send a web page request to a local server running on port 3000
- Our default web page should now load and dispaky in the browser

<hr>

![screenshot](./_images/ss-20.png)

<hr> 
 
## III. Push the server to Heroku

### IV-A. Create a local GitHub repository

- In order to post this app to Heroku, we'll need to push it to a *remote* Git repository. To do this we'll first make a *local* Git repository
- To create a new local githib repository:
  - using GitBash/Powershell/Terminal, make **first-web-server** your *cwd*
  - type `git init`

### IV-B. Create a remote GitHub repository

### IV-C. Link the local and remote repository

### IV-D. Create an App on Heroku

### IV-E. Test it!

<hr> 

## V. Submission



<hr><hr>

| <-- Previous Unit | Home | Next Unit -->
| --- | --- | --- 
|   [Skill #4 - Hello Node](4-hello-node.md) |  [**IGME-430**](../) | Skill #6 TBA
