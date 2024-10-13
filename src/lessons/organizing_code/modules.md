# Modules

In Python, **modules** are files that contain code that's ready for us to use.

Here are a few examples:

- The `random` module that we previously used to generate random numbers.
- The `cmath` module offers complex mathematical functionality.
- The `csv` module is for reading and writing tabular data to and from delimited files.
- The `email` module supports *parsing, manipulating, and generating email messages.*
- The `scikit-learn` library contains modules for machine learning work.

There are tons of modules and libraries out there. When you need to implement some feature and you don't know how, you can search for a module that provides these functions for you.

You can also write your own modules, like the `utilities` module from the first example in the discussion of helper functions.

## Importing Modules

To use a module, you’ll need to `import` it using Python’s module system. You’ve used `import` before, for code like this:

```python
import random
random_number = random.randint(0, 100)
print(random_number) # 76 (when I ran it - different each time)
```

`random` is a **module** with useful functions like `randint`, which generates a random number. Modules are python’s way of grouping related functions.

## Importing from modules you wrote

You've seen how to import from external modules like `random`. But what about importing functions from your own code?

You can import functions from other files within your project using `import` too.

Imagine that you have a file called `utilities.py` where you have the following function:

```python
def square_area(length, width):
    return length * width
```

You can import this helper function from another file by using the name of the file it's from:

```python
# (in main.py)
from utilities import square_area

result = square_area(10, 20)
```

Since `square_area` is in the file `utilities.py`, you can import it using `from utilities`. The name of the file is where you import from.

> Note: If you take a look at how the tests work in your exercises, they often import code from `main.py` to test.

## Renaming imports

If you want to use a different name for something you import, you can change the name using `as`. For example:

```python
from utilities import square_area as sq

result = sq(10, 20)
```

### dir() built-in function

One way to know what functions does a module provides is by using the built-in function `dir()`

For example, run this snippet to see all the variables and functions in the `random` module:

```python
import random

print("The contents of the random library are:")
print(dir(random))
```

When I run this, I see:

```python
The contents of the random library are:

['BPF', 'LOG4', 'NV_MAGICCONST', 'RECIP_BPF', 'Random', 'SG_MAGICCONST',
'SystemRandom', 'TWOPI', '_BuiltinMethodType', '_MethodType', '_Sequence',
'_Set', '__all__', '__builtins__', '__cached__', '__doc__', '__file__', '__loader__',
'__name__', '__package__', '__spec__', '_acos', '_ceil', '_cos', '_e', '_exp',
'_inst', '_log', '_pi', '_random', '_sha512', '_sin', '_sqrt', '_test', '_test_generator',
'_urandom', '_warn', 'betavariate', 'choice', 'expovariate', 'gammavariate', 'gauss',
'getrandbits', 'getstate', 'lognormvariate', 'normalvariate', 'paretovariate', 'randint',
'random', 'randrange', 'sample', 'seed', 'setstate', 'shuffle', 'triangular', 'uniform',
'vonmisesvariate', 'weibullvariate']
```

This is a lot of output! `dir()` doesn't explain what any of those variables or
functions do, but you can look up the documentation for any of the ones that
seem interesting.

## Reading the Docs

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