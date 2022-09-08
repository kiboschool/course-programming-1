# If/Else

_Estimated Time: 30 minutes_

---

## Conditional statements

A conditional statement runs code based on a specific condition.

In Python, the syntax uses the keyword `if`, a **condition** followed by a colon `:`, and then an **indented block of code** to run.

```python
if response == "yes":
	print("Proceeding...") 
```

The `print` only runs if the value of the variable response is equal to "yes"

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

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/kibo-fpwp6/W21-If-Awkward" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

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

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/kibo-fpwp6/W22-Stay-and-Par-tay" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
