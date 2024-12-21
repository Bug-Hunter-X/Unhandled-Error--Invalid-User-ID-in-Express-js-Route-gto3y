# Express.js Unhandled Error: Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  failure to handle invalid input, specifically in this case, non-numeric user IDs.

The `bug.js` file shows the problematic code. The `bugSolution.js` file provides the corrected code with proper error handling.

## Bug

The original code attempts to parse the user ID from the request parameter as an integer and directly uses it to find a user. If the user ID is not a valid integer (e.g., a string or a non-numeric value), the `parseInt` function will return `NaN`, leading to a potential crash or unexpected behavior.

## Solution

The solution adds error handling to check if the parsed `userId` is actually a number using `isNaN`. If it's not a number, a 400 Bad Request response is returned, preventing the application from crashing and providing informative feedback to the client.
