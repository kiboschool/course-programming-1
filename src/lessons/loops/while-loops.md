# While loops

Often, we want code to keep going. For example, a password prompt might ask a user for their password until they enter a valid value. The program doesn’t know ahead of time how many tries the user will need. Instead, it knows when to stop asking — when the user enters a valid password. This type of situation is perfect for a `while` loop.

In this section, we'll learn about `while` loops. `while` loops repeat a block of code until a condition is met.

### `while` loops

<aside>

📗 A `while` loop is a way to repeat code while a certain condition is true.

</aside>

The syntax looks like this:

```python
while condition:
	block of code to execute
```

It’s a lot like an `if` statement. It checks the condition, then runs the block of code if the condition is `True`.

Unlike an `if` statement, however, after executing the block, a `while` loop checks the condition again and again. It only stops when the condition becomes `False`.

Here’s a flow chart depicting a `while` loop:

![While loops flowchart](/lessons/loops/while-loops/while-loops-flowchart.png)

The flow of a `while` statement is:

1. Evaluate the condition, the result will be **True** or **False**.

2. If the condition is **False**, exit the `while` statement and continue execution at the next statement (after the while loop block).

3. If the condition is **True**, execute the body of the while statement and **go back to Step 1**

## Examples

Here's an example asking the user for password:

```python
# Set up the password
password = "super secret"
user_entry = ""

# While loop
while user_entry != password:
	user_entry = input("What's the password?")
```

In the example above, the program will keep prompting the user for a password _while_ the user's input is not the expected value.

![Password prompt interactive](/lessons/loops/while-loops/password-interactive.gif)

Below is another example:

```python
n = 5
while n > 0:
    print(n)
    n = n - 1
print('Blastoff!')
```

You can read the code in English as:

- The initial value of `n` is 5
- While `n` is greater than 0, display the value of `n`, and then reduce the value of `n` by 1
- When `n` is no longer greater than 0, display the string Blastoff!

The code will output:

```
5
4
3
2
1
Blastoff!
```

The condition we are checking before every loop is: **"Is `n` greater than zero?"** This is a boolean expression that will yield either `True` for 5, 4, 3, 2, and 1, or `False` when the value of `n` is 0.

## What does a loop look like?

```python
a = 1
while a < 10:
	print(a)
	a += 2
```

Let’s visualize how this code runs:

![While loop visualization](/lessons/loops/while-loops/while-loop-visualization.gif)

In the animation, you can see the variable `a` change over time, and the loop condition checked before each execution of the loop body.

<aside>

👉🏿 Step through this code interactively on [pythontutor.com](https://pythontutor.com/visualize.html#code=a%20%3D%201%0Awhile%20a%20%3C%2010%3A%0A%20%20%20%20print%28a%29%0A%20%20%20%20a%20%2B%3D%202&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false)

</aside>

## Loop Vocabulary

A `while` loop has a **condition** and a **body.** The condition is what gets checked each time. The body is the code that runs again and again. Just like an `if` statement, the body code has to be indented.

Every execution of the body of a `while` loop is called an **iteration**. In the blastoff example, the body of the loop was executed five times, so the loop has five iterations.

Whether or not the loop body will be executed depends on whether or not the condition evaluates to `True` or `False`.

In the ‘blastoff’ example above, the loop is controlled by an **iteration variable** `n` which tells the loop whether or not to proceed. The body of the loop changes the value of `n` each time the loop runs, so that the loop eventually finishes running.

If `n` did not change, the loop would repeat forever, creating an **infinite loop**.

### Infinite loop

An infinite loop is a loop that runs forever. For example:

```python
x = 4
while x > 0:
	print("Run on!")
print ("Done!")
```

4 is always greater than 0, and `x` never changes, so the loop runs forever.

If you accidentally write an infinite loop, you will have to figure out how to stop it. Sometimes you’ll need to force-close the program. If you accidentally run an infinite loop in a repl or terminal, you can press Control + C in the console to end the program.

### Infinite Loop Demo

♾️ Try running this demo of an infinite loop.

> Press the Stop button to end the program. Otherwise, it will run on forever! Or, at least until you leave the page.

<iframe src="https://trinket.io/embed/python/7098abab1d" width="100%" height="300" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


## Practice: Loop Prediction

🤔 Look at the following code snippet. **What will the output be? Why?**

Think about it, write down what you think the result will be, then expand the solution.

```python
i = 10
while i > 13:
  print ('This is a while loop')
  i = i + 1
```

<details>
<summary>Unfold to see the solution</summary>

The body of the loop will never get executed!
The condition `i > 13` will be `False` because 10 is not greater than 13. So, the body of the while loop will be skipped.

</details>

## Practice

<aside>

👩🏿‍💻 Write a `while` loop that displays the integers 1 through 10. Follow the code comments in the below Replit exercise.

</aside>

<iframe src="https://trinket.io/embed/python/b94b6e570b" width="100%" height="300" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
