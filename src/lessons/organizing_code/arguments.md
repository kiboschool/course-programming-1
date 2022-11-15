# Function Arguments

You've written lots of functions that accept arguments. Python has a few ways to write and call functions that make functions more readable and flexible.

## Keyword arguments

Python allows us to pass arguments using their names. This way, you can pass arguments without caring about the order. This feature called _keyword arguments_. Here's a simple example to
demonstrate the syntax:

```python
def greet(name, msg):
  print("Hello,", name, msg)

# keyword arguments
greet(name="Bruce", msg="How do you do?")

# change argument order, but the result is the same
greet(msg="How do you do?", name="Bruce")
```

Both calls will work the same. In the code where you call the function, you
can use the name of the argument to assign the value to that argument.

This is particularly useful if a function takes in lots of arguments. It makes
it really clear which values are doing which job.

## Default Argument Values

If we have a greeting function with two arguments for example, it would look like something like this:

```python
def greet(name, msg):
    print("Hello", name + ', ' + msg)
```

Let us have a closer look at these arguments. What would happen if we call this function with a wrong number of arguments **(one argument for example)**? For instance, `greet("Alice")`

In that case, python interpreter will show an error saying the following:

```
TypeError: greet() missing 1 required positional argument: 'msg'
```

We can change the function to use a **default value** if there is no argument
passed in when the function is called.

Provide a default value using the **`=`** operator:

```python
def greet2(name, msg="Good morning!"):
    print("Hello", name + ', ' + msg)

greet2("Alice")
greet2("Ben", "How are you?")
```

The output will be:

```
Hello Alice, Good morning!
Hello Ben, How are you?
```

In `greet2`, there is a default value for the `msg` parameter that the function will use if no other message is provided. The first parameter `name` is still required: the function will encounter an error without it.

### Mixing default and required arguments

A function may have a mix of default and non default arguments. But, if a parameter has a default value, all the following parameters must also have default arguments.

If we try to write the function with a default argument first, we get an error:

```python
def greet(msg = "Good morning!", name):
    print("Hello", name + ', ' + msg)
```

Results in: `SyntaxError: non-default argument follows default argument`.

## Variable Number of Arguments

Some functions may need to perform a process on all arguments, regardless of how many arguments we pass.

For instance, no matter how many values you pass into the `print` function, it
prints all of them out:

```python
print(1)
print(1,2)
print(1,2,3,4,5,6,7,8,9,10)
```

Python allows you to pass a variable number of arguments to functions, using `*args` (pronounced 'star args').

### `*args`

`*args` allows us to pass a variable number of arguments to a function.

The star collects all the arguments into a list.

```python
def greeting(*args)
    # args is a list with the arguments
    for arg in args:
        print(arg)

greeting('Welcome', 'to', 'Programming 1', 'at', 'Kibo')
```

Output:

```
Welcome
to
Programming 1
at
Kibo
```

Star args don't have to appear in the first position.

An example that with another argument first:

```python
def greeting(first_word, *args):
    print("First word :", first_word)
    for arg in args:
        print(arg)

greeting('Greeting','Welcome', 'to', 'Programming 1', 'at', 'Kibo')
```

Output:

```
First word: Greeting
Welcome
to
Programming 1
at
Kibo
```

The name of the collection argument is often called `args` by convention, but it doesn't
have to be. Here's an example where it's called `numbers` instead:

```python
def product(*numbers):
  total = 1
  for number in numbers:
    total *= number
  return total

print(product(5, 2, 10, 10))
```

output:

```
1000
```

_Note: there is a related concept `**kwargs`, for keyword arguments that you may have heard reference to online. We'll introduce it when covering Dictionaries later in the course._

## Multiple Return Values

You already know how to use the `return` keyword to return a specific value from a function.

What about the cases where you need to return more than one value?

Python only **allows returning a single value** from a function, but using a _wrapper_ like a list or tuple, you can return more than one thing.

For example, here is a function that takes two numbers and performs addition, subtraction, multiplication, and division upon them.

```python
def basic_calculator(a, b):
    sum = a + b
    diff = a - b
    mul = a * b
    div = a / b

    return [sum, diff, mul, div]
```

## Tuples

But, a list isn't always the right way to represent this. A list can have items added to it or removed from it, and that isn't what usually what we mean when we return a value.

Python offers another data type called `tuple` which is like a list, but with _immutable_ values - we can't change what's in it.

<details><summary> Look up the differences between a list and a tuple in the Python docs</summary>

From the [Python docs](https://docs.python.org/3/tutorial/datastructures.html#tuples-and-sequences):

> Though tuples may seem similar to lists, they are often used in different situations and for different purposes. Tuples are immutable, and usually contain a heterogeneous sequence of elements that are accessed via unpacking (see later in this section) or indexing (or even by attribute in the case of namedtuples). Lists are mutable, and their elements are usually homogeneous and are accessed by iterating over the list.

So, in most situations, lists have values of the same type (for example a list of strings or a list of numbers), and a tuple would have a mix of strings, numbers, or other types of values.

</details>

Tuples support a pair of useful syntactic operations called _packing_ and _unpacking_. That means we can rewrite the function like this:

```python
def basic_calculator(a, b):
    sum = a + b
    diff = a - b
    mul = a * b
    div = a / b

    return sum, diff, mul, div
```

Python will 'pack' the return values into a single Tuple value, then return the Tuple.

How do we access that from the calling side?

If we just do a normal function call, we'd have to remember which index of the result represented which value

```python
result = basic_calculator(5, 10)
# is the product result[1] or result[2]?
```

Instead, we can use the _unpacking_ feature of Tuples and assign to lots of variables at once:

```python
sum, diff, mul, div = basic_calculator(5, 10)

print(
    f"The sum is {sum}\n"
    f"The difference is {diff}\n"
    f"The multiplication gives {mul}\n"
    f"The division gives {div}\n"
)
```
