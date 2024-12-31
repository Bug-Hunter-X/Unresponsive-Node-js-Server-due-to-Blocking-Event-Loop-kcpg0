# Unresponsive Node.js Server

This repository demonstrates a common Node.js issue where a long-running operation in the request handler blocks the event loop, making the server unresponsive. The `bug.js` file contains the problematic code, while `bugSolution.js` provides a solution using asynchronous operations.

## Problem

The `bug.js` server simulates a long-running operation (a 5-second CPU-bound loop) within the request handler.  During this time, the server cannot handle any other requests, leading to unresponsiveness and potentially causing timeouts for clients.

## Solution

The `bugSolution.js` file demonstrates a solution using asynchronous programming.  Instead of blocking the event loop, it uses `setTimeout` or promises to schedule the long operation, allowing the event loop to continue processing other requests during the waiting period.