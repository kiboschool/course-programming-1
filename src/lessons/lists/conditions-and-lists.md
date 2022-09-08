# Conditions and Lists

<aside>

Watch this video to learn about lists and loops with conditions.

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/b567c2661782431a86891fcc9337d3d3" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## Check if an item is in the list

Sometimes you want to find out if some item is in the list. You can use the same pattern as before, but with a different change to the variable in the loop body.

Here’s an example:

```python
# Does the list have string "Python" in it?
languages = ["Ruby", "JavaScript", "C", "Rust", "Smalltalk", "Clojure", "Python"]

has_match = False
for language in languages:
	if language == "Python":
		has_match = True

print(has_match)
```

It’s the same pattern as before, but with an `if` statement in Step 2.

- 🔑 **Step 1:** Create a variable called `has_match`, which starts as `False`
- 🔑 **Step 2:** Loop through the strings in the list. If the string matches, set `has_match` to `True`
- 🔑 **Step 3:** Print out the `has_match` variable

<aside>

⚠️ Note: You could use the `in` operator for this problem.

- `in` is easier if we want to check for a specific item.
- Using a loop makes it possible to check more complicated conditions like _“Is there a string in this list longer than 40 characters?”_

</aside>

## Filter a list

Sometimes, you want to find only the values in your list that meet a certain condition.

Again, we can use the three step pattern. The variable we are updating will be a new list, with just the filtered values.

```python
numbers = [62, 60, 53, 53, 33, 3, 25, 61, 36, 1, 69, 55, 56, 39, 32, 76, 20, 62, 47]
# Write a program to find all the even numbers in the list
evens = []
for element in numbers:
  if element % 2 == 0:
		evens.append(element)

print(evens) # [62, 60, 36, 56, 32, 76, 20, 62]
```

We use an `if` statement and the modulo operator to find the even values, and add them to the list.

## Practice: Sum of Odds

<aside>

👩🏿‍💻 Write a loop that finds the total of all the odd numbers in the list.

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/kibo-fpwp6/W45-Sum-of-Odd-Numbers" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

<details>
<summary>Solution (try for at least 10-20 minutes before looking)</summary>

```python
numbers = [62, 60, 53, 53, 33, 3, 25, 61, 36, 1, 69, 55, 56, 39, 32, 76, 20, 62, 47]

total = 0
for n in numbers:
  if n % 2 == 1:
    total += n

print(total)
```

</details>

## Smallest Item

Finding the minimum value in a list uses the same pattern. Step through the elements of the list, and update a variable that is tracking the _current_ minimum value.

Each time through the loop, check if the number is smaller than the current minimum value. If it is, then it’s the new minimum value.

We can use the first value in the list as the initial value of the minimum.

```python
numbers =  [62, 60, -53, 53, 33, -3, 25, 81, 36, 1, 69, 55, 56, 39, -32, -76, 20, 62, 47]
minimum = numbers[0]
for number in numbers:
	if number < minimum:
		minimum = number

print(minimum) # -76
```

With one small change, this same code works to find the largest value instead.

## Practice: Interactive Minimum

<aside>

👩🏿‍💻 Follow the prompts in the comments to write a program to find the smallest number among numbers the user enters.

The program should look like this when it runs:

![enter.png](/future-proof-with-python/lists-and-loops/debugging-loops-and-lists/enter.png)

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/kibo-fpwp6/W46-Interactive-Minimum" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

<details>
<summary>Solution (try for at least 10-20 minutes before looking)</summary>

```python
numbers = int(input("How many numbers will you enter? "))
i = 0
minimum = float('inf')

for i in range(numbers):
  x = int(input("Enter a number: "))
  # check whether x is smaller than minimum, and reassign minimum to it if so
  if x < minimum:
    minimum = x

print("The smallest number is:", minimum)
```

</details>
