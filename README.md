## Running React on Repl.it

[React](https://reactjs.org/) is a popular JavaScript library for building user interfaces.

[Vite](https://vitejs.dev/) is a blazing fast frontend build tool that includes features like Hot Module Reloading (HMR), optimized builds, and TypeScript support out of the box.

Using the two in conjunction is one of the fastest ways to build a web app.

### Getting Started
- Hit run
- Edit [App.jsx](#src/App.jsx) and watch it live update!

By default, Replit runs the `dev` script, but you can configure it by changing the `run` field in the [configuration file](#.replit). Here are the vite docs for [serving production websites](https://vitejs.dev/guide/build.html)

### Typescript

Just rename any file from `.jsx` to `.tsx`. You can also try our [TypeScript Template](https://replit.com/@replit/React-TypeScript)

# Module 1 Steps
    • Create a new file in src/ named Quiz.js
    • In the first line of the file, add the line import React, { Component } from 'react' to make React functions available in this file.
    • On the third line of the file, add the statement let quizData = require('./quiz_data.json')
    • Create a class named Quiz that extends Component. After that component is created, add export default Quiz as the last line of the file.
