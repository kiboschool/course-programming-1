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

<iframe src="https://trinket.io/embed/python/3acf190b0d" width="100%" height="300" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

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

![flow chart illustrating even or odd paths](/lessons/conditionals/simple-decisions/even-odd-flowchart.png)

The boolean expression `x % 2 == 0` checks to see if the remainder of x divided by 2 is equal to 0. If this is true, then the first indented statement (called a branch) gets executed and the program prints "x is even". If the boolean expression is false, then the branch after the`else` gets executed instead and the program prints "x is odd".

When writing conditional statements, **you must pay attention to indentation**. You must indent after an `if` statement, maintain the indent as long as you want to be in the `if` block, then reduce the indent when done with the `if` block. Also, **don't forget to add the `:`** after the condition, and another **`:`** after the `else` if you have one.

## Practice

<aside>

👩🏿‍💻 Modify the code to match the flow chart using an `else` block.
If the user does not answer "yes" to the first question, encourage them to stay.

</aside>

<img alt="awkward party decision making flowchart" src="/lessons/conditionals/simple-decisions/do-you-feel-awkward-flowchart.png" height="350"/>

<iframe src="https://trinket.io/embed/python/861143ef37" width="100%" height="300" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

A sample run of the code should look like this:

```
Hello! What's your name? Opeyemi
Hello Opeyemi! Let's see if it's time to leave this party.
Is it awkward? I'm not sure
Stay and par-tay!
```
