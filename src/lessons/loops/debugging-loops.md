# Debugging loops

Usually it takes more than one try to write the code to solve a problem with loops. When the code isn’t working correctly, you need a strategy for figuring out what is happening, and to fix it.

## Loop debugging: Printing each step

**Printing values at each step** is a strategy for debugging what’s happening in your loop. Let’s see what it looks like.

Here’s some broken code for solving a loop problem:

```python
# Find the total of the even numbers from 2 to 12
total = 0
for i in range(1,12,2):
	total + i
print(total) # 0  <- Wrong, should not be 0!
```

You might be able to spot the bug in this code, but let’s try printing out the values to debug it.

```python
total = 0
print("before the loop total is", total)
for i in range(1,12,2):
	print("i is", i, "total is", total)
	total + i
print("after the loop total is", total)
print(total)
```

Here’s the output:

```
before the loop total is 0
i is 1 total is 0
i is 3 total is 0
i is 5 total is 0
i is 7 total is 0
i is 9 total is 0
i is 11 total is 0
after the loop total is 0
0
```

Wow! It looks like there are actually 3 bugs!

- instead of the even numbers, `i` is getting set to the odd numbers
- instead of including `12`, it’s stopping at `11`
- `total` isn’t changing at all in the loop

### Fixing the code

Since we can see the values, it’s much easier to tell what we need to fix.

- `range` needs to start at `2` (instead of `1`)
- `range` needs to stop at `13` (instead of `12`)
- it needs to be `total += i` instead of `total + i`

When we fix the code, we can leave the `print`s in to make sure our changes work.

```python
total = 0
print("before the loop total is", total)
for i in range(2,13,2):
	print("i is", i, "total is", total)
	total += i
print("after the loop total is", total)
print(total)
```

Now the output is:

```
before the loop total is 0
i is 2 total is 0
i is 4 total is 2
i is 6 total is 6
i is 8 total is 12
i is 10 total is 20
i is 12 total is 30
after the loop total is 42
42
```

Now that we can see that the code is working, we can remove the extra `print` statements. Here’s the final code:

```python
total = 0
for i in range(2,13,2):
	total += i
print(total)
```

## Practice

<aside>

🐛 Practice using `print` to debug a faulty loop.

</aside>

<iframe src="https://trinket.io/embed/python/7f4fc6d772" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

<details>
<summary>Solution (try for 10-20 minutes before looking)</summary>

```python
total = 0
print("total before is", total)
for i in range(10,25,2):
  print("i is", i, "total is", total)
  total + i
print("total after is", total)
print(total)

# BUGS
# - supposed to be the odd numbers (range should start at 11)
# - supposed to include 25 (range should end at 26)
# - should be total += i
```

</details>

## Loop debugging: Visual Tracing

When debugging more complicated code, it’s helpful to be able to see how the code executes step by step. You can use [pythontutor.com](https://pythontutor.com/visualize.html#mode=display) to run your code step by step, and see the values of all your variables as the program runs.

<details>
<summary>🎥 Watch this video to see how to step through the code using PythonTutor</summary>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://youtube.com/embed/LRDpkh58Q1k?rel=0" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

</details>

Similar to printing out the values at each step, PythonTutor helps you see what’s happening when your code runs. That makes it easier to spot bugs.

Here’s the [**example from before in pythontutor**](https://pythontutor.com/visualize.html#code=%23%20Does%20the%20list%20have%20string%20%22Python%22%20in%20it%3F%0Alanguages%20%3D%20%5B%22Ruby%22,%20%22JavaScript%22,%20%22C%22,%20%22Rust%22,%20%22Smalltalk%22,%20%22Clojure%22,%20%22Python%22%5D%0A%0Ahas_match%20%3D%20False%0Afor%20language%20in%20languages%3A%0A%20%20%20%20if%20language%20%3D%3D%20%22Python%22%3A%0A%20%20%20%20%20%20%20%20has_match%20%3D%20True%0A%0Aprint%28has_match%29&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false). Try it out!
