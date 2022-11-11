# Range function

## Range function

There’s another way to tell the `for` loop what values to iterate over. `range()` is a function that generates a series of numbers within a certain range.

```python
# Same loop as before, using range()
for i in range(5,0,-1):
	print(i)
print("Blastoff!")
```

```
5
4
3
2
1
Blastoff!
```

For longer lists of numbers, `range` is easier than typing the whole thing out.

The syntax for the range function is below.

```python
range(start, stop, step)
```

- **_start_** specifies the first value of the range.
- **_stop_** specifies the stopping point.
  - The stop value is **not** included in the range, so `range(1,10)` will only go up to `9`.
- **_step_** specifies how much to count by each time. `range(2,10, 2)` produces `2`, `4`, `6`, `8`.
  - The **default value** is 1, which means that if you leave _step_ out, `range` will count by 1.

Here’s some examples using `range`:

```python
# Print the numbers 1-10
for n in range(1,11): # 11 is not included!
	print(n)

# Print the numbers 5, 10, 15, 20... 100, counting by 5s
for number in range(5, 101, 5):
	print(number)

# Print the numbers counting down from 5 to 1
for i in range(5,0,-1):
	print(i)
print("Blastoff!")
```

## Range Practice

<aside>

🎯 Practice writing `for` loops that use `range`.

- Print the numbers from 4 to 14
- Print the numbers from -10 to 10
- Print the numbers from 1 to 20, counting by 2s
- Print the numbers from 1000 to 500, counting backwards by 100s

</aside>

<iframe src="https://trinket.io/embed/python/3f00eb351f" width="100%" height="400" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
