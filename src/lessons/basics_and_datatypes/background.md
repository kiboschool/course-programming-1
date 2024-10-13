# What is a program?

Everything you do on the computer has a computer program — “software” — behind the scenes.

We write computer programs to help us solve problems or perform tasks, like editing documents, browsing web pages, sharing images, or chatting with friends.

Everything on a computer is a program behind the scenes.

This very moment, you are reading on a computer, with a web browser. The browser is a program, built by a large team. But, how do they actually do it? What does a program look like when they are writing it? How does it work?

This is the question we'll focus on first: **What are computer programs?**

- Programming languages let us write instructions for computers using words
- Programming languages get translated into 1s and 0s the machine understands
- Python is a beginner-friendly language that has tons of real-world use
- You can make basic programs in Python using `print`, `input`, `+`, and `=`

## Programs are...

> **Programs are text that a computer can execute as instructions.**

That means you can read them and write them with the keyboard.

Programs use special symbols and keywords. The symbols and the order they have to go in is called the **syntax**.

If a program has valid syntax, then the computer can run it. If the program has the right logic, it will do what the programmer wanted. The syntax, grammar, and vocabulary make up a **Programming Language**.

We're learning Python, so we're going to learn what words and symbols are allowed in Python, and how to structure them to make the computer do what we want.

## Translating for machines

Underneath the screens and keyboards, computers are mechanical. They only understand 1s and 0s. But, _people don’t think in 1s and 0s_! When you want something, you use words.

So, how do we tell computers what we want them to do, like “send a message” or “show this webpage”?

We need a **translator**.

_Programming languages let us write instructions for computers using words_. Those words translate into instructions that the machine understands (1s and 0s). Then, we can type something like “send a message”, and it’ll get translated into something like `00011101001010001 001010010001001 101000010010100 10001010001010100000 01001010010`, which will make the computer send the message.

### A Very Picky Translator

Programming languages are **very picky** about what you type in. You can’t actually type in `send a message` — the programming language wouldn’t understand! Instead, it would be more like `send_message("Hello!")` . The program has to be crafted precisely, with lots of attention to detail, so that the programming language knows _exactly_ what you mean.

Programming languages only understand a **few specific words and symbols**, in a **few specific combinations**. Those words, symbols, and combinations are the **vocabulary, grammar and syntax** of a programming language — and that’s what you’ll learn in this course!

## What is Python?

Python is a programming language. You can write Python code, and then it will turn into instructions the computer understands and runs.

Here’s a small program that prints out 10 copies of the word “Programming”.

```python
message = "Programming"
number_of_copies = 10

print(message * number_of_copies) # ProgrammingProgrammingProgrammingProgrammingProgrammingProgrammingProgrammingProgrammingProgrammingProgramming
```

As you can see:

- It uses words, like `message` and `print` and numbers like `10`
- It uses symbols like `=` , `*`, and `()`
- The words and symbols are arranged in a particular order

### What is python used for?

- Python is a **general purpose programming language**, which means it’s a good fit for a wide variety of problems.
- Python is popular for **data science**, **mathematics**, **web development**, and more. It’s commonly used for “scripting” - small programs to do specific tasks.
- Python is a widely recommended language for beginners. The syntax is not as hard to get started with as some other languages, and you can build cool, real-world projects with it.

## How do you write programs?

We need two things to start writing programs of our own:

1. A **Text Editor**: A tool to write text
2. An **Interpreter or a Compiler:** A tool to translate your code to computer-executable programs.

In this course, we recommend using VSCode as your text editor, and the built-in
terminal for VSCode to run the Python interpreter.

We'll also use Replit for other helpful features: multiplayer mode and sharing.

<details>
<summary>
<strong>Further Exploration: Plain text vs. Rich text</strong>
</summary>

> Why not use something like Google Docs to write code?

Google docs is awesome for writing formatted text. It's got highlighting, different fonts, sizes, alignment, tables, and lots of different options for formatting.

But... Python doesn't understand any of that formatting. **Python only understands the text.** That's true of most programming languages: they only consist of text.

Google docs is known as a "_Rich Text Editor_". It's the text, plus the formatting.

For programming, we use something called a "Plain Text Editor", or just "Text Editor". That means we can't use bold, center, or other formatting options. We only type the characters and symbols.

But... in the examples above, the code has colors!?

