Palindrome Checker

Overview

This C++ program checks if a given passage of text contains palindromic sequences. It analyzes the input passage to determine:

Whether the entire passage is a palindromic sequence of lines.
The number of palindromic lines within the passage.
The number of palindromic words within the passage.

Features

Palindrome Detection for Lines: Determines if the sequence of lines in a passage reads the same forwards and backwards.
Palindrome Detection for Words: Counts the number of words in the passage that are palindromes.

Requirements

C++ compiler (e.g., g++)
Standard C++ libraries

### Project Structure

- **main.cpp**: The main program file that contains the implementation of the palindrome checker.
- **myStack.h**: Header file defining the stack class used in the program.
- **stackADT.h**: Abstract data type header file required by `myStack.h`.
- **queueAsArray.h**: Header file defining the queue class used in the program.
- **queueADT.h**: Abstract data type header file required by `queueAsArray.h`.

Build Instructions

Ensure you have a C++ compiler installed.
Clone the repository to your local machine:

git clone https://github.com/JWar959/palindrome-checker.git
cd palindrome-checker

Compile the program using the following command:

g++ -o palindromeChecker main.cpp
Make sure queueAsArray.h, myStack.h, queueADT.h, and stackADT.h are included in your project directory.

Usage

To run the program, use the following command:

./palindromeChecker
When prompted, input your passage line by line. Type end on a new line to finish input.

Example:

Enter the passage (type 'end' on a line by itself to finish):

A man a plan a canal Panama
Madam in Eden I'm Adam
Never odd or even
end

Example Output

The passage is a palindromic sequence of lines!
Number of palindromic lines: 3
Number of lines in the passage: 3
Number of palindrome words in the passage: 5

How It Works

The program uses two custom data structures:

Queue (queueAsArray): To maintain the sequence of lines for comparison.
Stack (myStack): To reverse the order of lines or words for palindrome checking.

Contributing
If you wish to contribute, please fork the repository and submit a pull request. Feel free to open issues for any bug reports or feature requests.

Contact
For any questions or feedback, please contact john.warren959@gmail.com
