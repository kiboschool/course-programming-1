# List basics

_Estimated Time: 1 hour_

---

# What is a list?

In your life, you’ve come across all kinds of lists - grocery lists, todo lists, the attendance roll at school, the roster of your football team. Lists in Python are a way to represent many pieces of data, like you do on those lists. Instead of just one number, string, or boolean, a list can hold many pieces of data at once.

When working with lists in your life, there are a few core actions you perform:

- Create a list
- Add something to the list
- Remove something from the list
- Change an item on the list
- Take some action for all of the items on the list

In this lesson, we’ll cover the syntax for creating lists and updating lists, and performing these core actions.

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

We can access the first list item using `countries[0]`, the second list item using `countries [1]`, and so on.

```python
countries[0] # "Kenya"
countries[1] # "Ghana"
```

Remember that lists are **indexed starting at 0**. So the first item has position 0, the second item has position 1, and so on. This start-from-zero numbering is common to almost all programming languages.

<aside>

👉🏿 **Why do list indices start at 0?**
You can think of a list index as an **offset.** Indexes answer the question:

> _How many **spaces from the start** do I go to find the item?_

![array_indices_explanation.png](/future-proof-with-python/lists-and-loops/list-basics/array-indices-explanation.png)

In this list, you have to move 0 spaces to get to `"Kenya"`, so it is at index `0`. You have to move 2 spaces to get to Ethiopia, so it is at index `2`.

```python
countries[0] # "Kenya"
countries[2] # "Ethiopia"
```

</aside>

After you access an element from a list, you can use it anywhere you’d use another value or variable.

```python
print(countries[0]) # Kenya
print(countries[1] + " is a nice place to visit") # Ghana is a nice place to visit
```

## Practice

<aside>

👩🏿‍💻 Practice accessing items in a list. Modify the code below by following instructions in the comments.

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/kibo-fpwp5/W41-Accessing-List-Items" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

- Solution Code (try for 5 minutes before peeking)
  ```python
  tallest_buildings = ["Burj Khalifa", "Merdeka 118", "Shanghai Tower", "Abraj Al-Bait Clock Tower", "Ping An International Finance Centre", "Lotte World Tower"]

  print(tallest_buildings[0])
  print(tallest_buildings[2])
  print(tallest_buildings[1], "is taller than", tallest_buildings[5])
  ```

## More about list indices

If you try to access a value past the end of the list, Python will raise an error:

```python
print(countries) # ['Kenya', 'Ghana', 'Ethiopia', 'Zimbabwe']
countries[3] # "Zimbabwe"
countries[4] # IndexError: list index out of range
```

To keep from going out of bounds, you can get the length of the list with the function `len`:

```python
len(countries) # 4
```

If there are 4 elements, then the last index is `3`, since we start counting at `0`. The last element is always at index one less than the length of the list.

```python
countries = ['Kenya', 'Ghana', 'Ethiopia', 'Zimbabwe']
last_index = len(countries) - 1 # 3
countries[last_index] # "Zimbabwe"
countries[len(countries) - 1] # "Zimbabwe"
```

Python has a shorthand for accessing elements from the end of the list:

```python
countries[-1] # "Zimbabwe"
countries[-2] # "Ethiopia"
```

Negative indices start counting from the end of the list, so `-1` is the last index, and `-2` is the second-to-last, and so on.

## Changing Lists

Lists are **mutable.** In programming, that means ‘changeable’. The order of items in a list and the list items themselves **can be changed**. We can add and remove items, swap items in place, and reorder the list.

We can change any element of a list by assigning at an index. For example, to change the second item in the list above to the `"Nigeria"`, we can assign to index `1`, like this:

```python
# The old list
print(countries) # ['Kenya', 'Ghana', 'Ethiopia', 'Zimbabwe']
# Change the second item
countries[1] = 'Nigeria'
# The new list
print(countries) # ['Kenya', 'Nigeria', 'Ethiopia', 'Zimbabwe']
```

To add a new element to the end of the list, you use `.append()`

```python
countries.append("Cameroon")
print(countries) # ['Kenya', 'Nigeria', 'Ethiopia', 'Zimbabwe', 'Cameroon']
```

To remove an item from a list, you use `pop()`. With no arguments, pop removes the last element.

```python
countries = ['Kenya', 'Ghana', 'Ethiopia', 'Zimbabwe']
print(countries) # ['Kenya', 'Nigeria', 'Ethiopia', 'Zimbabwe', 'Cameroon']
countries.pop() # removes the last element, "Cameroon"
print(countries) # ['Kenya','Nigeria', 'Ethiopia', 'Zimbabwe']
```

Or, you can specify an index to remove, and `pop()` will remove the element at that index.

```python
print(countries) # ['Kenya','Nigeria', 'Ethiopia', 'Zimbabwe']
countries.pop(1) # Removes the element at index 1, "Nigeria"
print(countries) # ['Kenya', 'Ethiopia', 'Zimbabwe']
```

## Check your understanding

Try this quiz to check how well you understand what list operations will do.

<div data-tf-widget="zKMVM3FL" data-tf-medium="snippet" style="width:100%;height:400px;"></div><script src="//embed.typeform.com/next/embed.js"></script>

## Practice

<aside>

👩🏿‍💻 Modify the code below to perform operations on a list.

A sample run of your code should look like this:

![967C2CAE-7F32-4C99-A035-74A8D0E206C1-535-0003A68938832020.png](/future-proof-with-python/lists-and-loops/list-basics/c2cae-7f32-4c99-a035-74a8d0e206c1-535-0003a68938832020.png)

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/kibo-fpwp5/W42-Mutating-A-List" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

- Solution Code (try for 5 minutes before peeking)
  ```python
  my_list = [10, 20, 30, 40, 50]
  print(my_list)

  # Assign the first list item the value 5
  my_list[0] = 5
  print(my_list)

  # Assign the last list item the value 'dog'
  my_list[4] = 'dog'
  print(my_list)

  # Remove the second item in the list
  my_list.pop(1)
  print(my_list)

  # Add another item to the end of the list with value False
  my_list.append(False)
  print(my_list)

  print("The number of items in the list is", len(my_list))
  ```

<aside>

<img src="../Lesson%200%20Learning%20With%20Kibo%2032002756da8b4ed2a610df0347af2a08/man-in-hike.png" alt="../Lesson%200%20Learning%20With%20Kibo%2032002756da8b4ed2a610df0347af2a08/man-in-hike.png" width="40px" /> Next up: [Practice: Lists](/future-proof-with-python/lists-and-loops/practice-lists.md)

</aside>
