# Complexity

When computer scientists think about algorithms, they care about how fast the
algorithm will be.

Of course it will take longer to sort a list of 1000000 items than to sort a
list of 100 items. So, instead of considering how many seconds a given program
takes to run, it's better to compare algorithms based on how the runtime
increases as the size of the input increases.

* If an algorithm takes the same amount of time, no matter how big the input is,
that's great!
* If the algorithm takes one more step for every item in the input, that's okay.
* If the algorithm takes twice as much time for every item in the input, that's
  really bad!

_Complexity_ is how you can measure how fast an algorithm is, relative to the
size of the input.

## Binary Search

On average, how many guesses does it take to win the Guess the Number game?

Well, each time, we cut the search space in half. We win when the search space
is down to just 1 element. Here's the search space size by step:

* Step 0: 100
* Step 1: 50
* Step 2: 25
* Step 3: 12.5
* Step 4: 6.25
* Step 5: 3.125
* Step 6: 1.5625
* Step 7: 0.78125

So, it will take us six or seven guesses to get to the answer.

> **Question**: How many guesses would it take if the number was between 1 and
> 1000? What about 1 and 1 million? 1 and 1 billion?

Binary Search complexity grows with the _log base 2_ of the input size.

```txt
log2(100) = 6.644
```

That's really good! The logarithm function grows very slowly. Even if we had to
search among 10 billion random numbers, it would only take about 33 guesses!

```python
>>> math.log2(10000000000)
33.219280948873624
```

## Insertion Sort

To analyze how many steps there are in insertion sort, we have to think about
the nested loops.

Here's the core of the algorithm, with some pieces left out:
```python
  for item in a_list:
    for i in range(len(results)):
      if item <= results[i]:
        results.insert(i, item)
```

If `a_list` is 100 items long, and `results` is 100 items long (which it will
be, at the end of the process), then this loop has to check 100 * 100 = 10000
times.

How does that grow when the input grows?

| List size | Steps in worst-case insertion sort |
|---|---|
| 1 | 1 |
| 10 | 100 |
| 100 | 10000 |
| 1000 | 1000000 |
| 10000 | 100000000 |
| 100000 | 10000000000 |

Yikes!

The steps grow with the _square_ of the input size. That's bad, because the
square grows quickly!

Any time you have nested loops, take care. If both loops will have as many steps
as the elements in the list, and the list might get big, then you could be
creating a big source of slowness in your program.

Thankfully, there are sorting algorithms that are faster than insertion sort!
