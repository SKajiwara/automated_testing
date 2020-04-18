# Automated Tests
In software development, people typically wrtie production code along with test code. 

Basically, testing has three types, 
```
1. Unit test
2. Integration test
3. End to end test
``` 

End-to-end test is a manual test where testers repeat to use the UI over and over to find a bug. It is impossible to automate most of the time. Unit test and Integration test, however, are built onto the software.

The benefits of using automated tests:
```
1. Frequently testable, less time required
2. Catch a bug before deploying
3. Refactorying is easy; changing the structure of the code without changing the behaveor is easy
```
Unit Test
- Tests a unit of an application without its external dependencies

Integration Test
- Tests the application with its external dependencies as a whole ****can break easily as you make changes***

Test Pyramid 
- Tells you to have more unit tests if you have more algorithms.
```
    / \       Less - algorithm 
   /E2E\      
  /Integ\
 / Unit  \    More - algorithm
-----------
```
## Automated Test Tools for Node.js
The most popular libraries for testing are shown below.
```
1. Jasmine
2. Mocha + Chai + Simon
3. Jest
```
In this repository, it will be focused on Jest. See [documentation](https://jestjs.io/docs/en/getting-started.html) for more info.

Jest Installation
``` $ npm i jest --save-dev ```

Change Script in package.js
```script { "test" : jest }```

Name test files ***.test.js or .spec.js

Test Function has two names but the same fucntionality
```
In lib.test.js
Import function to add two numbers as adder

1. test('adding fucntion, () => {
    const result = lib.adder(5, 6)
    expect(result).toBe(11)
   })
2. it('addes two numbers', () => {
    const result = lib.adder(4, 6)
    expect(result).toBe(10)
   })
```

Other methods than expect(result).toBe()
- Truthiness
```
    .toBeNull()
    .toBeDefined()
    .not.toBeUndefined()
    .not.toBeTruthy()
    .toBeFalsy()
```
- Numbers
```
  expect(value).toBeGreaterThan(3)
  expect(value).toBeGreaterThanOrEqual(3.5)
  expect(value).toBeLessThan(5)
  expect(value).toBeLessThanOrEqual(4.5)

  // toBe and toEqual are equivalent for numbers
  expect(value).toBe(4);
  expect(value).toEqual(4);
  
  // For floating points
  const value = 0.1 + 0.2;
  // expect(value).toBe(0.3);        // This won't work because of rounding error
  expect(value).toBeCloseTo(0.3); // This works.
```
- Strings
```
    // There is no 'I' in 'team'
    expect('team').not.toMatch(/I/)

    // There is "stop" in Christoph
    expect('Christoph').toMatch(/stop/);
```
- Arrays and iterables
```
const shoppingList = [
  'diapers',
  'kleenex',
  'trash bags',
  'paper towels',
  'beer',
];

test('the shopping list has beer on it', () => {
  expect(shoppingList).toContain('beer');
  expect(new Set(shoppingList)).toContain('beer');
});
```
- Exceptions
```
    function compileAndroidCode() {
        throw new Error('you are using the wrong JDK')
    }

    test('compiling android goes as expected', () => {
        expect(compileAndroidCode).toThrow()
        expect(compileAndroidCode).toThrow(Error)

        // You can also use the exact error message or a regexp
        expect(compileAndroidCode).toThrow('you are using the wrong JDK')
        expect(compileAndroidCode).toThrow(/JDK/)
    })
```


