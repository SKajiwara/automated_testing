# Automated Tests
In software development, people typically wrtie production code along with test code. 

Basically, testing has three types, 
```
1. Unit test
2. Integration test
3. End to end test
``` 

End-to-end test is a manual test where testers repeat to use the UI over and over to find a bug. Unit test and Integration test, however, are built onto the software.

The benefits of using automated tests:
```
1. Frequently testable, less time required
2. Catch a bug before deploying
3. Refactorying is easy; changing the structure of the code without changing the behaveor is easy
```
Unit Test
- Tests a unit of an application without its external dependencies
Integration Test
- Tests the application with its external dependencies as a whole ***can break easily as you make changes
Test Pyramid 
- Tells you to have more unit tests if you have more algorithms.
```
    / \       Less - algorithm 
   /E2E\      
  /Integ\
 / Unit  \    More - algorithm
-----------
```
