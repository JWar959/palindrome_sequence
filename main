
#include <iostream>
#include "queueAsArray.h"
#include "myStack.h"
#include <string>
#include <vector>


using namespace std;


bool isPalindrome(const vector<string>& passage, int& palindromeLineCount) {
    queueType<string> linesQueue;
    stackType<string> linesStack;
    bool isPalindromeLine = true;

    for (const string& line : passage) {
        string noSpaceLine; // Create a new string for each line
        bool isSpace = false;

        for (char c : line) {
            if (isalpha(c)) {
                c = toupper(c);
                noSpaceLine += c;
                isSpace = false;
            } else if (c == ' ' || c == '\n') {
                if (!isSpace) {
                    noSpaceLine += c;
                    isSpace = true;
                }
            } else {
                noSpaceLine += ' '; // Replace all other punctuations with a space
                isSpace = true;
            }
            if (c == '\n') {
                linesQueue.addQueue(noSpaceLine);
                linesStack.push(noSpaceLine);
                noSpaceLine.clear();
            }
        }

        linesQueue.addQueue(noSpaceLine);
        linesStack.push(noSpaceLine);
    }

    while (!linesQueue.isEmptyQueue() && !linesStack.isEmptyStack()) {
        string compareLineStack;
        string compareLineQueue;
        for (char c : linesStack.top()){
            if (isalpha(c)){
                compareLineStack+= c;
            }
        }
        for (char c : linesQueue.front()){
            if (isalpha(c)){
                compareLineQueue += c;
            }
        }
        if (compareLineQueue != compareLineStack) {
            isPalindromeLine = false; //
        }
        if (compareLineQueue == compareLineStack){
            palindromeLineCount++;
        }
        linesQueue.deleteQueue();
        linesStack.pop();
        compareLineQueue.clear();
        compareLineStack.clear();
    }

    return isPalindromeLine;
}


int isPalindromeWord(const vector<string>& passage) {
    stackType<string> WordsStack;
    string noSpaceLine;



    int palindromeWordCount = 0;

    for (const string& line : passage) {
        noSpaceLine = noSpaceLine + line + ' ';
    }

    cout << "No space line " << noSpaceLine << endl;

    bool isChar = false;
    string word;

    for (const char c : noSpaceLine) {
        if (isalpha(c)) {
            word += c;
        }
        if (c == ' ') {
            if (!isChar) {
                WordsStack.push(word);
                cout << "Word is " << WordsStack.top() << endl;
                word = "";
                isChar = true;
            }
        } else {
            isChar = false; // Reset the isChar flag when you encounter a non-alphabetic character
        }
    }

    
    while (!WordsStack.isEmptyStack()) {
        queueType<char> charQueue;
        stackType<char> charStack;

        for (char c : WordsStack.top()) {
            charQueue.addQueue(c);
            charStack.push(c);
        }

        bool isPalindrome = true; // Assume it's a palindrome until proven otherwise

        while (!charQueue.isEmptyQueue() && !charStack.isEmptyStack()) {
            if (charQueue.front() != charStack.top()) {
                isPalindrome = false; // Set to false on a mismatch
                break; // Exit the loop on mismatch
            }

            charQueue.deleteQueue();
            charStack.pop();
        }

        if (isPalindrome) {
            palindromeWordCount++;
        }

        WordsStack.pop();
    }

    return palindromeWordCount;

}


int main() {
    vector<string> passage;
    string line;
    int palindromicLines = 0;
    int passageLines = 0;
    int palindromeWords = 0;


    cout << "Enter the passage (type 'end' on a line by itself to finish):\n";


    while (true) {
        getline(cin, line);

        if (line == "end") {
            break;
        }
        passageLines++;
        passage.push_back(line);
    }

    if (isPalindrome(passage, palindromicLines)) {
        cout << "The passage is a palindromic sequence of lines!" << endl;
    } else {
        cout << "The passage is not a palindromic sequence of lines." << endl;
    }
    cout << "Number of palindromic lines: " << palindromicLines << endl;

    cout << "Number of lines in the passage: " << passageLines << endl;

    palindromeWords = isPalindromeWord(passage);

    cout << "Number of palindrome words in the passage: " << palindromeWords << endl;



    return 0;
}



