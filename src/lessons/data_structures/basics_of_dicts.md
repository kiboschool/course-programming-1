# 8.1 Dictionary Basics

Estimated Time: 35 Minutes

In this section, you will be introduced to a new data structure in python called a dictionary. What is it? Why do we need it? And basic usage.

## What is a Dictionary
A Dictionary is one of the greatest features of python. It acts a building block for more complicated algorithms and coding solutions.

A dictionary is like a list, but more general. In a list, the indices have to be integers; in a dictionary they can be (almost) any type.

A dictionary contains a collection of indices, which are called keys, and a collection of values. Each key is associated with a single value. The association of a key and a value is called a key-value pair or sometimes an item.

In mathematical language, a dictionary represents a mapping from keys to values, so you can also say that each key “maps to” a value. As an example, we’ll build a dictionary that maps from English to Spanish words, so the keys and the values are all strings.

The function dict creates a new dictionary with no items. Because dict is the name of a built-in function, you should avoid using it as a variable name.

## Basic Concepts
Let us start by some basic commands using dictionaries and build some concepts:
```
>>> eng2sp = dict()
>>> eng2sp
{}
```

The squiggly-brackets, {}, represent an empty dictionary. To add items to the dictionary, you can use square brackets: `>>> eng2sp['one'] = 'uno'`
This line creates an item that maps from the key 'one' to the value 'uno'. If we print the dictionary again, we see a key-value pair with a colon between the key and value:

```
>>> eng2sp
{'one': 'uno'}
```

This output format is also an input format. For example, you can create a new dictionary with three items:
```
>>> eng2sp = {'one': 'uno', 'two': 'dos', 'three': 'tres'}
```
But if you print eng2sp, you might be surprised:
```
>>> eng2sp
{'one': 'uno', 'three': 'tres', 'two': 'dos'}
```

The order of the key-value pairs might not be the same. If you type the same example on your computer, you might get a different result. In general, the order of items in a dictionary is unpredictable.

But that’s not a problem because the elements of a dictionary are never indexed with integer indices. Instead, you use the keys to look up the corresponding values:
```
>>> eng2sp['two']
'dos'
```
The key 'two' always maps to the value 'dos' so the order of the items doesn’t matter.

If the key isn’t in the dictionary, you get an exception:
```
>>> eng2sp['four']
KeyError: 'four'
```
The len function works on dictionaries; it returns the number of key-value pairs:
```
>>> len(eng2sp)
3
```

The in operator works on dictionaries, too; it tells you whether something appears as a key in the dictionary (appearing as a value is not good enough).
```
>>> 'one' in eng2sp
True
>>> 'uno' in eng2sp
False
```

To see whether something appears as a value in a dictionary, you can use the method values, which returns a collection of values, and then use the in operator:
```
>>> vals = eng2sp.values()
>>> 'uno' in vals
True
```

## Dictionary Common Use Case - Collection of Counters
Suppose you are given a string and you want to count how many times each letter appears. There are several ways you could do it:

- You could create 26 variables, one for each letter of the alphabet. Then you could traverse the string and, for each character, increment the corresponding counter, probably using a chained conditional.
- You could create a list with 26 elements. Then you could convert each character to a number (using the built-in function ord), use the number as an index into the list, and increment the appropriate counter.
- You could create a dictionary with characters as keys and counters as the corresponding values. The first time you see a character, you would add an item to the dictionary. After that you would increment the value of an existing item.

Each of these options performs the same computation, but each of them implements that computation in a different way.

An implementation is a way of performing a computation; some implementations are better than others. For example, an advantage of the dictionary implementation is that we don’t have to know ahead of time which letters appear in the string and we only have to make room for the letters that do appear.

Here is what the code might look like:
```
def histogram(s):
    d = dict()
    for c in s:
        if c not in d:
            d[c] = 1
        else:
            d[c] += 1
    return d
```
The name of the function is histogram, which is a statistical term for a collection of counters (or frequencies).

The first line of the function creates an empty dictionary. The for loop traverses the string. Each time through the loop, if the character c is not in the dictionary, we create a new item with key c and the initial value 1 (since we have seen this letter once). If c is already in the dictionary we increment d[c].

Here’s how it works:
```
>>> h = histogram('brontosaurus')
>>> h
{'a': 1, 'b': 1, 'o': 2, 'n': 1, 's': 2, 'r': 2, 'u': 2, 't': 1}
```
The histogram indicates that the letters 'a' and 'b' appear once; 'o' appears twice, and so on.

Dictionaries have a method called get that takes a key and a default value. If the key appears in the dictionary, get returns the corresponding value; otherwise it returns the default value. For example:
```
>>> h = histogram('a')
>>> h
{'a': 1}
>>> h.get('a', 0)
1
>>> h.get('c', 0)
0
```

> **Try it yourself** As an exercise, use `get` to write the histogram more concisely. You should be able to eliminate the if statement.

## Global Variables with Dicts
We recall from Lesson 6.1 that we discussed global variables and how to change them. If a global variable refers to a mutable value, you can modify the value without declaring the variable:

```
known = {0:0, 1:1}

def example4():
    known[2] = 1
```
So you can add, remove and replace elements of a global list or dictionary, but if you want to reassign the variable, you have to declare it:
```
def example5():
    global known
    known = dict()
```
Global variables can be useful, but if you have a lot of them, and you modify them frequently, they can make programs hard to debug.