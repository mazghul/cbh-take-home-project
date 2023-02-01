# Refactoring

You've been asked to refactor the function `deterministicPartitionKey` in [`dpk.js`](dpk.js) to make it easier to read and understand without changing its functionality. For this task, you should:

1. Write unit tests to cover the existing functionality and ensure that your refactor doesn't break it. We typically use `jest`, but if you have another library you prefer, feel free to use it.
2. Refactor the function to be as "clean" and "readable" as possible. There are many valid ways to define those words - use your own personal definitions, but be prepared to defend them. Note that we do like to use the latest JS language features when applicable.
3. Write up a brief (~1 paragraph) explanation of why you made the choices you did and why specifically your version is more "readable" than the original.

You will be graded on the exhaustiveness and quality of your unit tests, the depth of your refactor, and the level of insight into your thought process provided by the written explanation.

## Your Explanation Here

###  Refactoring the Deterministic Partition Key Function
1. Convert the function to typescript as typescript functions are easier to understand as types are self explanatory.
2. Extracting the repeated logic for creating a hash to a separate function getHash
3. Extracting the logic for finding the candidate partition key to a separate function getCandidate
4. Returning the false condition first to reduce unnecessary condition checks.
5. Adding descriptive variable names and comments to explain the code's purpose
6. I also added unit tests to cover the existing functionality, so that I could be confident that my refactor doesn't break it. The tests check for the different cases in which the function could be called and the expected results, including corner cases such as falsy events and events with partition keys longer than the maximum length. This helps ensure the code's robustness and maintainability in the future.

(Please not as I have converted the function to typescript I have the changes in dpk.ts)
