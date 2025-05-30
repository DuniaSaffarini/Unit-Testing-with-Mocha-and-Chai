# Unit-Testing-with-Mocha-and-Chai
Mocha

Mocha is a JavaScript testing framework that runs in both the browser and Node.js, making it ideal for both unit and integration tests. In this course, we will focus on using it specifically for unit testing.

Unit Tests
Applications are large pieces of software with many moving parts, making it challenging to pinpoint issues. Unit tests help break the application into smaller pieces, focusing on individual modules or functions and ensuring they work in isolation.

Mocha Coding Example
When Mocha tests are run, they execute within the Mocha test runner environment.

To run tests, Mocha requires them to be in a file ending with .test.js, such as mytest.test.js, which is typically kept in a test folder.

Each test includes a describe block to define a test suite and an it block to define a test case.

Describe Block:

A function that takes two arguments:
A string describing the test suite.
A callback function that contains all the test cases for the suite.
It Block:

Similar to a describe block, it takes two arguments:
A string describing the test case.
A callback function that contains the test logic. The callback in an it block is where the main logic resides. It includes:
Setting up the test, such as calling the code being tested and preparing any arguments or mock data.
An assertion, which verifies the test results to ensure the code behaves as expected.
Mocha offers many additional features, including functions to execute blocks of code before and after test suites, specialized functionality to handle asynchronous methods, and much more. For a deeper dive, check out the Mocha Documentation.(opens in a new tab)

Chai

Mocha comes with some built-in assertion methods, but we can use an assertion library like Chai to expand functionality.

Chai provides methods like expect and should that allow us to chain other methods and create more specific assertions.

In the example below, we use expect, to, and equal to assert that the result variable is expected to equal 10:


expect(result).to.equal(10)
See the Chai documentation for more assertions: Chai Documentation The test suite below tests a function that validates user input for a password. The password must be at least 12 characters long and contain special characters.


describe("Password Validator", () => {

                          it("should return true for a valid password", () => {

                            const validPassword = "StrongPass123!";

                            expect(passwordValidator(validPassword)).to.be.true;

                          });



                          it("should return false for a password shorter than 12 characters", () => {

                            const shortPassword = "Short1!";

                            expect(passwordValidator(shortPassword)).to.be.false;

                          });



                          it("should return false for a password without a special character", () => {

                            const noSpecialChar = "NoSpecialChar123";

                            expect(passwordValidator(noSpecialChar)).to.be.false;

                          });



                          it("should return false for an empty password", () => {

                            const emptyPassword = "";

                            expect(passwordValidator(emptyPassword)).to.be.false;

                          });

});


ummary
In this exercise, you will create unit tests using Mocha and Chai.

Resources
Mocha Documentation(opens in a new tab)
Chai Documentation(opens in a new tab)
Instructions
src/fizzBuzz.js includes a function we will be testing with Mocha.

1. Install Mocha and Chai
Open the terminal and enter the following command to install Mocha and Chai as development dependencies:
npm install mocha chai --save-dev
2. Create a Test File
Create a new file in the testing folder called fizzBuzz.test.js.
3. Build the Testing Suite
Import Chai and the function to be tested:
const { expect } = require("chai");
const fizzBuzz = require("../src/fizzBuzz.js");
Note: Mocha is a test runner and does not need to be imported.

Create a describe block for your test suite:
describe("FizzBuzz Function", () => {
// Test cases will go here
});
4. Create a Test Case
Inside the describe block, create an it block for a specific test case:
describe("FizzBuzz Function", () => {
it("Should return 'FizzBuzz' if the input is divisible by 3 and 5", () => {
// Assertions will go here
});
});
5. Add an Assertion
Call the fizzBuzz function, passing 15 as an argument, and save the result to a variable:
const result = fizzBuzz(15);
Use Chai's expect to make an assertion:
expect(result).to.equal("FizzBuzz");
Full test case:
describe("FizzBuzz Function", () => {
it("Should return 'FizzBuzz' if the input is divisible by 3 and 5", () => {
const result = fizzBuzz(15);
expect(result).to.equal("FizzBuzz");
});
});
6. Run Your Tests
Add a test script to your package.json:
"scripts": {
"test": "mocha"
}
Open the terminal and run:
npm run test
You should see output like this:
FizzBuzz Function
✔ Should return 'FizzBuzz' if the input is divisible by 3 and 5

1 passing (3ms)
7. Add More Test Cases
Repeat steps 4–6 for the following scenarios:
Numbers divisible by 3 should return "Fizz".
Numbers divisible by 5 should return "Buzz".
Non-number inputs should return false.
Use the Chai Documentation(opens in a new tab) to explore other assertions and methods for validation.