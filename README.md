# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid or unexpected input.  Specifically, the provided code attempts to parse a user ID as an integer without checking if the input is a valid integer. This can lead to crashes or unexpected behavior.

The `bug.js` file contains the erroneous code. The `bugSolution.js` file provides a corrected version with improved error handling.

## Bug

The main issue is that the route handler doesn't validate the `userId` before attempting to parse it as an integer.  If the `userId` is not a valid integer (e.g., a string, a negative number), `parseInt(userId)` might return `NaN`, causing unexpected errors or crashes.

## Solution

The solution adds input validation to ensure that `userId` is a valid integer before attempting to use it.

This example uses a simple `isNaN` check, but more robust validation methods (e.g., regular expressions) might be necessary in real-world scenarios.  Proper error handling ensures that the server responds gracefully in case of invalid input.