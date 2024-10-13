# List basics

# What is a list?

In your life, you’ve come across all kinds of lists - grocery lists, to-do lists, the attendance roll at school, the roster of your football team. Lists in Python are a way to represent many pieces of data, like you do on those lists. Instead of just one number, string, or boolean, a list can hold many pieces of data at once.

When working with lists in your life, there are a few core actions you perform:

- Create a list
- Add something to the list
- Remove something from the list
- Change an item on the list
- Take some action for all of the items on the list

In this lesson, we’ll cover the syntax for creating lists and updating lists, and performing these core actions.

Watch this video for an overview of lists in Python:

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.youtube.com/embed/zEyEC34MY1A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## List Syntax

A list is a sequence of values. It’s written like this:

```python
[1,2,3]
```

The list is surrounded by square brackets, with **elements** separated by commas. The values inside a list are called ‘elements’ or ‘items’. You can assign lists to variables, just like you can with numbers and strings:

```python
my_list = [1,2,3]
```

Lists can be empty. An empty list looks like this:

```python
empty_list = []
```

Lists can contain any type of element, even other lists.

Below are some examples of valid lists:

```python
countries = ["Kenya", "Ghana", "Ethiopia", "Zimbabwe"]
primes = [2, 3, 5, 7, 11]
empty_list = []
foods = [["apples", "kiwis", "bananas"], ["chorizo", "steak", "chicken nuggets"], ["ice cream", "popcorn", "chocolate bars"]]
different_types = [False, 1, "string", []]
```

## The `list` data type

Earlier, you learned the basic Python data types: String, Int, Float, Boolean. A List is another core data type in Python, but it’s different from the others you’ve learned so far.

```python
my_list = [1,2,3]
type(my_list) # <class 'list'>
```

A list is a type of **data structure**.

<aside>

📗 A **data structure** is a way of storing and organizing data. Data structures are used in programming to organize and store data such that computers can efficiently perform operations on that data.

</aside>

Different data structures are useful for solving different kinds of problems in Python. The other most common built-in Python data structures are dictionaries, sets, and tuples. We’re going to focus on Lists, but as you grow in your Python skills, you’ll learn the uses of these other types.

### List indices

Each element of the list has a position, called an **index**. We can get an element from a list using the name of the list and its index in brackets. For example, given the list below:

```python
countries = ['Kenya', 'Ghana', 'Ethiopia', 'Zimbabwe']
```

We can access the first list item using `countries[0]`, the second list item using `countries[1]`, and so on.

```python
countries[0] # "Kenya"
countries[1] # "Ghana"
```

Remember that lists are **indexed starting at 0**. So the first item has position 0, the second item has position 1, and so on. This start-from-zero numbering is common to almost all programming languages.

<details>
<summary><strong>Why do list indices start at 0?</strong></summary>

You can think of a list index as an **offset.** Indexes answer the question: _"How many spaces from the start do I go to find the item?"_

![array_indices_explanation.png](/lessons/lists/list-basics/array-indices-explanation.png)

In this list, you have to move 0 spaces to get to `"Kenya"`, so it is at index `0`. You have to move 2 spaces to get to Ethiopia, so it is at index `2`.

```python
countries[0] # "Kenya"
countries[2] # "Ethiopia"
```

</details>

After you access an element from a list, you can use it anywhere you’d use another value or variable.

```python
print(countries[0]) # Kenya
print(countries[1] + " is a nice place to visit") # Ghana is a nice place to visit
```

## Practice: Access List Items

<aside>

👩🏿‍💻 Practice accessing items in a list. Modify the code below by following instructions in the comments.

</aside>

<iframe src="https://trinket.io/embed/python/7a8f4f2dbb" width="100%" height="400" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

<details>
<summary>Solution Code (try for 5 minutes before peeking)</summary>

```python
tallest_buildings = ["Burj Khalifa", "Merdeka 118", "Shanghai Tower", "Abraj Al-Bait Clock Tower", "Ping An International Finance Centre", "Lotte World Tower"]

print(tallest_buildings[0])
print(tallest_buildings[2])
print(tallest_buildings[1], "is taller than", tallest_buildings[5])
```

</details>

## More about lists

### `IndexError`

If you try to access a value past the end of the list, Python will raise an error:

```python
print(countries) # ['Kenya', 'Ghana', 'Ethiopia', 'Zimbabwe']
countries[3] # "Zimbabwe"
countries[4] # IndexError: list index out of range
```

### `len`

To keep from going out of bounds, you can get the length of the list with the function `len`:

```python
len(countries) # 4
```

### Last item

If there are 4 elements, then the last index is `3`.

Since we start counting at `0`, the last element is always at index _one less than the length of the list_.

```python
countries = ['Kenya', 'Ghana', 'Ethiopia', 'Zimbabwe']
last_index = len(countries) - 1 # 3
countries[last_index] # "Zimbabwe"
countries[len(countries) - 1] # "Zimbabwe"
```

### Negative indexes

Python has a shorthand for accessing elements from the end of the list:

```python
countries[-1] # "Zimbabwe"
countries[-2] # "Ethiopia"
```

Negative indices start counting from the end of the list, so `-1` is the last index, and `-2` is the second-to-last, and so on.
