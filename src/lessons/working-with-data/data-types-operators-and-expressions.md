# Data types operators and expressions

_Estimated Time: 20 minutes_

---

## What you need to know about data types

- Python can store different **types** of data
- The basic types of data you’ll learn about first are Strings, Integers, Floats, and Boolean values
- Python knows how to do different operations based the type of value, like `+` to add numbers together

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

These are called _primitive types_. Python can represent more complicated data using _compound types_ like List and Dictionary, \*\*which are made out of the primitive types. We’ll learn about some of those in later lessons.

Python figures out the type automatically based on some rules:

- numbers without a decimal point are treated as **ints** (like `10`)
- numbers with a decimal point are treated as **floats** (like `1.0`)
- text between quote marks is treated as **strings** (like `"Hello"` or `'100.5'`)

There are more rules for other types, but we're skipping them for now.

## Video: Data Types

<aside>

<img src="../instruction.png" alt="../instruction.png" width="40px" /> Watch this video to learn about data types.

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.youtube.com/embed/xvmPtqoEBn8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## Video Notes

- Every value in Python has a type, for example, **string**, **float**, and **integer**. You can find out what type a value is by using the `type()` function.
- **Strings** are for representing text.
  - They look like this: `"Kibo School"`, starting and ending with `"`, the _double quote_.
  - When you add them together with `+`, Python _concatenates_ the strings. It sticks them together end to end, like this:
    ```python
    school_name = "Kibo"
    print("I love " + school_name) # "I love Kibo"
    ```
  - They are called _strings_ because they are a series (a ‘string’) of characters. The string `"Kibo"` is made of the characters `'K'`, `'i'`, `'b'`, `'o'`.
- **Integers** are for representing positive and negative whole numbers.

  - They look like numbers: `10`, `9019`, or `-5`
  - Python works like a calculator. It can do math with `+`, `-`, `*`, `/` and more.

    ```python
    10 + 5 # 15

    value = 100
    value + 10 # 110
    value - 10 # 90
    value * 10 # 1000
    value / 10 # 10
    ```

- **Floats** are for representing fractional numbers
  - They look like numbers with a decimal point: `10.5`, `90.19`, or `-0.781`
  - Python stores them differently from integers, so they show something different when you call `type` on them
- **TypeError** is a common error you get when the types don’t match, like if you tried to add a string and a number.
  ```python
  "Hello" + "5" # "Hello5"
  "Hello" + 5 # TypeError
  ```
- There are lots more Python types that we didn’t cover. You can look them up by using Google to find the Python documentation.

## Operators

- **Operators** are symbols that represent computations like addition and multiplication.
  - **+** performs **addition**
  - **-** performs **subtraction**
  - **\*** performs **multiplication**
  - **/** performs **division**
  - **\*\*** performs **exponentiation**
  - **%** performs **remainder (or modulus) operation**

## Expressions

An expression is a sequence of operands and operators, like 15+5, that gets evaluated to a certain result.

Python doesn’t do everything all at once. It runs a program line by line, in order. Within a line, Python has an evaluation order that decides what comes first.

In the below code, the _right hand side_ is evaluated before _assignment_.

```python
age = 15 + 5
print(age) # 20
```

The `15 + 5` part of the line is called an “expression”. It’s a part of a line in Python.

Expressions get evaluated before assignment. So in the above code, `15 + 5` is evaluated to `20`, and then the value `20` is assigned to the variable `age`.

Expressions also get evaluated before they get printed out in `print()`:

```python
print(10 / 2) # 5
```

Python does the `10 / 2` first, then the `print()`

### Math operators and evaluation order

Python uses the same order of operations that arithmetic traditionally uses.

```python
5 + 4 * 3 # 17 (not 27)
6 * 2 ** 2 # 24 (not 144)
```

This is the order for the math operators:

- **Parenthesis**
- **Exponentiation** (raising to the power)
- **Multiplication**/**division**/**remainder**
- **Addition**/**subtraction**
- **Left to right** to break any ties

You can use parentheses for grouping. They can change the order, or make it more obvious:

```python
5 + (4 * 3) # 17
(5 + 4) * 3 # 27
6 * (2 ** 2) # 24
(6 * 2) ** 2 # 144
```

Parentheses are also used for calling functions like `str()` or `print()`, but it’s usually not that confusing to tell which is which.

Every opening paren needs a closing paren. You can’t do just `(5 + 7`, it needs to be `(5 + 7)`.

## Practice: Working with operators

<aside>

👩🏿‍💻 Practice working with operators. Modify the code below by following instructions in the comments.

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/kibo-fpwp6/W12-Practice-Operators" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

<aside>

</aside>

<details><summary>Solution Code (try for 5 minutes before peeking)</summary>

```python
a = 15
b = 7

# Print the sum (+) of a and b (this one is done for you)
print(a + b)

# Print the difference (-) of a and b
print(a - b)
# Print the product (*) of a and b
print(a * b)
# Print the quotient (/) of a and b
print(a / b)
# Print the remainder (%) of a and b
print(a % b)
```

</details>

## TypeError and Type Conversion

If you try to add a number to a string, Python will raise a `TypeError`. It doesn’t know what you want to do. Do you want to concatenate the two, as if they are both strings? Or, add them together mathematically, as if they are numbers? **Python refuses to guess.**

```python
age = "15" # a string
age + 5 # TypeError, tried to add a string and an int
```

To solve this error, you can convert between data types.

- Turn a string into an **int** with the function `int()`.
- Turn an integer into a **str** with the function `str()`

```python
age = "15" # a string
int(age) + 5 # 15
age + str(5) # "155"
```

<aside>

Next up: [Input and Output](/future-proof-with-python/working-with-data/input-and-output.md)

</aside>
