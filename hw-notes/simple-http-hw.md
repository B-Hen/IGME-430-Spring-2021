# Simple HTTP HW Notes

## I. Overview

- The PDF for this HW is in myCourses
- *In this assignment, you will use Node.js to build a simple HTTP server to server HTML, text and JSON. The server will accept several different URLs and make a choice of what to return based on the URL.*
- This HW assignment walks though building an HTTP server similar to what we did in Core Skills #1-#7, and should reinforce much of what we covered there
- It also adds the following - we will elaborate on much of this in class:
  - rather than building a Node.js project from scratch, there is substantial start code that you will *fork* from an existing repository
  - you will be installing *developer dependencies* (e.g. packages) to your node project:
    - this will allow us to run ESLint - https://www.npmjs.com/package/eslint - which will periodically (whenever we type `npm test`) check our code for code quality issues
    - we will be following the Airbnb's base JS Style Guide:
      - https://www.npmjs.com/package/eslint-config-airbnb-base
      - https://github.com/airbnb/javascript
  - you will write "test" and "pretest" scripts in your **package.json** file
  - you will periodically run `npm test` to validate your code
  - rather than have all of the JS code in 1 file like we have been doing, you will split it up into 4 files (modules):
    - **server.js**, **htmlResponses.js**, **jsonResponses.js** and **textResponses.js**
    - you will use `module.exports` to give each module a "public" interface
    - you will then `require()` them where their functions are needed
  - rather than having your HTML pages hard-coded in the JS, you will instead use `fs.readFileSync()` to load them from separate files
  - this HW uses CircleCI (Continuous Integration, see handout in myCourses)
     
<hr>

## II. Tips & Hints

1) You will be ***forking*** the start code:

    - https://github.com/IGM-RichMedia-at-RIT/Simple-HTTP-Assignment-Start
    - the **fork** button is in the upper right corner of the repository screen
    - when you fork an exisitng repository you create a copy of it in your own account
    - once you have created this new (forked) repository you can `git clone` it
    - we covered git cloning in [Skill #3 - Command-line Git & Cloning Repositories](../core-skills/3-command-line-git.md)
