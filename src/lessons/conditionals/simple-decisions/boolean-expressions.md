# Boolean Expressions

Boolean is another Python data type. The only two Boolean possible values are `True` and `False`. These values are useful for writing code that makes decisions, like deciding whether or not to stay at the party.

## Boolean Expressions

<aside>

📗 A boolean expression is an expression that evaluates to either `True` or `False`.

</aside>

The simplest boolean expressions are the keywords `True` and `False`. Just like
we can do arithmetic with numbers, we can also build more complicated statements
that turn into `True` or `False`.

One kind of operation that results in boolean values is **comparisons**.

## Comparisons

You can compare values in Python using **comparison operators.** These operators produce `True` or `False` based on the values on either side.

```python
# '<' is the 'less than' operator
5 < 10 # True
15 < 10 # False
```

Here are the other comparison operators:

- **==** means **Equal to**
- **<** means **Less than**
- **<=** means **Less than or Equal to**
- **>=** means **Greater than or Equal to**
- **>** means **Greater than**
- **!=** means **Not Equal to**

Here’s some examples:

```python
x = 10  # Set x to 10. Note that the usage of "=" is not a boolean expression.

x == 10 # True (check if x equals 10)
x == 6  # False
x < 8   # False
x > 8   # True
x > 10  # False
x >= 10 # True
x <= 90 # True
```

Comparisons work on strings too:

```python
y = "Hello"    # set y to "Hello"

y == "Goodbye" # False
y == "Hello"   # True
y == "hello"   # False (!!! equality is case-sensitive)
y != "Goodbye" # True
y != "Hello"   # False
y == 5         # False
y > 5          # TypeError
```

<aside>

📌 If you write these lines in `main.py` in Replit and press Run, you won’t see any output. Remember, the output in the Console tab comes from `print`. If you want to see the results in the console, add `print`. For example, write `print(10>7)`

Alternatively, you can enter these examples line-by-line in the Console itself. The Console runs lines of Python, so you can test out small snippets of code like these. Try it out!

</aside>

## Exploring Using the REPL

Check this video on how to use python **REPL** to test boolean expressions and conditions.

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/9dfafa43e05d471e80b7adc52960137e" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

