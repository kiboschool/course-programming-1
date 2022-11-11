# Readability

Especially as you work on larger and larger projects with more and more teammates, _code readability_ becomes more and more critical. But, what does it mean for code to be readable? You'll learn a few different strategies for

## Comments

So far, you've used comments to explain your code as you've written it. As you've probably seen, some comments are very useful, and others are just taking up space, without helping you understand what is happening. Adding _long_ comments can hurt readability more than it helps!

You should continue to use comments to help organize your thoughts and understand how your code works as you write it. As you learn more, you'll likely find that you will write fewer comments, and they will be more targeted at parts of your code that are surprising or _deserve_ an explanation, rather than sprinkled everywhere.

## Docstrings

Python has a special syntax for comments that document a function, called a _docstring_.

A docstring is a string written as the first statement of a function that explains the function, its parameters, and its return value.

Docstrings can be one line or multiple lines, depending on how much information they include.

Here's a one-line docstring explaining a function:
```python
def divide(a, b):
    """This function divides the value of a by b and returns a float result"""
    return a / b
```

Longer docstrings add an explanation of each argument as well as the return value

```python
def divide(numerator, denominator):
    """
    This function divides the numerator by the denominator and returns the result without attempting any type conversion.


    :param numerator: (float) the value to be divided
    :param denominator: (float) the value to divide by; the divisor

    :returns: (float) result of numerator divided by the denominator
    """
    return numerator / denominator
```

This example specifies the parameters and return values in the common [Sphinx documentation style](https://sphinx-rtd-tutorial.readthedocs.io/en/latest/docstrings.html). Based on docstrings formatted this way, Sphinx can automatically build pages of documentation.

You can read more about docstrings in [PEP 257 - Docstring Conventions](https://peps.python.org/pep-0257/), or see an example of the [Google Documentation format](https://www.sphinx-doc.org/en/master/usage/extensions/example_google.html).

## Naming

Names should strive to be:

- short
- meaningful
- unambiguous

Coming up with a good name for a function, variable, or argument can be hard!

When possible, avoid names that don't mean anything. When you can, also avoid naming variables after the type of data that they are, unless you are writing a function that is generic to that data type.

- Bad: `def greet(s)`
- Bad: `def greet(string)`
- Better: `def greet(person)`
- Good: `def greet(name)`

It's sometimes helpful to name functions with _verbs_ and name variables with _nouns_, since functions usually represent actions. This isn't always the case. It's true for functions like `List.append()` but not for conversion functions like `int()`.

> [Naming Conventions](https://peps.python.org/pep-0008/#naming-conventions) from the PEP8 style guide is an interesting read. Naming is hard, even for the people who designed Python!

## Readable code

What about the code itself? How do you make it so that your code is easy to read?

First, you should follow the Python style conventions. These help other Python coders read your code, since it will look like 'standard' Python.

There are lots of recommendations to follow, like:
- Use blank lines to separate your functions, but keep the body of the function together
- Use lower_snake_case for function and variable names
- Put imports at the top of your file

The full list of recommendations is called [PEP8](https://peps.python.org/pep-0008/), but it's too long to memorize all at once.

Instead of memorizing all of them, you can configure your editor to format your code for you, and detect any issues using a _linter_. See the [VSCode docs on formatting](https://code.visualstudio.com/docs/python/editing#_formatting) and [linting](https://code.visualstudio.com/docs/python/linting) for help to configure your editor.

But, just following the style guide will not be enough to write code that is readable! You can still write confusing code while remaining compliant with PEP8 and the auto-formatter.

From the Zen of Python:

```
Simple is better than complex.
Flat is better than nested.
```

Try to write functions that do fewer things, and do things in simple ways when possible.

Try to avoid code that is complicated. One obvious sign of complicated code is the level of _nesting_. If you have lots of loops and if statements nested inside of each other so that the code is indented many times, then you know that the code is pretty complicated!

## Type Annotations

When we write Python functions, it's often helpful to know the data types of the parameters and return values.

Python lets us add type annotations that specify the types of the values:

```python
# No type hints
def greeting(name):
  return f'Hello, {name}'

# With type annotation
def greeting(name: str) -> str:
  return f'Hello, {name}'
```

In the Python interpreter, these won't change anything. If you run `greet(4.5)` it will still do the same thing. However, there are tools like [mypy](http://mypy-lang.org/), [pyright](https://github.com/microsoft/pyright), and [pydantic](https://pydantic-docs.helpmanual.io/) that can verify that functions are called with the correct kinds of arguments. That can help avoid common issues like passing in a string where there is supposed to be a number.

Why would you use type hints?

- **Faster Development:** Type annotation will uncover mistakes more quickly and protects from passing wrong values.
- **Users of your code:** Type hints can make your funcitons more clear for anyone reading or using your code.
- **Documentation:** Type hints can be part of your documentation. Some people even consider it the whole documentation of the function!

> Type hints are a relatively new feature in Python. You can read more about the rationale for adding the feature here: https://peps.python.org/pep-3107/

We won't cover how to write type annotations in this course, but you can read more about them, and you'll see more in future courses.