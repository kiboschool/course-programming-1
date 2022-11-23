# Libraries

In this section, you'll learn more about libraries and how to use them.

## What is a Library?

You've used the keyword `import` to access external modules. Now, you'll take a closer look at how programmers use code written by other people.

A library is a collection of code that can be used in other programs for specific operations. Other than code, a library may contain documentation, configuration data, message templates, classes, values, and more.

A Python library aims to make programming simpler and more convenient for the programmer. We don’t need to write the same code again and again for different programs.

Python libraries play a vital role in many fields like Machine Learning, Data Science, Data Visualization, and Web Development. As you learn more about those fields, you'll become familiar with the modules that are most often used in those fields.

> **Libraries & Modules** A library is a collection of modules, but the terms are often used interchangeably, especially since many libraries only consist of a single module. Don’t worry if you mix them up.

## The Standard Library

The Python Standard Library is a collection of modules accessible to every Python program to simplify the programming process. You have used the Standard library by importing modules at the beginning of your scripts.

The following are among the most common:
- random
- time
- json
- math
- os
- urllib
- re

> **Exploration**
> * Look up the documentation each of the libraries listed. What is each library for?
> * See the list of all standard library modules at [http://www.python.org/doc/](http://www.python.org/doc/).
>   What other modules are you curious about?

## Using modules

Use `import` to load a module into your program. Then, you can use items from the module as `module_name.thing_name`
Python uses `.` to mean “part of”.

Here's an example using the `string` module, a standard library module for common string operations:

```
import string

print('The lower ascii letters are', string.ascii_lowercase)
print(string.capwords('capitalise this sentence please.'))
```

Output:
```
The lower ascii letters are abcdefghijklmnopqrstuvwxyz
Capitalise This Sentence Please.
```

## Installing Libraries

Only some libraries are part of the Python Standard Library that come with every
Python installation. They need to be downloaded onto your computer in order to
use them.

Python has a built-in package manager called `pip` for installing external libraries.

You can install a library by running this terminal command:

```sh
python -m pip install <library>
```

Usually, the documentation for a library will tell you the name of the library
to pass into `pip`, often in a section called "Installation" or "Getting
Started".

## Try it: install a library with pip

The [requests](https://requests.readthedocs.io/en/latest/) library is helpful
for fetching data from the web.

Install it with:

```sh
python -m pip install requests
```

Then try it out. Start a `python` repl, then import and use the library:

```python
$ python
>>> import requests
>>> r = requests.get('https://api.github.com/events')
>>> r.text
```

There's a big blob of JSON data there, fetched from Github!

> Note: installing libraries can get messy. Ask for help in Discord if you
> encounter any issues with library installation.

## Library Contents

You use the keyword `help` to show the contents of a library once it's installed.

`help(string)` would show the following:

```txt
Help on module string:

NAME
    string - A collection of string constants.

MODULE REFERENCE
    https://docs.python.org/3.6/library/string

    The following documentation is automatically generated from the Python
    source files.  It may be incomplete, incorrect or include features that
    are considered implementation detail and may vary between Python
    implementations.  When in doubt, consult the module reference at the
    location listed above.

DESCRIPTION
    Public module variables:

    whitespace -- a string containing all ASCII whitespace
    ascii_lowercase -- a string containing all ASCII lowercase letters
    ascii_uppercase -- a string containing all ASCII uppercase letters
    ascii_letters -- a string containing all ASCII letters
    digits -- a string containing all ASCII decimal digits
    hexdigits -- a string containing all ASCII hexadecimal digits
    octdigits -- a string containing all ASCII octal digits
    punctuation -- a string containing all ASCII punctuation characters
    printable -- a string containing all ASCII characters considered printable
```

## Specific Imports

You can use `from __<module>__ import __<method>__` to load only specific items 
from a library. Then you can refer to them without the library name as prefix.

```python
from string import ascii_letters

print('The ASCII letters are', ascii_letters)
```

Output:
```
The ASCII letters are abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
```

## Import with alias

An alias is an alternate name given to a module in your program, using the `as`
keyword.

Use `import ... as ...` to give a library a short alias while importing it.

```python
import string as s
print(s.capwords('capitalise this sentence again please.'))
```

Output:
```txt
Capitalise This Sentence Again Please
```

Aliasing is useful when a library is used frequently, or if it has a long name. 

For example, the `pandas` library is often aliased to `pd`, since data
scientists use the library so much!

> **Note:** Like all names, aliases can make programs harder to understand, 
> since readers must learn your program’s aliases.

## Try it: Exploring Libraries

Try answering each of the following questions about libraries, using the lesson
above and the documentation.

> **Question:** What function from the `os` library can you use to determine the 
> current working directory?
>
> **Solution:** Using help(os), see that `os.getcwd()` returns the current working directory.

> **Question:** Given the variables year, month and day, how would you generate 
> a date in the standard ISO date format?
> - Which standard library module could help you?
> - Which function would you select from that module?
> - Try to write a program that uses the function.
>
> **Solution:** The datetime module could help. 
>   You could use `date(year, month, date).isoformat()` to convert your date
>
> ```python
> import datetime
> iso_date = datetime.date(year, month, day).isoformat()
> print(iso_date)
> ```

> **Question:** Match the following print statements with the import statements
> needed to make them work.
>
> _Import statements:_
>
> A. `from string import digits`
>
> B. `import string`
>
> C. `import string as s`
>
> _Print statements:_
> 1. `print(list(s.digits))`
> 2. `print(list(digits))`
> 3. `print(string.ascii_uppercase)`
>
> **Solution:**
> * A == 2: Importing `digits` from string provides the digits methods
> * B == 3: Importing `string` provides methods such as `ascii_uppercase`, with the `string.` prefix. 
> * C == 1: Importing `string` with the alias `s` allows `s.digits`
