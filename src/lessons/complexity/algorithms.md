# Algorithms

In this lesson, you'll encounter two classic algorithms: Binary Search and 
Insertion Sort.

In future courses, you'll learn more algorithms in more detail; for now it's
enough to get a basic picture of what an algorithm is.

## What's an algorithm?

An algorithm is a set of instructions to perform a computation.

By that definition, every program and function you've written so far is an
algorithm. That's interesting, but it isn't very helpful.

Typically, when computer scientists describe an algorithm, they aren't talking
about a particular implementation, or about any program whatsoever. Usually,
they are interested in specific algorithms to solve problems that show up again
and again.

Computer scientists are interested both in inventing or applying algorithms to 
solve problems encountered in the real world, and in analysing and understanding
the properties of different algorithms, especially how long they take to run and
how much memory they use.

Let's see a couple example algorithms.

## Binary Search

Way back when you learned about loops, you may have written the Guess My Number
game. The way the game works is that the program chooses a random number between
1 and 100, and the player guesses. If they guess the number, they win. If they
guess too low or too high, the program tells them that and lets them keep
guessing.

<details><summary>(See the video if you need a refresher)</summary>
<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/c4e8de950300449f814416d6665809cc" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
</details>

What is the best strategy for the _guesser_?

Well, the worst that could happen is that they have to guess all the wrong 
numbers before they get it right, like if the number was 99 and they started
guessing at 1, then 2, then 3 and so on. That would take 99 guesses.

The same would be true you started guessing at 99, then counted down -- the
random number might be _1_, and you would have to guess 99 times.

If you started at _50_, then no matter if the program said your guess was too
high or too low, you would always only have 49 more guesses to go. You cut the
search space in half.

If you keep guessing the _middle number_ of the range of numbers that are
left, then you keep cutting the search space in half every time.

```txt
I'm thinking of a number between 1 and 99
Enter a guess: 50
Your guess is too low
Enter a guess: 75
Your guess is too low
Enter a guess: 87
Your guess is too high
Enter a guess: 81
Your guess is too low
Enter a guess: 84
Congrats! The number was 84
```

This strategy is called _Binary Search_. 

The idea of the binary search algorithm is to cut the search space in half at
each point, and then cut in half again.

To specify the steps more carefully for the number game:

```txt
- Start the low end of the range at 1 and the high end of the range at 100
- Choose the midpoint of the range with Floor(low + high / 2)
- Check the midpoint
  - If it's the answer, stop
  - If too high, set the high end of the range to the midpoint
  - If too low, set the low end of the range to the midpoint
- Repeat with the updated range 
```

For the guess my number game, we're guaranteed that the number is in the range.
Usually, we don't get that guarantee!

> **Challenge**: If instead of an interactive game, you had a sorted list of 100
> elements, could you write a Python function to check if a particular element
> is in the list? Use binary search and the `==` operator, not the `in`
> keyword.

**Further Reading**: [Binary Search on Wikipedia](https://en.wikipedia.org/wiki/Binary_search_algorithm)

## Insertion Sort

In order for Binary Search to work, the numbers have to be in sorted order.

Binary search works well on data like:

```txt
[2,4,12,19,20,22,23,29,31,32,33,40,45,49,53,54,68,71,72,73,76,81,88,91,99]
```

But it doesn't work if that data is shuffled around:
```txt
[12,49,72,33,40,81,19,53,88,99,32,2,4,76,68,23,71,20,91,45,31,54,73,29,22]
```

If you tried to check the midpoint, it wouldn't tell you anything about whether
your number was in the list!

Sorting a list so that it's in ascending (or descending) order is a really
common problem, so there are a few algorithms to do the job.

One algorithm to sort a list is called Insertion Sort. Here's the idea:

```txt
- keep a sorted sublist, which starts empty
- step through each element in the list to sort
- search through the elements in the sublist to find where it belongs (the first element it is smaller than)
- insert it in that spot
```

You step through the whole list, finding the right spot in the resulting sorted
array for each element and inserting it there.

Here's one version of the algorithm in Python:

```python
def insertion_sort(a_list):
  results = [a_list[0]]

  for item in a_list:
    if item >= results[-1]: 
      results.append(item)
      continue

    for i in range(len(results)):
      if item <= results[i]:
        results.insert(i, item)
        break

  return results
```

It starts by adding the first item to the result list (instead of starting the
result list empty) and it has to have an additional check to see if the item is
larger than all the items in the sublist. Otherwise, it just does the nested
loop, like the description.

> **Question**: How many times does this function have to _compare_ two items?
>
> **Challenge**: Could you implement this function "in place"? That is, can you
> rewrite it so that it changes the original array instead of creating a results
> array?
