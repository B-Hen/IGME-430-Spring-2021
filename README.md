# IGME-430-01 (Spring 2021)

## I. Mission

<blockquote>
"Students will create and deploy <i>full-stack</i> web apps that are <i>secure</i> and <i>persistent</i>, while following <i>industry standard development practices</i>"
</blockquote>
  
- *Full-stack* means that the app has both client-side and server-side components
- *Secure* means that the apps will utilize a login system, encryption, and data validation
- *Persistent* means that app data will be cached both locally and in "the cloud" so that it can be recovered by the user at a later date
- *Industry standard development practices* means utilizing common build tools and workflows (automatic server rebooting, automatic code analysis aka linting, continuous integration, transpiling et al), testing, version control, and implementing MV* software design patterns both "from scratch" and by using current popular frameworks

<hr><hr>

## II. Projects

### Project 1 - API Portal

- Functionality
  - Web Services:
    - #1 - Custom Web API (Read):
      - uses HTTP `GET` method
      - returns data in JSON format
      - public facing, and CORS is turned on
      - takes at least 2 parameters
      - example: 
        - *"Get Jokes" API with `limit` and `minrating` parameters*
        - endpoint: `/get-jokes?limit=5&minrating=3`
        - data stored in hard-coded array of object literals - `allJokes`
    - #2 - User submitted data API (Write):
      - uses HTTP `POST` method
      - takes at least 2 body parameters
      - response:
          - sends back proper HTTP status codes ex. `201 Created`
          - send back created resource
          - sends back in either JSON or XML depending on `accept` request header of client
      - example: 
        - *"Suggest Joke" API with `q` and `a` parameters*
        - endpoint: `POST /suggest-joke?q=setup&a=punchline&username=abc1234`
        - adds the submitted data to a `userSuggestions` array - the data is in object literal format
    - #3 - User submitted data API (Read):
      - uses HTTP `GET` method
      - takes at least 1 parameter
      - example:
        - returns contents of `userSuggestions` array
        - endpoint: `/get-suggestions?sort=latest`
  - HTML Pages:
    - #1 - Home Page:
      - "landing page" for API - should look nice
      - describes API
      - has documentation of API functionality
      - simple demonstration of API usage
      - example: 
        - gives examples of `/get-jokes` endpoints, with and without parameters
        - *shows a random joke from the "Get Jokes" API, the `q` only, every time the page is reloaded*
    - #2 - Suggestion Page
      - HTML `<form>` for users to input data and send it to the **JSON "write" API** above
      - example: 
        - *users can suggest data for the API by submitting a setup and punchline for a joke*
    - #3 - Admin Page
      - login functionality not required
      - shows the entire contents of the **User submitted data API (Read)** above
      - example:
       - calls and displays `/get-suggestions?sort=latest`
    - #4 - Client Page
      - demonstrates API (Web Service #1) in action
      - has controls to show all features of API
      - example:
        - calls `/get-jokes?limit=5&minrating=3`
  - Server Code Style
    - multiple CommonJS code modules
    - all pages/files "served" by your Node.js server
  - Client Code Style
    - VanillaJS
    - ES6 Modules
    - Global Navgation System (HTML)
    - External CSS file(s)
- Client-side Technologies
  - VanillaJS
- Server-side technologies
  - ephemeral server-side data
- Developer Tools
  - `eslint`
  - `nodemon`
  - Continuous Integration via CircleCI

<hr>

### Project 2 - Product/Service App VueJS

- Functionality
- Client-side Technologies
  - Vue.js
- Server-side technologies
  - Express
  - MongoDB (NoSQL)
- Developer Tools
- Server Code Style:
  - MVC - router style

<hr>

### Project 3 - Product/Service App ReactJS

- Functionality
- Client-side Technologies
  - React
- Server-side technologies
  - Express
  - MongoDB + Mongoose
  - User Authentication
  - In Memory Datastore/caching - Redis
- Developer Tools
  - Testing (Assertions)

<hr>
