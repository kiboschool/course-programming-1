# Using Dictionaries

When would you use a Dictionary instead of a List?

In this lesson, you'll see two cases where a dictionary is a better data
structure to use. There are lots more cases, some of which you'll explore in
the weekly Practice.

## Representing data: Modeling a Restaurant

Lists are great for storing lots of pieces of identical types of data, like
names. But when data has more structure, Lists start to get awkward!

In this example we want to model a Restaurant, to print some information about
it.

In our model, a restaurant has a name, a cuisine, a number of dollar signs
indicating how expensive it is, and an average rating.

We could keep the information in a list, like this:

```python
restaurant = ["Chicken Republic", "Fast food", "$", 3.7]
```

When we want to use that information, we have to remember the index for each of
the different types of values.

```python
def display_restaurant(rst):
  print("Name: ", rst[0])
  print("Cuisine: ", rst[1])
  print("Expense: ", rst[2])
  print("Rating: ", rst[3])
```

If we want to add or remove information, we'd have to change our code.

Instead, we can use a Dictionary to represent the structure of our data. Instead
of remembering the indexes, we can use the appropriate keys:

```python
restaurant = {
  "name": "Chicken Republic",
  "cuisine": "Fast food",
  "expense": "$",
  "rating": 3.7,
}
```

Then our function wouldn't have to know about the indexes of the data:

```python
def display_restaurant(rst):
  print("Name: ", rst["name"])
  print("Cuisine: ", rst["cuisine"])
  print("Expense: ", rst["expense"])
  print("Rating: ", rst["rating"])
```

### Try It: Structuring Data

> Give structure to this List of information. Rewrite it as a Dictionary with
> meaningful keys.
>
> ```python
> device = ["Galaxy Note 9", "Samsung", "Cloud Silver", "201g", "161.9 x 76.4 x 8.8 mm", "1440 x 2960 pixels"]
> ```

## Counting Items: The `histogram` function

Another use for dictionaries is when you want to compute a result for lots of
different values, and associate the results with the values.

Suppose you are given some text, and you want to count how many times each
letter appears. This is called a `histogram` - a statistical term for a
collection of frequencies.

There are several ways you could do it:

- You could create 26 variables, one for each letter of the alphabet. Then, as
  you traverse the string, for each character, increment the corresponding counter.
- You could create a list with 26 elements. Then you could convert assign each
  character to a number, and use the number as an index into the list to
  increment the appropriate counter.

Both of these options perform the same computation, but they implement
the computation in different ways.

Some implementations are better than others. Using 26 variables will be quite
tedious. Using a List might be less typing, but it could be quite confusing to
debug.

Both solutions are _fragile_. They would need to be changed if you wanted to
count numbers, symbols, or emoji in the text.

Here's a solution using a Dictionary:

- Create a dictionary with characters as keys and counters as values.
  The first time you see a character, add an item to the dictionary.
  After that, increment the value of an existing item if you see that character.

An advantage of the dictionary implementation is that we don’t have to know
ahead of time which letters appear in the text. We only have to make room for
the letters as they show up.

Here an example implementation using a Dictionary:

```python
def histogram(text):
    counts = {}
    for char in text:
        if char not in counts:
            counts[char] = 1
        else:
            counts[char] += 1
    return counts
```

The first line of the function creates an empty dictionary. The `for` loop
traverses each character of the string. Each time through the loop, if the
character is not in the dictionary, we add a new item for the character, with
initial value 1, since we have seen this letter once. If the character is
already in the dictionary, we increment `counts[char]` by 1.

Here’s the result:

```python
>>> histogram('brontosaurus')
{'a': 1, 'b': 1, 'o': 2, 'n': 1, 's': 2, 'r': 2, 'u': 2, 't': 1}
```

The histogram indicates that the letters 'a' and 'b' appear once; 'o' appears
twice, and so on.

If we wanted to count the characters in text with numbers, symbols, and emoji,
the function still works!

```python
>>> histogram("123123 hiii! 🚀🚀🚀!!")
{'1': 2, '2': 2, '3': 2, ' ': 2, 'h': 1, 'i': 3, '!': 3, '🚀': 3}
```

Using a Dictionary makes this solution easier and more robust. It's a clear
winner of a data structure for this problem!

## Try it: `get`

Dictionaries have a method called `get` that takes a key and a default value.
If the key appears in the dictionary, `get` returns the corresponding value.
Otherwise, it returns the default value.

