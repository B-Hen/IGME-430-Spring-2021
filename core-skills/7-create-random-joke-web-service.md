# Skill #7 - Create Random Joke Web Service

## I. Overview
- For today's skill, you will port a simplified version **random-jokes.php** (seen in [Core Skills #1](./1-client-tools-and-http-protocol.md)) from PHP to JavaScript/Node.js, and then post it to Heroku
- Here is what the "done" version looks like:
  - Random Joke -->
  - note that it returns a *single random joke*, so it is simpler than both **random-jokes.php** and the **random-number** web service from last time
  - 404 Page --> 
- There are no notes or videos for this "skill", but here are some tips:
  - create a new folder named **random-joke** and `cd` into it
  - `npm init -y`
  - add a "start" key to "package.json"
  - create a **src** folder, and go ahead and copy over the **index.js** file from last time if you really want to, but:
    - the app will have a **/random-joke** endpoint that returns JSON formatted as in the example linked above, and it will return a "404 - file not found" page for all other endpoints (i.e. paths or file names)
    - you MUST delete all unnecessary code
      - that means you need to delete all of the "index page" code
      - because you also don't need to parse any query parameters, you MUST delete the `querystring` `require()` and any dependent code
      - also comment out any `console.log()` statements
   - You must have at least 10 jokes, with a `q` and an `a` property just like in the **random-jokes.php** service:
     - go ahead and copy the jokes from that assignment, but be aware that you need to convert the PHP associative array syntax over to JavaScript object literal syntax
     - we also had an array of jokes in the correct JS format in 330 - you can use those if you wish
  - after you get this working, post it it Heroku like we did in the last 2 assignments
  
  <hr>
  
  ## II. Submission
     

<hr><hr>

| <-- Previous Unit | Home | Next Unit -->
| --- | --- | --- 
|   [Skill #6 - First Node Web Service](6-first-node-web-service.md) |  [**IGME-430**](../) | Skill #8 - TBA
