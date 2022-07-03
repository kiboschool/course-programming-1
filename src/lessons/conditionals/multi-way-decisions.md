# Multi way decisions

_Estimated Time: 40 minutes_

---

In this section, we will explore writing conditional statements when there are more than two possible outcomes.

### If-elif statements

`if` and `else` let us express conditions with two possible outcomes. But what if there are more than two possibilities we want to express in our program? `elif` stands for "else if". It lets us check more conditions, so we can cover as many conditions as we want.

Below is the flow control diagram for a multi-branch program:

![2%202%20Multi-way%20decisions%205adb8178795a43bf9ff453def27f562e/Untitled.png](/future-proof-with-python/learning-with-kibo/lesson-topics-and-navigation/untitled.png)

Here is the corresponding Python code:

```python
if x < y:
    print('x is less than y')
elif x > y:
    print('x is greater than y')
else:
    print('x and y are equal')
```

The code runs line by line. So, the conditions are checked _in the order the code is written._ The code does not look ahead. So, in the example above, assuming x = 3 and y = 3, the code will do 2 comparisons:

- Check if x is less than y. Since x = 3 and y = 3 this statement is false, and it keeps going
- Check if x is greater than y. Since x = 3 and y = 3, this statement is false
- Execute the else statement and print 'x and y are equal'

But with x = 4 and y = 6, the code will run the first comparison, print `'x is less than y'` and finish. It will never even run the second check!

There is no limit on the number of `elif` statements that can be added, but the code will evaluate them from top to bottom. Having an `else` statement is optional, but if you have one, it has to be at the end.

## Practice

<aside>

👩🏿‍💻 Let's get back to the party. Modify the code to account for whether or not there is free food.

</aside>

![2%202%20Multi-way%20decisions%205adb8178795a43bf9ff453def27f562e/Screen_Shot_2021-07-27_at_3.10.10_PM.png](/future-proof-with-python/conditionals/simple-decisions/screen-shot-2021-07-27-at-3.10.10-pm.png)

Sample runs of the code now look like this:

![2%202%20Multi-way%20decisions%205adb8178795a43bf9ff453def27f562e/Untitled%201.png](/future-proof-with-python/conditionals/simple-decisions/untitled-1.png)

![2%202%20Multi-way%20decisions%205adb8178795a43bf9ff453def27f562e/Untitled%202.png](/future-proof-with-python/conditionals/simple-decisions/untitled-2.png)

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/kibo-fpwp5/W23-Free-Food" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## Combining Conditions with `and` and `or`

To check more than one thing, you can combine conditions with `and` or `or`.

```python
if x > 10 and x < 100:
	print("x is a medium sized number")
elif x < 10 or x > 100:
	print("x is either small or large")
else:
	print("x is exactly 10 or 100")
```

They work basically like they do when you use them in English:

- `and` is `True` if both the left and the right side are true, `False` if either is false
- `or` is `True` if either the left or the right side are true, `False` if both are false

| left side | right side | and   |
| --------- | ---------- | ----- |
| True      | True       | True  |
| True      | False      | False |
| False     | True       | False |
| False     | False      | False |

| left side | right side | or    |
| --------- | ---------- | ----- |
| True      | True       | True  |
| True      | False      | True  |
| False     | True       | True  |
| False     | False      | False |

**Note:** Python’s `or` results in `True` if either **the left, the right, or both** are `True`. This is somewhat different from how we speak. Sometimes in English, “or” means one or the other, but not both. That’s sometimes called the “exclusive or” or ‘xor’, but it doesn’t have a Python keyword.

## Not

Python can turn a boolean into its opposite with `not`.

```python
not True # False
not False # True
not 100 > 10 # False
not 100 < 10 # True

if not response == "It's awkward":
	print("Stay and par-tay!")
```

Sometimes it’s useful to be able to express the opposite of a condition.

```python
response = int(input("Enter a big number: "))
if not response > 100:
	print("That's not a big enough number!")
```

If the input is not greater than 100, it will print output to tell the user that their number isn’t big enough.

<aside>

🤔 How else could you write this snippet?

- Solution
  You could express the same thing with `<=`.
  `response <= 100` is equivalent to `not response > 100`

</aside>

`not` can be combined with other conditions, like `and` and `or`. It’s often useful to group expressions with parentheses when making combinations.

```python
if not (x < 10 or x > 100):
	print("x is a medium sized number")
```

<aside>

<img src="../Lesson%200%20Learning%20With%20Kibo%2032002756da8b4ed2a610df0347af2a08/man-in-hike.png" alt="../Lesson%200%20Learning%20With%20Kibo%2032002756da8b4ed2a610df0347af2a08/man-in-hike.png" width="40px" /> Next up: [Practice Conditionals](/future-proof-with-python/conditionals/practice-conditionals.md)

</aside>
