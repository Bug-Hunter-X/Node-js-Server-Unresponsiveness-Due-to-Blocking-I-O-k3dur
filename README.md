# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js applications: server unresponsiveness caused by blocking the event loop with a long-running synchronous operation.

The `server.js` file contains a simple HTTP server that simulates a long-running task within the request handler.  This blocks the event loop, preventing the server from processing other requests.  The solution (`serverSolution.js`) demonstrates how to use asynchronous operations or worker threads to prevent this.

## How to Reproduce

1. Clone this repository.
2. Run `node server.js`.
3. Make several requests to `http://localhost:3000`. You will observe that after one request the server will take a long time to respond or not respond at all to subsequent requests.
4. Run `node serverSolution.js`. You will see the solution that avoids blocking the main thread.