# And, Or, Not

_Estimated Time: 15 minutes_

---

In Python, you can combine conditions using the _logical operators_ `and`, `or`,
and `not`. They let you express more complex conditions, like "even numbers
greater than 100" or "the password must be between 8 and 26 characters long, and include
a number, a symbol, and a capital and lowercase letter".

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

<details><summary> 🤔 How else could you write this snippet? </summary>

You could express the same thing with `<=`. 

`response <= 100` is equivalent to `not response > 100`

</details>

</aside>

`not` can be combined with other conditions, like `and` and `or`. It’s often useful to group expressions with parentheses when making combinations.

```python
if not (x < 10 or x > 100):
	print("x is a medium sized number")
```

## Practice: Print multiples

In this practice, you will write a program that asks the user for a number then prints a statement based on the number the user enters.

<aside>

[✂️ **Access** and **submit** the practice here](https://replit.com/team/kibo-fpwp6/Print-multiples)

</aside>
