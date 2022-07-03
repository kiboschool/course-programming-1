# Programs and comments

_Estimated Time: 20 minutes_

---

Everything on the computer is a program behind the scenes.

At this very moment, you are reading on a computer, with a web browser. The browser is a program, built by a large team. But, how do they actually do it? What does a program look like when they are writing it? How does it work?

This is the question we'll focus on first: **What are computer programs?**

In <a href="/future-proof-with-python/admissions-challenge.md" target="_blank">Intro to Programming in Python </a> you learned...

- Programming languages let us write instructions for computers using words
- Programming languages get translated into 1s and 0s the machine understands
- Python is a beginner-friendly language that has tons of real-world use
- You can make basic programs in Python using `print`, `input`, `+`, and `=`

Let’s review.

## Programs are...

> **Programs are text that a computer can execute as instructions.**

That means you can read them and write them with the keyboard.

Programs use special symbols and keywords. The symbols and the order they have to go in is called the **syntax**.

If a program has valid syntax, then the computer can run it. If the program has the right logic, it will do what the programmer wanted. The syntax, grammar, and vocabulary make up a **Programming Language**.

We're learning Python, so we're going to learn what words and symbols are allowed in Python, and how to structure them to make the computer do what we want.

## How do you write programs?

We need two things to start writing programs of our own:

1. A **Text Editor**: A tool to write text
2. An **Interpreter or a Compiler:** A tool to translate your code to computer-executable programs.

In this course, we're going to use <a href="https://replit.com/" target="_blank">Replit</a>, because it has both of those pieces: a **text editor** and an **interpreter**.

Replit also has other helpful features that we'll use: multiplayer mode, comments, sharing, and assignments.

### Plain text vs. Rich text

> Why not use something like Google Docs to write code?

Google docs is awesome for writing formatted text. It's got highlighting, different fonts, sizes, alignment, tables, and lots of different options for formatting.

But... Python doesn't understand any of that formatting. **Python only understands the text.** That's true of most programming languages: they only consist of text.

Google docs is known as a "_Rich Text Editor_". It's the text, plus the formatting.

For programming, we use something called a "Plain Text Editor", or just "Text Editor". That means we can't use bold, center, or other formatting options. We only type the characters and symbols.

But... in the examples above, the code has colors!?

Text Editors for programming have features like **Syntax Highlighting** that display your code in color to help you. The colors aren't saved with the code, and you can't change them word-by-word. Replit has built-in features like Syntax Highlighting, so you don't have to worry about it as long as you're using Replit.

## Code Comments

> **Programs are written and read by people.**

That means that when writing code, we prioritize **both** making the computer do what we want **and** making sure someone else can understand what the code means.

We can help others make sense of our code through its structure, and with comments.

<aside>

<img src="../instruction.png" alt="../instruction.png" width="40px" /> Watch this video to learn about comments.

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.youtube.com/embed/7AihnEjsglc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## Comments

In the example below, the first two lines are **code comments**.

```python
# Prints "Programming" ten times
# string * number copies the string that many times
message = "Programming"
number_of_copies = 10
print(message * number_of_copies)
```

To make programs do what we want, we have to read them, write them, and edit them **together**. We use comments to communicate with the other people that may need to read and understand our code. While code can sometimes make sense on its own, comments fill gaps in explanation.

In Python, comments start with the `#` character (called ‘hash’ or ‘octothorp’). Anything after the `#` gets ignored by Python - it won’t try to run it as code.

In Kibo, we’ll often use comments to explain code and to illustrate what code does. When you see a snippet like:

```python
print(message * number_of_copies) # ProgrammingProgrammingProgrammingProgrammingProgrammingProgrammingProgrammingProgrammingProgramming
```

The comment is explaining the result of running that line of code.

<aside>

Next up: [Variables and Assignment](/future-proof-with-python/working-with-data/variables-and-assignment.md)

</aside>
