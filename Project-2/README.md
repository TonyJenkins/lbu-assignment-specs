# Introduction to Programming

## Project 2: A Chatbot

### The Problem

In order to improve the service it offers to its students, the University of Poppleton is seeking to develop a new system for answering questions from prospective students, based on an interactive online chat.

The budget is tight, but a project has been started to develop a prototype. You will be working on this development.

#### Specification

*The following is deliberately vague, but should give you the general idea. You are encouraged to add your own features, and to develop the project in any way you find interesting.*

The program should start by prompting the user to enter their name. It should then display the name of the agent, who will then respond to questions. This should carry on until the user indicates that they wish to exit.

Of course, there are no real agents, so the name should be randomly generated. How the chat terminates is up to you, but having the user enter ``bye`` or similar is probably a good bet.

During the chat, the "agent" should spot key words in the questions. For example, if the user types a question including the word "coffee", the "agent" might respond with the opening times of the campus coffee bar. If the "agent" finds no interesting words in the question, it should just come up with some random response.

#### Requirements

For a pass, your program should:

1. Prompt the user to enter their name, and respond with a cheery greeting that includes the name.
1. Display the agent's name to the user (this will be a randomly generated name, perhaps chosen from a list).
1. Allow the user to enter questions, with no response.
1. Exit when the user enters ``bye``.

To improve on this, your program should:

1. Detect at least *four* key words in the user's question, and respond accordingly.
2. Print a random response if a key word is not found.
3. Include the user's name in some of the responses.
4. Exit if the user enters ``quit``, ``exit`` (or any similar string).

For top marks you could also:

1. Refactor the code so that the key words and responses can be configured *without* editing the program itself.
2. Complete the above using a well known format such as JSON or YAML (which will be easiest anyway).
3. Use the above to implement at least *ten* responses.
4. Mirror real-life chat systems by randomly disconnecting.
5. Create a log file of all the questions and answers in a session.
6. Add any other features that you find interesting, or even amusing.
