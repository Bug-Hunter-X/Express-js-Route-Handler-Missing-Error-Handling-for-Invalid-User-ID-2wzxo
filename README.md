# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the code attempts to parse a user ID from the request parameters but fails to handle cases where the ID is not a valid integer.

## Bug

The `bug.js` file contains the erroneous code.  It fetches a user based on the ID provided in the URL. However, if the ID is not a number (e.g., a string or null), `parseInt(userId)` will return `NaN`, leading to the `find()` method returning `undefined`. This results in no user being found and may lead to unexpected behavior or crashes. 

## Solution

The `bugSolution.js` file provides a corrected version that includes proper error handling. The solution adds a check to see if `parseInt(userId)` returns `NaN`, returning a 400 Bad Request error in such a case.