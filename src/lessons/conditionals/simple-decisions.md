# Simple decisions

Life is full of decisions.

- Do I stay at the party, or is it too awkward?
- Is the price too high?
- Should I study more for the exam?

Programs also need to make decisions. Depending on the circumstances, programs should behave differently.

In this lesson, you’ll learn how to write programs that can make simple decisions using `if` statements. `if` (and related keywords `else` and `elif`) will let you write code that can handle different situations appropriately.

![flowchart illustrating decision about whether to stay at a party](/lessons/conditionals/simple-decisions/screen-shot-2021-07-27-at-3.10.10-pm.png)

In the example above, you are going to stay at the party if you do not feel awkward. You can write that decision in a general `if` statement:

```
if I don't feel awkward:
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

<div style="text-align:center">

![onebranchif](/lessons/conditionals/simple-decisions/one-branch-if.png)

</div>

The **boolean expression** after `if`, in this case `x > 0`, is called the **condition**. If it is true, then the indented statement gets executed. **If not, nothing happens.**

In the rest of this lesson, you’ll learn more about:

- **boolean values** and **boolean expressions**
- **conditional statements**
- `if`, `elif`, and `else` keywords

![snakes standing awkwardly at a birthday party](/images/snake_party.png)
