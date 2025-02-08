# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in a request handler can cause the server to hang and become unresponsive.  The provided `bug.js` file shows the problematic code. The solution, in `bugSolution.js`, illustrates how to handle such operations asynchronously using promises or async/await to prevent blocking the event loop.

## Problem

Node.js is single-threaded, meaning it uses a single thread to handle all requests. When a long-running synchronous operation occurs in a request handler, the entire event loop blocks, preventing the server from responding to other requests.  This results in server unresponsiveness and potential crashes.

## Solution

The solution is to handle long-running operations asynchronously using promises or async/await.  This allows the event loop to continue processing other requests while the long-running operation executes in the background.