# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid or unexpected input.  Specifically, the example code attempts to parse a user ID from a route parameter as an integer without any validation or error handling.

## Bug

The `bug.js` file contains the buggy code.  It fetches a user from an array based on the ID passed in the route parameter. However, if the ID is not a valid number, `parseInt(userId)` will return `NaN`, leading to the `users.find()` method failing silently or throwing an error depending on the implementation.  This can cause unexpected behavior in the application. 

## Solution

The `bugSolution.js` file provides a corrected version of the code. It includes error handling to check if the `userId` is a valid number and returns appropriate error responses for invalid input.  This makes the application more robust and less prone to unexpected crashes.

## How to reproduce

1. Clone the repository.
2. Run `npm install` to install Express.js.
3. Run `node bug.js`. 
4. Make a request to `/users/abc` (an invalid ID).  Observe the behavior (likely an error or undefined behavior).
5. Run `node bugSolution.js` and try again.  Observe the improved handling of invalid input.