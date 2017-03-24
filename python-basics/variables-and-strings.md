# Variables and Strings

Variables are one of the basic building blocks of Python code. We’ll look at some of these - what they look like, what they can do.

But before we start, let’s talk about bugs.  Bugs are errors that either stop your code from running, or make it run in ways that you weren’t expecting. 

You will meet many bugs when you’re coding. Don’t let them scare you: dealing with bugs is just one of the features of coding. You can do things to make this easier: for instance, if you use an editor like sublimetext to write your code, it has handy features like changing the colour of your code when you write something incorrectly.

These are not the same: 

`print('Hello World!')`

`print(‘Hello World!’)`

`print('Hello World!’)`

**Beware the quote characters!** If you cut and paste code from text files \(like these slides\), you might see one of these error messages:

* SyntaxError: Non-ASCII character '\xe2' in file helloworld.py on line 1
* SyntaxError: invalid character in identifier
* SyntaxError: EOL while scanning string literal
* SyntaxError: invalid syntax

This happens because the symbols “ and ” above aren’t the same as the ones in your code editor.  It’s annoying, but easily fixed: just delete them and type “ and ” in the right places in the editor.

## Comments

`# This is a comment`

`print('Hello World!') # this is a comment too`

Coders leave messages for each other \(and themselves\) in their code: these are called comments. They’re there for humans to read, and are completely ignored by the python interpreter. 

The comments you’ll see in this course are mostly the ones that start with the ‘\#’ symbol. Everything from the ‘\#’ to the end of the line it’s on is a comment.

You might see "magic comments" in python files, e.g.

**`#!/usr/bin/python`**

**`# -*- coding: utf-8 -*-`**

These tell the interpreter which type of file this is \(python\), and which character set it uses \(remember the problem with ‘“‘ earlier?\). utf-8 is a very commonly-used character set.

## Variables

`my_string = 'Hello World!'`

`my_boolean = True`

`my_number = 10`

`type(my_number)`

`my_number = 15.523`

Variables are places where you put objects that you don’t want to keep typing out. You do this because

1. you don’t have to keep typing “Hello World” when you use it several times in your code
2. it’s easier to read your code and see what’s going on
3. it’s harder to make mistakes \(e.g. if you put “10” everywhere in your code, and change your mind, then you might change some but not all of those “10”s to “11s”… if you put x=10 and then use x everywhere, you only have to change one thing\).

Variables have “types” that tell the interpreter what can be done with them \(e.g. you can multiply numbers together, but you can’t do that with strings\). Here are some common variable types:

* String: a set of characters, which could be letters, numbers or symbols.
   Strings can be as long as you like - in some datasets \(e.g. reading in book texts\) you’ll see strings thousands of characters long.
* Boolean: can be either True or False.
   Useful for when you want to do one thing if something is true \(e.g. x == 10\), and something else if it isn’t.
* Numbers: a number.
   This include integers \(e.g. 10\), and floating-point number \(e.g. 15.523\).

Note how I reused the same variable name for two numbers. Try typing my\_number = 10, then print\(my\_number\), then my\_number=15.523, then print\(my\_number\) in ipython. 

## Strings

`my_string = 'Hello World!'`

`len(my_string)`

`my_string[4]`

Strings are a bit special. A string is made out of characters \(e.g. “H” or “r”\), so it makes sense to ask things like:

* len\(string\): how many characters are there in this string?
* my\_string\[4\]: what’s the 5th character in this string? \(NB python counts from 0, not 1, e.g. my\_string\[0\] is H\).

## Functions

`my_string = 'Hello World!'`

`stringlength = len(my_string)`

`lowstring = my_string.lower()`

`print('{} is a number. My string is {}'.format(15.2, lowstring))`

Functions are pieces of code that \(often\) do something that gets repeated lots. We already met the function “print\(\)”. Here are some more functions.

Functions generally have 3 parts: the function name \(e.g. “len”\), the function arguments \(e.g. “my\_string”\) that tell the function what to do its thing on, and the the function return \(e.g. stringlength\), which is the variable \(or variables\) that the function puts its results into.

You can use ‘string formatting’ to put other variables \(numbers, other strings etc\) into a string. Here, we’ve put a number \(15.2\) and a string \(“Hello World!”\) into a new string, and printed it. print\(“{}”.format\(x\)\) is very very useful for printing out more-complicated variables, where a simple print\(x\) will fail.

### Writing your own functions

`def my_function(my_text):`

`    new_text = my_text + ’ bananas'`

`    return new_text`

`new_sentence = my_function('sara likes')`

`print(new_sentence)`

`print(my_function(“Let’s eat some”))`

You can write your own functions using the keyword “def”. Here, we’ve created a function \(my\_function\) that takes an argument called my\_text, adds some more text to it, puts that new text into variable new\_text, and returns new\_text to the person who called the function.

Then we use the function. We call my\_function with the argument “sara likes “: my\_text is now set to “sara likes “ before we add “bananas” to it. The function returns “sara likes bananas”, which is put into the variable new\_sentence.