For example:

```python
>>> h = histogram('brontosaurus')
>>> h
{'a': 1, 'b': 1, 'o': 2, 'n': 1, 's': 2, 'r': 2, 'u': 2, 't': 1}
>>> h.get('a', 0)
1
>>> h.get('c', 0)
0
```

> Use the `get` method to rewrite the `histogram` function more concisely.
> You should be able to write it without the `if` statement!

<div style="position: relative; padding-bottom: 56.25%; height: 0;">
<iframe src="https://www.youtube.com/embed/09Y-UX7xgZI" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

## Think about it: Which data structure to use?

> You've seen two examples (structuring information and counting) where
> dictionaries are a good choice of data structure to use. For each of the
> following scenarios, think about what data structure you would use.
>
> - The names of all the Pokemon
> - The attributes for the Pokemon Pikachu
> - A blog post
> - The attributes for all of the Pokemon

<details><summary>Explanation</summary>

- The names of all the Pokemon

A List makes sense for this one. It's a list of ordered names.

- The attributes for the Pokemon Pikachu

A Dictionary would make it easy to structure this information.
`pikachu['health']` would be way easier than remembering the index for
`pikachu[3]` or something!

- The attributes for all of the Pokemon

This one is tricky! Since it's a lot of Pokemon, it should be a List. But, to
structure the information, it should be a dictionary.

One way to model this would be a List of Dictionaries. Each item in the List
would be a Dictionary representing the attributes for one pokemon, like this:

```python
pokemon = [
  {
    "name": "Pikachu",
    "health": 50,
    "attack": 27,
    ...
  },
  {
    "name": "Charizard",
    "health": 181,
    "attack": 92,
    ...
  }
  ...
]
```

- A blog post

There are different options for this, but a String might make the most sense.
If you also wanted to include structured information like the date and author,
then a Dictionary could also make sense.

</details>

## Lookup Time

One key factor when choosing data structures is program speed. We haven't
covered much about how to consider the speed of different programs, but the
basic idea isn't that complicated: the more operations a program has to do, the
slower it is.

One of the key properties of Dictionaries is that the _lookup time_ for a key is
fast, similar in speed to accessing a list item with a given index.

```python
# These are roughly similar in speed
some_list[6]
some_dictionary["key"]
```

When designing a system that has to find information quickly, it's often better
to use a dictionary, if there is a key that you can use for lookups. That way,
you don't have to loop through the whole list to find the item you need.

Here's the (fake) code comparing List and Dictionary versions of the lookup
function.

```python
# lookup in a List
def lookup_person(people_list, name):
  for person in people_list:
    if person["name"] == name:
      return person

# lookup in a dictionary
def lookup_person(people_dict, name):
  return people_dict[name]
```

For the dictionary, there is just one operation. For the List, there is one
operation _per item in the list_. If there were thousands of people in the list,
you'd have to check thousands of names!

## Think it through: Event Attendees

Imagine that you are asked to organise an event with lots of attendees. Each
attendee has a name, badge number, the name of the organization they are part of,
and whether or not they've paid.

> What would you use to store attendee information, a list or a dict? Why?

<details><summary>Show Discussion</summary>

There's no one right answer. The right decision depends on how the data will be
accessed.

## Design 1: List of Dictionaries

One design might be to use a list to store all attendees, with each item in the list being a dictionary. That way, you could loop through the list to print out all of the badges.

```python
attendees = [
  {
    "name": "John Doe",
    "badge_number": 123,
    "organization": "ACME",
    "paid": True,
  },
  {
    "name": "Jane Doe",
    "badge_number": 456,
    "organization": "ACME",
    "paid": False,
  },
  ...
]
```

This design would make it easy to print out all of the badges. And if the list of attendees is quite small, searching through the list to find a particular attendee wouldn't be too slow.

## Design 2: Dictionary of Dictionaries

A different design might be to use a dictionary, with the badge number as the key.

```python
attendees = {
  123: {
    "name": "John Doe",
    "organization": "ACME",
    "paid": True,
  },
  456: {
    "name": "Jane Doe",
    "organization": "ACME",
    "paid": False,
  },
  ...
}
```

This design would make it easy to look up the information for a particular badge. You can also use the name as the key, if you want to look up the information by name. But, in this case, you have to be careful to make sure that the name is unique!

There's also other ways to structure data that we haven't explored yet. It might
make sense to use another data structure or a database, depending on the
situation.

</details>