Text Editors for programming have features like **Syntax Highlighting** that display your code in color to help you. The colors aren't saved with the code, and you can't change them word-by-word. Replit has built-in features like Syntax Highlighting, so you don't have to worry about it as long as you're using Replit.

</details>

## A Brief Tour of Python

Over the next few weeks, you’ll learn about Python in more detail.

First, we'll quickly illustrate some of the basics, to get you started.

## Comments: Explaining your code

> **Programs are written and read by people.**

That means that when writing code, we prioritize **both** making the computer do what we want **and** making sure someone else can understand what the code means.

We can help others make sense of our code through its structure, and with comments.

<summary><strong>📺 Watch this video to learn about comments.</strong></summary>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.youtube.com/embed/7AihnEjsglc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

In the example below, the first two lines are **code comments**.

```python
# Prints "Programming" ten times
# string * number copies the string that many times
message = "Programming"
number_of_copies = 10
print(message * number_of_copies)
```

Comments communicate with the other people that read our code. While code can sometimes make sense on its own, comments fill gaps in explanation.

In Python, comments start with the `#` character (called ‘hash’ or ‘octothorp’). Anything after the `#` gets ignored by Python - it won’t try to run it as code.

In Kibo, we’ll often use comments to explain code and to illustrate what code does. When you see a snippet like:

```python
# prints message lots of times
print(message * number_of_copies)
# => ProgrammingProgrammingProgrammingProgrammingProgrammingProgrammingProgrammingProgrammingProgramming
```

The comments explain the result of running the code.

### Print: Showing output from your program

The easiest way to make your program display some result is to use `print`.

Here’s an example:

```python
print("This is the output")
```

The program would output:

```
This is the output
```

- You use the keyword `print`
- Then parentheses
- Inside the `( )` you put the value you want to show
- Text has to go in inside quote marks `" "`

To run code in line with the lessons, we'll use Trinket,

Click the ▶️ button to run the program and see the output.

<div style="position: relative;">
<iframe src="https://trinket.io/embed/python/a709bfd326" width="100%" height="300" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
</div>

<aside>

💡 Try to change the text between the `" "` and run the program again by clicking the green 'Run' button. Notice the output in the Console window.

If you want more than one line of output, you can use more than one `print`.

```python
print("This is line 1")
print("This is line 2")
print("This is line 3")
```

Try editing the code to print more than one line.

</aside>

### Variables: Storing values to reuse

You can give a value a name, and use it later, using a variable.

```python
message = "I love programming"
print(message)
print(message)
print(message)
```

`message` is a variable. It stores the value `"I love programming"`.

The equals sign `=` assigns the value to the variable.

The program would output:

```text
I love programming
I love programming
I love programming
```

Click the ▶️ button to run the program and see the output.

<iframe src="https://trinket.io/embed/python/90601e3027" width="100%" height="300" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

### Adding things together with `+`

In Python, you can add things together with the `+` operator.

```python
print(10 + 10) # 20
print(10 + 154) # 164
print(12345 + 23456) # 35801
```

Computers are good at arithmetic — they are very fancy calculators.

Python can also add text together with `+`:

```python
message = " loves programming"
print("Adesola" + message)
print("Chidi" + message)
print("Ebbe" + message)
```

The program would output:

```
Adesola loves programming
Chidi loves programming
Ebbe loves programming
```

Click the ▶️ button to run the program and see the output.

<iframe src="https://trinket.io/embed/python/fee059f28c" width="100%" height="300" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

### Input: get some data from the user

Python can ask the user to type in a message using `input`.

```python
favorite = input("What is your favorite thing? ")
print("I like " + favorite + " too!")
```

When the program sees `input`, it prints the message and waits for the user to enter their response. Then, it continues from there.

The variable `favorite` stores the value that the user typed in.

If the user typed in `playing soccer`, then the output would look like:

`What is your favorite thing? playing soccer`
`I like playing soccer too!`

When you run this program, be sure to click in the “Result” box to type a response, and press Enter.

<iframe src="https://trinket.io/embed/python/f1b1832ddc" width="100%" height="300" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## In summary

- Programming languages get translated into 1s and 0s the machine understands
- Python is a beginner-friendly language that has tons of real-world use
- You can make basic programs in Python using `print`, `input`, `+`, and `=`
