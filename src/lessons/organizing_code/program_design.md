# Program Design

Take a look at these two programs.

- [Version One](https://replit.com/@kibocurriculum/ttt-inline)
- [Version Two](https://replit.com/@kibocurriculum/ttt-factored)

Explore them: run the code, read the code, and see what you can understand.

These programs have the same behavior! They are both different versions of
the Tic Tac Toe game. But, one program is better than the other.

What differences do you notice these programs? What makes one better than the other?

## Good Programs and Bad Programs

Writing good programs involves significant _judgement_. As you've seen, there
are tons of different ways to solve the same problem with code. Different
programmers have different opinions about what makes one solution better than
another. Still, there are some rules that are universal.

Here's one attempt at explaining what makes a good program:

```
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one -- and preferably only one -- obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

Of the two programs above,

* one was complex, the other _split code up to make each piece simple_
* one had functions that could be understood on their own, and the other didn't
* one was _readable_, the other was not

> What other tenets of the Zen of Python did the programs follow or violate?

## Factors of well-designed programs

What are the factors that make a program well designed or poorly designed? This
is a big topic, and one that you'll chew on for the rest of your programming
career.

The factors and techniques we're going to focus on right now are:
- splitting code into helper functions
- designing functions based on their inputs and outputs
- naming for variables and functions
- using documentation and comments to explain how our code works
- following the Python style guide
- using modules to organize our code

> Look back at some of the code you've written for your projects for the last few weeks. Which principles do you notice in your code? What improvements do you think you could make?