# Simple decisions

_Estimated Time: 1 hour_

---

Life is full of decisions.

- Do I stay at the party, or is it too awkward?
- Is the price too high?
- Should I study more for the exam?

Programs also need to make decisions. Depending on the circumstances, programs should behave differently.

In this lesson, you’ll learn how to write programs that can make simple decisions using `if` statements. `if` (and related keywords `else` and `elif`) will let you write code that can handle different situations appropriately.

![2%201%20Simple%20decisions%20efbfa340f5df47bd9059c5d369f5793d/Screen_Shot_2021-07-27_at_3.10.10_PM.png](/future-proof-with-python/conditionals/simple-decisions/screen-shot-2021-07-27-at-3.10.10-pm.png)

In the example above, you are going to stay at the party if you do not feel awkward. You can write that decision in a general `if` statement:

```
**if** I don't feel awkward:
  stay at the party
```

This example isn’t _quite_ something Python could execute, but it’s surprisingly close!

### If statement

The `if` statement is the simplest tool for controlling the flow of the program in Python.

```python
if x > 0 :
    print('x is positive')
```

Up until now, Python has run every line of code in our programs, in order. With the `if` statement, that’s no longer the case. The `print` here only runs if `x` really is more than `0`. Otherwise, the `print` will never run at all.

A one-branch `if` statement is the simplest **conditional statement**. Below is a flow control diagram for the code snippet.

![2%201%20Simple%20decisions%20efbfa340f5df47bd9059c5d369f5793d/Untitled.png](/future-proof-with-python/learning-with-kibo/lesson-topics-and-navigation/untitled.png)

The **boolean expression** after `if`, in this case `x > 0`, is called the **condition**. If it is true, then the indented statement gets executed. **If not, nothing happens.**

In the rest of this lesson, you’ll learn more about:

- **boolean values** and **boolean expressions**
- **conditional statements**
- `if`, `elif`, and `else` keywords

### Boolean Values

Boolean is another Python data type. The only two Boolean possible values are `True` and `False`. These values are useful for writing code that makes decisions, like deciding whether or not to stay at the party.

### Boolean Expressions

<aside>

📗 A boolean expression is an expression that evaluates to either `True` or `False`.

</aside>

### Comparisons

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

### Conditional statements

A conditional statement runs code based on a specific condition.

In Python, the syntax uses the keyword `if`, a **condition** followed by a colon `:`, and then an **indented block of code** to run.

```python
if response == "yes":
	print("Proceeding...") # only runs if the value of the variable response is equal to "yes"
```

In this example, the **condition** is `response == "yes"` and the code block is `print("Proceeding...")`.

The code block **ends when you stop indenting**.

In the following example, `"Goodbye"` is _always_ printed, no matter what the response is. It’s outside of the code block, because it’s no longer indented.

```python
response = input("Type 'yes' to proceed")
if response == "yes":
	print("Proceeding...") # only runs if response is equal to "yes"

print("Goodbye")         # runs no matter what
```

## Practice

<aside>

👩🏿‍💻 Write a program that asks the user if the party that they are attending is awkward. If they answer `"yes"`, print `"Leave!"`

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/kibo-fpwp5/If-Awkward" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## If-Else

Sometimes we want to do one thing if a boolean expression is true, and something else if it is false. In those cases, we can write an `if-else` statement.

<aside>

↔️ The `else` keyword executes a block of code if the `if` statement condition is **not** true.

</aside>

Take a look at the example below. It prints a different message based on whether `x` is even or odd.

```python
if x % 2 == 0:
    print('x is even')
else:
    print('x is odd')
```

We want to check if a given number x is even or odd. The `%` operator is called ‘modulo’ and it returns the remainder after division. If the remainder is `0` when `x` is divided by `2`, then `x` is even. The flow control diagram looks like this:

![2%201%20Simple%20decisions%20efbfa340f5df47bd9059c5d369f5793d/Untitled%201.png](/future-proof-with-python/conditionals/simple-decisions/untitled-1.png)

The boolean expression `x % 2 == 0` checks to see if the remainder of x divided by 2 is equal to 0. If this is true, then the first indented statement (called a branch) gets executed and the program prints "x is even". If the boolean expression is false, then the branch after the`else` gets executed instead and the program prints "x is odd".

When writing conditional statements, **you must pay attention to indentation**. You must indent after an `if` statement, maintain the indent as long as you want to be in the `if` block, then reduce the indent when done with the `if` block. Also, **don't forget to add the `:`** after the condition, and another **`:`** after the `else` if you have one.

## Practice

<aside>

👩🏿‍💻 Modify the code below to match the flow chart using an `else` block.
If the user does not answer "yes" to the first question, encourage them to stay.

</aside>

![2%201%20Simple%20decisions%20efbfa340f5df47bd9059c5d369f5793d/Screen_Shot_2021-07-27_at_5.46.48_PM.png](/future-proof-with-python/conditionals/simple-decisions/screen-shot-2021-07-27-at-5.46.48-pm.png)

A sample run of the code should look like this:

![2%201%20Simple%20decisions%20efbfa340f5df47bd9059c5d369f5793d/Untitled%202.png](/future-proof-with-python/conditionals/simple-decisions/untitled-2.png)

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/kibo-fpwp5/Stay-and-Par-tay" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

<aside>

<img src="../Lesson%200%20Learning%20With%20Kibo%2032002756da8b4ed2a610df0347af2a08/man-in-hike.png" alt="../Lesson%200%20Learning%20With%20Kibo%2032002756da8b4ed2a610df0347af2a08/man-in-hike.png" width="40px" /> Next up: [Multi-way decisions](/future-proof-with-python/conditionals/multi-way-decisions.md)

</aside>
