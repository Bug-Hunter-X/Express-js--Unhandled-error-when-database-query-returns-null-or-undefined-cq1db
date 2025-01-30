# Express.js Unhandled Error with Null or Undefined User Data

This repository demonstrates a common error in Express.js applications where a database query returns null or undefined data, leading to an unhandled error and application crash. The bug and a solution are provided below.

## Bug
The bug lies in the `/users/:id` route handler. If the database query fails to find a user with the given ID, it returns null or undefined. The code then tries to send this null/undefined value as a response, resulting in an error.

## Solution
The solution involves adding a check to ensure the `user` object is valid before sending it as a response. If `user` is null or undefined, a proper 404 response is sent to the client.