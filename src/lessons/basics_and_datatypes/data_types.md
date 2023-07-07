# Data types

## What you need to know about data types

- Python can store different **types** of data
- The basic types of data you’ll learn about first are:
  - Strings
  - Integers
  - Floats
  - Booleans
- Python can do different operations based the data type
  - like `+` to add numbers together

## Basic Data Types

Your name, age, date of birth, and photo are different pieces of data. Data, and the variables that refer to them, are represented by different _types_.

Every programming language has data types, but the built-in types are different from one programming language to another. In Python, we have more than 10 built-in data types. Here are the 3 types we need in this lesson:

- **int** (for integer)
  - Represents integer numbers, like `1`, `4`, or `10`
- **float** (a floating-point number)
  - Represents floating-point numbers, like `1.0`, `4.32`, or `10.189`
  - You might know these as ‘decimal’ numbers or fractions - numbers that have a dot separating the integer part from the fractional part.
- **str** (for string)
  - Stores text as character-based data like words, e.g., `Hello World`

These are called _primitive types_. Python can represent more complicated data using _compound types_ like List and Dictionary, which are made out of the primitive types. We’ll learn about some of those in later lessons.

Python figures out the type automatically based on some rules:

- numbers without a decimal point are treated as **ints** (like `10`)
- numbers with a decimal point are treated as **floats** (like `1.0`)
- text between quote marks is treated as **strings** (like `"Hello"` or `'100.5'`)

There are more rules for other types, but we're skipping them for now.

## Video: Data Types

<aside>

📺 Watch this video to learn about data types.

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.youtube.com/embed/xvmPtqoEBn8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## Data Types

Every value in Python has a type, for example, **string**, **float**, and **integer**. You can find out what type a value is by using the `type()` function.

### Strings

**Strings** are for representing text.

They look like this: `"Kibo School"`, starting and ending with `"`, the _double quote_.

When you add them together with `+`, Python _concatenates_ the strings. It sticks them together end to end, like this:

```python
school_name = "Kibo"
print("I love " + school_name) # "I love Kibo"
```

They are called _strings_ because they are a series (a ‘string’) of characters. The string `"Kibo"` is made of the characters `'K'`, `'i'`, `'b'`, `'o'`.

### Integers

**Integers** are for representing positive and negative whole numbers.

They look like numbers: `10`, `9019`, or `-5`

Python works like a calculator. It can do math with `+`, `-`, `*`, `/` and more.

```python
10 + 5 # 15

value = 100
value + 10 # 110
value - 10 # 90
value * 10 # 1000
value / 10 # 10
```

### Floats

**Floats** are for representing fractional numbers

They look like numbers with a decimal point: `10.5`, `90.19`, or `-0.781`

Python stores them differently from integers, so they show something different when you call `type` on them

### TypeErrors

**TypeError** is a common error you get when the types don’t match, like if you tried to add a string and a number.

```python
"Hello" + "5" # "Hello5"
"Hello" + 5 # TypeError
```

There are lots more Python types that we didn’t cover. You can look them up by using Google to find the Python documentation.

> **Question:** What do you happens when you add a float and an integer?
> Try to guess the answer first, then try it out in the Python interpreter.
