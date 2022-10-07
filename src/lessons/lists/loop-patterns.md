# Loop patterns

_Estimated Time: 40 minutes_

---

You’ve learned and practiced some of the core actions of working with lists. You can create a list, add and remove items, and perform actions for all of the items. Now it’s time to learn to write code that uses lists and loops to solve problems.

Using lists and loops together, you can answer questions about data.

- _What’s the smallest (or largest) item in this list?_
- _What’s the sum of all the items in the list? What’s the average?_
- _What are the items in the list that fit this condition?_

When solving more complicated problems with lists, it’s also helpful to have more powerful debugging techniques. In this lesson, you’ll learn problem solving with loops, including common patterns and strategies for figuring things out.

## Video: Lists and Loops

<aside>

Watch this video to learn about lists and loops.

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/f1a3374792a54c378b710954bf5a2a0d" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## Looping through a list with `for`

When you first saw the `for` loop, you learned that it could loop through a list, or through a `range`. You’ve been using this the whole time, but as a quick refresher, here’s a loop that will print the numbers from 5 down to 1:

```python
for number in [5,4,3,2,1]:
	print(number)
```

And here’s another version, using `range`:

```python
for number in range(5,0,-1): # start at 5, go down to (but not including) 0, by -1 each time
	print(number)
```

We’ll be using `for` loops for almost all of the loop and list problems here. A `while` loop can work in some circumstances, but it’s usually a little more work.

### Sum of numbers in a list

Here’s a python program to add up all the numbers between 1 and 10:

```python
total = 0
for number in [1,2,3,4,5,6,7,8,9,10]:
	total += number

print(total) # 55
```

Here’s what this program does:

- **Step 1:** Creates a variable called `total`, which starts at `0`
- **Step 2:** Loop through the numbers 1 through 10. Increase `total` by the `number` each time.
- **Step 3:** After the loop, print out the total

<aside>

⚠️ **Common Mistake:** If you create a variable inside the loop, it will get re-created from scratch each time the loop body executes.

To make sure you are updating the variable every iteration, you have to **create the variable before the loop.**

Here is the wrong version. `total` is created inside the loop, so it doesn’t work. **Don’t do this!**

```python
for number in range(1,11):
     total = 0          # total gets re-assigned 0 every time the loop body runs
     total += number

print(total) # 10   <- WRONG!
```

</aside>

## Solving problems using loops

Many loop problems can be solved using the pattern in this example: **update the variable every time you go through the loop.** In this lesson, you’ll see lots of different problems you can solve with this pattern.

🔑 **Common pattern**

**Step 1:** Create a variable before the loop starts and set the initial value.

**Step 2:** Perform some computation on each item in the loop body, which may change the value of the variable.

**Step 3:** Use the value of the variable when the loop completes.

Let’s try it out.

## Practice

<aside>

🔢 Find the sum of the **even** numbers from 10 to 100 (including 10 and 100).

_Remember, you can use the third argument to_ `range` _to control the step size._

</aside>

<iframe src="https://trinket.io/embed/python/4203943828" width="100%" height="300" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

<details>
<summary>Solution (try for 10-20 minutes before peeking)</summary>

```python
total = 0
# We want to include 100, so we stop at 101
# We want even numbers, so step by 2
for i in range(10,101,2):
  total+=i
print(total)
```

Note: there's a built-in Python function called `sum` that can do this for us.
But, that's not a great way to practice using loops!

</details>
