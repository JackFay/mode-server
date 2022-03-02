# Luhn Checksum Exercise

## Overview

Create a PHP program that outputs the validity of a number by applying the [Luhn Checksum](http://en.wikipedia.org/wiki/Luhn_algorithm).

***

**Input:**

The program should accept a single number to validate.
 
**Output:**

The program should output the input along with the validity of the number.
 
**Examples:**

Given an input of `79927398713`, the output should be:

```
79927398713 is valid.
```
 
Given an input of `79927398710`, the output should be:

```
79927398710 is not valid.
```

***

## File & Directory Structure

Please use the following file/directory structure for your submission:
```
.
├── src/
│   ├── main.php
│   └── <other files/directories as-needed>
├── test/
│   ├── luhn-test.php
│   └── <other files/directories as-needed>
├── README.md (place instructions for running your code and tests here)
└── backend-instructions.md (this file)
```

Your code should be able to be run by invoking `php ./src/main.php` or `php ./test/luhn-test.php`.

## Guidelines
### Dos:
Please do...
1. **Your best, but don't stress too much.** Please treat this as you would any other task you might encounter during your daily work, meaning deliver quality work on a deadline (try to complete this in 1-3 hours max).
1. **Test your code.** This means:
    - Include a few automated tests in `test/luhn-test.php` as indicated above.
        - This should be a simple PHP script that you create as a basic testing harnass.
        - No need to use any testing libraries or external tools beyond what is already included in PHP.
    - Include instructions on how to run your tests in the README.
    - Please note: Submissions without tests of some kind will **NOT** be reviewed.
1. **Make your code robust and clear.** This means:
    - Your code must gracefully handle invalid input and errors.
    - Your code must be clearly commented.
    - Your code must follow [PSR12: Extended Coding Style](https://www.php-fig.org/psr/psr-12/) guidelines.
3. **Review the "[Pre-Submission Checklist](#pre-submission-checklist)" below before submitting your work.**

### Dont's:
Please don't...
1. **Look up the solution online.** There are many solutions and code snippets online implementing the Luhn Checksum. Please resist using those. We want to see your coding style and approach to problem solving.
1. **Feel that you need to spend a great deal of time working on a solution.** Completing this exercise shouldn't take more than an hour or two.
1. **Use a framework.** That's overkill. The goal of this exercise is to verify basic coding proficiency within a reasonable amount of time. Stick to the file/directory structure given above and create only the classes/code you need to get the job done.
1. **Rush**. *Quality work is more important than speed*. Feel free to work on this exercise over the period of one to three days in order to ensure that your code checks all of the boxes in the "[Pre-Submission Checklist](#pre-submission-checklist)" below.

## Pre-Submission Checklist
- [ ] Review code quality:
    - [ ] Correct spelling
    - [ ] Formatting (indentation, spacing, etc.; refer to the [PSR12: Extended Coding Style](https://www.php-fig.org/psr/psr-12/))
    - [ ] Comments
    - [ ] Error handling
    - [ ] Invalid input handling
- [ ] Implement tests and ensure your code passes all of them
- [ ] Include a README explaining how to run/use your solution and any tests

## Credits

Adapted from: https://gist.github.com/tomharris/bc9a942bcd25e029e746
