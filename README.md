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
        • Add a render() method to the Quiz class that returns a single <div>. For now, inside of that div, add the text Quiz.
    • Add a constructor() function to the Quiz class that has props as a parameter. Inside of that constructor, call the super() method and pass props as an argument.
    • Still inside of the constructor() function, set this.state equal to {quiz_position: 1}.
    • Now that we've got some data available in the component's state, inside of the single div in the render function of the component, remove the text Quiz, and replace it with a child <div> that has a className of QuizQuestion.
        • Inside of that div with a className of QuizQuestion, access the first element in the quiz_questions property of the quizData object, and display the instruction_text value.
    • Now that the Quiz component is displaying something, open up App.js, and import Quiz from ./Quiz.js.
    • Finally, still in app.js, in the render() function's return statement, replace the <div /> with a <Quiz /> component. Now when you run npm start and visit localhost:3000 in a web browser, you should see the text of the first question.

# Module 2 Steps   
Refactor the Quiz component to display quiz question data in a new component named QuizQuestion.

    • Create a new file in src/ named QuizQuestion.js.
    • Still in QuizQuestion.js, at the top of the file, import the React module and Component class from react.
    • Still in QuizQuestion.js, create a class named QuizQuestion that extends Component. After that component is created, add export default QuizQuestion as the last line of the file.
    • flip back over to Quiz.js and send over the quiz question data as a prop. To start, in Quiz.js import QuizQuestion from ./QuizQuestion.js at the top of the file near your other imports.
    • Still in Quiz.js, replace the entire div with a className of QuizQuestion with the <QuizQuestion /> component.
    • In that <QuizQuestion /> component, add a prop named quiz_question that passes the value of the quizData.quiz_questions array at the state's quiz_position minus 1. If you do this right, this will send data for the first question over to the QuizQuestion component.
    • Back in QuizQuestion.js, in the ul tag, add an li tag that displays the value of this.props.quiz_question.answer_options[0]
    • Finally, in the first section's paragraph tag, display the instruction_text from this.props. Now when you run npm start and visit localhost:3000 in a web browser, you should see the text of the first question and the text of one of the answer options.
    
# Module 3 Steps
Refactor the QuizQuestion component to display quiz answer buttons in a new component named QuizQuestionButton.

    • Create a new file in src/ named QuizQuestionButton.js.
    • In QuizQuestionButton.js, at the top of the file, import the React module and Component class from react.
    • Still in QuizQuestionButton.js, create a class named QuizQuestionButton that extends Component. After that component is created, add export default QuizQuestionButton as the last line of the file.
    • Still in QuizQuestionButton.js, in the return of the render() function, create a single li tag that has a single <button> tag as a child. Remember, the parent component has a ul, so you only need the li and button.
    • Flip back over to QuizQuestion.js and import QuizQuestionButton from ./QuizQuestionButton.js at the top of the file near your other imports.
    • Still in QuizQuestion.js, replace the li tag and value with the <QuizQuestionButton /> component.
    • Add a prop named button_text on that QuizQuestionButton component, and send this.props.quiz_question.answer_options[0] as the value.
    • Now that you're sending button_text as a prop, access that in QuizQuestionButton.js and place it as the text content of the <button> tag.
    
# Module 4 Steps
create a QuizEnd component that will display a reset quiz link after the quiz is completed.
    • Create a new file in src/ named QuizEnd.js.
    • In QuizEnd.js, at the top of the file, import the React module and Component class from react.
    • Still in QuizEnd.js, create a class named QuizEnd that extends Component. After that component is created, add export default QuizEnd as the last line of the file.
    • Still in QuizEnd.js, in the return of the render() function, add the following HTML <div> <p>Thanks for playing!</p> <a href=''>Reset Quiz</a> </div>
    • Now that we've got the QuizEnd component, open up Quiz.js again and import QuizEnd from ./QuizEnd.js at the top of the file near your other imports.
    • In the render() method's return statement, add the QuizEnd component on the line before the QuizQuestion component (but still a child of the main div).
    • We only want the QuizEnd component to display when the last quiz question has been answered. We can determine if we're at the last question by checking if the state's quiz_position minus 1 is identical to quizData.quiz_questions.length. Save the result of that check on a single line in a const named isQuizEnd NOTE: that const should be declared inside of the render() method, but above the return statement.
    • Write a condition in JSX that displays QuizEnd component if the isQuizEnd constant is true. If it is false, display QuizQuestion component keeping the quiz_question prop that's already there. Note: until we get the full logic set up, you can test if this is working by manually setting isQuizEnd to true or false.
