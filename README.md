# Unhandled Promise Rejection in Express.js Request Handler

This repository demonstrates a common error in Node.js Express.js applications: unhandled promise rejections within request handlers.  When an asynchronous operation inside a route handler fails, if error handling isn't properly implemented, the request hangs without a response, and the server silently logs the error.

The `bug.js` file contains the problematic code. The `bugSolution.js` file shows how to fix this issue using a `try...catch` block or ensuring that a response is always sent.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory in your terminal.
3. Run `npm install express` to install the necessary dependencies.
4. Run `node bug.js` to start the server.
5. Make multiple requests to `http://localhost:3000`.  You'll notice some requests hang indefinitely.

## Solution

The solution is to handle the rejection properly in the route handler, ensuring that a response is always sent to the client, even in case of an error.