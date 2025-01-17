# Objective-C Memory Leak in Exception Handling

This repository demonstrates a common error in Objective-C related to exception handling and memory management. The example shows how a memory leak can occur if allocated memory is not released within a `try-catch` block when an exception is thrown.

The `bug.m` file contains the faulty code, while `bugSolution.m` provides a corrected version.

## Bug
The primary issue is the lack of proper resource management (memory release) within the `@catch` block. If an exception is thrown, `myObject` is not released, leading to a memory leak.

## Solution
The solution involves using an `@finally` block to ensure that `myObject` is released regardless of whether an exception is thrown or not. This guarantees that the memory is always deallocated, preventing leaks.