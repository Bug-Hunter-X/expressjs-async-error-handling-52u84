# Silent Crash: Unhandled Promise Rejection in Express.js

This repository demonstrates a common but often overlooked error in Express.js applications: unhandled promise rejections within request handlers.  The code simulates an asynchronous operation that can fail.  Without proper error handling, the server crashes silently, making debugging difficult.

The `bug.js` file shows the problematic code.  The `bugSolution.js` file provides a corrected version with robust error handling.

## Problem
The original code lacks a `catch` block to handle potential errors from the asynchronous `someAsyncOperation` function.  If this operation rejects, the promise rejection goes unhandled, leading to a silent crash of the Express.js server.

## Solution
The solution includes a comprehensive `catch` block within the request handler to gracefully handle errors.  This prevents the application from crashing and allows for appropriate error responses to the client, along with logging for debugging.