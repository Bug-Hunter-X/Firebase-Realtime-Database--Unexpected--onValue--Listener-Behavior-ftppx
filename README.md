# Firebase Realtime Database: Unexpected onValue Listener Behavior

This repository demonstrates a subtle bug related to the inconsistent triggering of the `onValue` listener in Firebase's Realtime Database. Under certain network conditions or with concurrent updates, the listener might fire multiple times, leading to unexpected data duplication or overwriting.

The `firebaseBug.js` file reproduces the problematic behavior.  The `firebaseBugSolution.js` file offers a solution using promises to ensure data consistency.

## Reproducing the Bug

1.  Ensure you have a Firebase project set up and have the necessary credentials.
2.  Clone this repository.
3.  Run `npm install firebase` to install the Firebase SDK.
4.  Replace placeholders in `firebaseBug.js` with your Firebase configuration.
5.  Run `node firebaseBug.js` and observe the console output.  You'll likely see duplicated or inconsistent data updates.

## Solution

The solution involves using promises or async/await to properly handle the asynchronous nature of the database operations and manage the timing of data updates. See `firebaseBugSolution.js` for the corrected code.