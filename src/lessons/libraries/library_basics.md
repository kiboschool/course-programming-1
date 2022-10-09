# 9.1 Libraries

Estimated Time: 30 Minutes

In this section, you will more about libraries, their usage and importance.

## What is a Library
We already talked about modules in python and how can we use external functions using the keyword `import`. At this section, we will take a closer look at this concept and in the next lesson, we are going to check main features of some known libraries in python.

Normally, a library is a collection of books or is a room or place where many books are stored to be used later. Similarly, in the programming world, a library is a collection of precompiled codes that can be used later on in a program for some specific well-defined operations. Other than pre-compiled codes, a library may contain documentation, configuration data, message templates, classes, and values, etc.

A Python library is a collection of related modules. It contains bundles of code that can be used repeatedly in different programs. It makes Python Programming simpler and convenient for the programmer. As we don’t need to write the same code again and again for different programs. Python libraries play a very vital role in many fields like Machine Learning, Data Science, Data Visualization, etc.

> **_Libraries & Modules_** A library is a collection of modules, but the terms are often used interchangeably, especially since many libraries only consist of a single module, so don’t worry if you mix them.

### Python Standard Library
The Python Standard Library is a collection of script modules accessible to a Python program to simplify the programming process and removing the need to rewrite commonly used commands. They can be used by 'calling/importing' them at the beginning of a script.

The following are among the most important:
- time
- sys
- os
- math
- random
- pickle
- urllib
- re

> Look up each of these libraries. Read about what the library is for.

> Check the list of all standard library modules at http://www.python.org/doc/

## Using modules

Use `import` to load a library module into a program’s memory. Then refer to things from the module as `module_name.thing_name`
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

### Install a Library

Some libraries are not part of standard Python, so you need to install them using `pip`.
`pip install <library>`

You need to check the documentation for the needed library to get the correct pip command.

## Library Contents
How would we then check functions within a specific library? We can use the keyword __help__

`help(string)` would show the following:

```
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
We can use from __<module>__ import __<method>__ to load only specific items from a library module. Then refer to them directly without library name as prefix.
```
from string import ascii_letters

print('The ASCII letters are', ascii_letters)
```
Output:
```
The ASCII letters are abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
```

## Import with Alias
An alias is a name tag that is given to a module where you can use it withing your code. Use import ... as ... to give a library a short alias while importing it.
Then refer to items in the library using that shortened name.

Example:
```
import string as s
print(s.capwords('capitalise this sentence again please.'))
```
Output:
`Capitalise This Sentence Again Please`

Alias is useful for libraries that are frequently used or have long names. E.g., The __pandas__ library is often aliased as __pd__.

> **_NOTE:_** Alias can make programs harder to understand, since readers must learn your program’s aliases.

## General Examples

> **_Exploring a Library:_**
>> **Practice Question:** What function from the os library can you use to determine the current working directory?
>>
>> **Solution:** Using help(os) we see that we’ve got `os.getcwd()` which returns a string representing the current working directory.


> **_Using the correct method withing a Library:_**
>> **Practice Question:** Given the variables year, month and day, how would you generate a date in the standard iso format:
`year = 2016, month = 10, day = 22`
>> - Which standard library module could help you?
>> - Which function would you select from that module?
>> - Try to write a program that uses the function.
>>
>>**Solution:** The datetime module seems like it could help you. You could use date(year, month, date).isoformat() to convert your date
>> `import datetime`
>> `iso_date = datetime.date(year, month, day).isoformat()`
>> `print(iso_date)`


> **_Ways to import a library:_**
>> **Practice Question:** Match the following print statements with the appropriate library calls
>> Library calls:
>> A) from string import digits
>> B) import string
>> C) import string as s
>> Print commands:
>> 1. print(list(s.digits))
>> 2. print(list(digits))
>> 3. print(string.ascii_uppercase)
>>
>> **Solution:**
>> A2) Importing digits from string provides the digits methods B3) Importing string provides methods such as ascii_uppercase, but requires the string. syntax. C1) Importing string with the alias s allows s.digits