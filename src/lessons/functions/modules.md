# Modules

In Python, **modules** are files that contain code that's ready for us to use.

Here are a few examples:

- The `random` module that we previously used to generate random numbers.
- The `cmath` module offers complex mathematical functionality.
- The `csv` module is for reading and writing tabular data to and from delimited files.
- The `email` module supports *parsing, manipulating, and generating email messages.*
- The `scikit-learn` library contains modules for machine learning work.

There are tons of modules and libraries out there. When you need to implement some feature and you don't know how, you can search for a module that provides these functions for you.

## Importing Modules

To use a module, you’ll need to `import` it using Python’s module system. You’ve used `import` before, for code like this:

```python
import random
random_number = random.randint(0, 100)
print(random_number) # 76 (when I ran it - different each time)
```

`random` is a **module** with useful functions like `randint`, which generates a random number. Modules are python’s way of grouping related functions.

## What functions does a module provide?

To find the functions that a module provides, you can use Google, or look at the documentation (”docs”) for that module.

[https://docs.python.org/3/library/random.html#module-random](https://docs.python.org/3/library/random.html#module-random) is the link to the docs for the `random` module. Click it to see everything there is to know about `random`.


### 📖 Tips for Reading Documentation

- Documentation covers *everything.* You probably only need a small part. Skim, search, and scan to find what you actually need
- Sometimes it’s helpful to just see the name of a function, then try it out to see what it does.
- Function descriptions in documentation look like this:

    > **random.choice(*seq*)**
    >
    >
    > Return a random element from the non-empty sequence *seq*. If *seq* is empty, raises `[IndexError](https://docs.python.org/3/library/exceptions.html#IndexError)`.
    >

    This one means you can pass a sequence (like a list) into the `choice` function provided by the `random` module, and it will return a random element from the list.

### What modules are available?

You can use Google to find a Python module, or look at the [index of all built-in modules](https://docs.python.org/3/py-modindex.html). There’s a lot of modules, so you might scan it now, then just Google it when there’s something in particular that you need.

Lots of modules are not built into python — they’re written by other developers. In order to use modules that aren’t built in, you need to install them so that they are available to `import`.

Later on, you'll learn how to install external libraries, and practice using some of the most common and powerful libraries, like `requests` and `flask`.

## Modules you’ll use

In the “Distance Traveled” practice, you’ll need to import the `math` module to use the `math.sqrt` function. In the "Quick Draw" practice, you imported the `random` module to generate random numbers, and the `time` module to measure how long things take.

In the past, students have used modules for special features in their projects, such as:

- the `requests` module to interact with data over the web
- the `gtts` module for text-to-speech
- the `termcolor` module to change the color of the text output
- various modules for drawing images and figures