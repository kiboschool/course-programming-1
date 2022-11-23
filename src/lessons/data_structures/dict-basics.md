# Dictionary Basics

In this section, you will learn a new Python data structure called a Dictionary. 

What is it? Why do we need it? How do you use it?

## What is a Dictionary?

So far, you've used Lists to manage collections of items.

In a list, items are ordered, and you use numeric indices to access them:

```python
countries = ["Kenya", "Ghana", "Ethiopia", "Zimbabwe"]
countries[2] # "Ethiopia"
```

A dictionary, like a list, stores a collection of values. Instead of keeping them
in order and accessing them with indices, a Dictionary has a _key_ for each
value.

```python
capitals = {
  "Kenya": "Nairobi",
  "Ghana": "Accra",
  "Ethiopia": "Addis Ababa",
  "Zimbabwe": "Harare",
}
capitals["Kenya"] # "Nairobi"
```

Each value has a key, and you can access the value using the key.

Each key is associated with a single value. As in Lists, values can have any
type. Keys are often strings, but can have other values too.

The association of a key and a value is called a "key-value pair" or sometimes an "item".

> Mathematically speaking, a dictionary represents a mapping from keys to values. You can also say that each key “maps to” a value.

## Basic Concepts

As an example, we’ll build a dictionary that maps from English to Spanish words, 
so the keys and the values are all strings. I encourage you to open a Python
repl and run each of these commands yourself as you read. You'll learn it better
if you are active, and it gives you a chance to explore.

Let's start with basic commands.

### Creating dictionaries and adding items

```
>>> english_to_spanish = {}
>>> english_to_spanish
{}
```

The squiggly-brackets, `{}`, represent an empty dictionary. 

To add items to the dictionary, you can use square brackets: 

```
>>> english_to_spanish['one'] = 'uno'
```

This adds an item to the dictionary that maps from the key `'one'` to the value 
`'uno'`. If we show the dictionary again, we see the key-value pair, with a colon 
between the key and value:

```
>>> english_to_spanish
{'one': 'uno'}
```

This output format is also a valid syntax for creating a dictionary. Instead of
adding items one by one, we can create a dictionary with three items:

```
>>> english_to_spanish = {'one': 'uno', 'two': 'dos', 'three': 'tres'}
```

### Indexing and Order

If you print `english_to_spanish`, you might be surprised:

```
>>> english_to_spanish
{'one': 'uno', 'three': 'tres', 'two': 'dos'}
```

The order of the key-value pairs might not be the same as you entered!

In general, the order of items in a dictionary is unpredictable.

But, that’s no problem, since elements of a dictionary are not indexed by numbers. 
Instead, you use the keys to look up the corresponding values:

```
>>> english_to_spanish['two']
'dos'
```

The key `'two'` maps to the value `'dos'`. The order of the items doesn’t matter.

### Missing Items

If you try to access a key that isn’t in the dictionary, you get an exception:

```
>>> english_to_spanish['four']
KeyError: 'four'
```

### How many items in a Dictionary

The `len` function returns the number of key-value pairs:
```
>>> len(english_to_spanish)
3
```

### Checking in the dictionary

The `in` operator works on dictionaries, too; it tells you whether a value
appears as a key (appearing as a value does not count).
```
>>> 'one' in english_to_spanish
True
>>> 'uno' in english_to_spanish
False
```

To see whether something appears as a value in a dictionary, you can use the 
method `values()`, which returns a collection of values, and the `in` operator:

```
>>> 'uno' in english_to_spanish.values()
True
```
## Further reading: Python docs

Skim the [Python documentation on
Dictionaries](https://docs.python.org/3/tutorial/datastructures.html#dictionaries).

What did you learn? What new questions do you have?

## Try it: Dictionaries

> Practice creating Dictionaries, accessing items, and updating values. 
>
> Try to accomplish the following:
>
> * Use ints and floats as Dictionary values.
> * Use an int and as float as a key. Are `3` and `3.0` the same key? 
>   What about `3` and `3.1`?
> * How do you update a value that's already in a Dictionary?
> * How do you delete a key and value in a Dictionary?
> * What happens if you try to access a key after it has been deleted?

## Further Experimentation

> Once you've explored some of the basics, try to figure out some more
> complicated syntax:
>
> * Add a List as a value in a Dictionary
> * Add a Dictionary as a value in a Dictionary
> * If you store a Dictionary as a value in another Dictionary, how can you
>    access the inner Dictionary's items?
> * Can you use a List as a key in a Dictionary?
