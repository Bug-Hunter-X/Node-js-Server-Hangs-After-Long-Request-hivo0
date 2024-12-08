# Node.js Server Hangs After Long Request

This repository demonstrates a common issue in Node.js applications where the server appears to hang after handling a request that takes a significant amount of time to process.  The issue stems from Node.js's single-threaded nature and the blocking of the event loop.

## Bug Description

The provided `bug.js` file contains a simple Express.js server.  A request to the root path initiates a 5-second delay before responding. During this delay, the server becomes unresponsive to new requests.  This behavior is because the event loop is blocked during the `setTimeout` call.

## Solution

The solution, shown in `bugSolution.js`, leverages asynchronous operations to prevent blocking of the event loop. By utilizing asynchronous techniques, the server remains responsive while handling long-running tasks.

## How to Reproduce the Bug

1. Clone this repository.
2. Run `node bug.js`.
3. Send a request to `http://localhost:3000`. Observe that the server becomes unresponsive until the 5 seconds have elapsed.

## How to Implement the Solution

1. Examine `bugSolution.js` to see the implementation of an asynchronous request handler.
2. Note the use of asynchronous functions to prevent blocking the event loop.