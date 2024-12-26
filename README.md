# Silent Failure in Async Dart Function

This repository demonstrates a common error in asynchronous Dart code:  failure to re-throw exceptions caught in `async` functions.  The `bug.dart` file contains code that fetches data from a remote API.  If the API call fails or encounters an exception, the error is printed but not re-thrown, leading to a silent failure. The `bugSolution.dart` file shows the corrected code. 

## How to reproduce

1. Clone the repository.
2. Run `bug.dart`. Observe that the error is printed to the console, but the function completes without explicitly signaling failure.
3. Run `bugSolution.dart` to see how to properly handle and re-throw exceptions for better error handling. 

## Solution

The solution involves re-throwing the caught exception using `rethrow` or explicitly throwing a new exception containing the original error information. This ensures that calling functions are properly notified of the failure and can take appropriate action. 