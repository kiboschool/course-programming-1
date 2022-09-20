# Function argument styles

Estimated Time: 50 Minutes

In this section, you will learn more about function signatures, syntax, and return values.

## Default Argument Values

You recall from "Functions" week that we talked about function arguments. If we have a greeting function with two arguments for example, it would look like something like this:

```python
def greet(name, message):
    print("Hello", name + ', ' + msg)
```

Let us have a closer look at these arguments. What would happen if we call this function with a wrong number of arguments __(one argument for example)__? For instance, `greet("Alice")`
In that case, python interpreter will show an error saying the following:

```TypeError: greet() missing 1 required positional argument: 'msg'```

### Default Argument

There is a way in python where we can program our function to use a `default` argument value in case it did not get a value from the user or the calling function.

Providing a default value can be done using **`=`** operator as follows:
```python
def greet(name, msg="Good morning!"):
    print("Hello", name + ', ' + msg)

greet("Alice")
greet("Ben", "How are you?")
```

Output will be:
```
Hello Alice, Good morning!
Hello Ben, How are you?
```
At this call, `name` is a mandatory argument and the function will not be move forward without it. On the other hand, there is a __default__ greeting message that the function will use in case no other message was inserted.

### Default with non Default Arguments

A function may have a mix of default and non default arguments (mandatory and optional), but if an argument has a default value, all arguments on its right side must have default arguments.

> **_NOTE:_**  **Non-default arguments cannot follow default arguments.**

`def greet(msg = "Good morning!", name):` would get us `SyntaxError: non-default argument follows default argument`

### Calling with keyword argument

We can call function with their keyword arguments. It that case, position would not be important.
```python
# 2 keyword arguments
greet(name = "Bruce",msg = "How do you do?")

# change order
greet(msg = "How do you do?",name = "Bruce")
```
Both calls will work the same.

## Variable Number of Arguments

Some function may need to perform a process on all arguments regardless of how many arguments we pass.

Python allows us to pass a variable number of arguments to functions. Main symbols that are used to achieve that are
-  *args (Non-Keyword Arguments)
- **kwargs (Keyword Arguments)

> **_NOTE:_**  *args allow us to pass variable number of arguments to a function. The star means the input list of variables is iterable.

```python
def greeting(*argv):
    for arg in argv:
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

Another example that uses an extra first argument would look like:
```python
def greeting(first_word, *argv):
    print("First word :", first_word)
    for arg in argv:
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

> **_NOTE:_**  **kwargs allow us to pass variable number of keyworded arguments to a function. Keyworded means that you provide a name for the variable. kwargs are close to a dictionary.

```python
def students(**kwargs):
    for key, value in kwargs.items():
        print("%s == %s" % (key, value))


# call
students(student_1='Ben', student_2='Alice', student_3='Ope')
```
Output:

```
student_1 == Ben
student_2 == Alice
student_3 == Ope
```

### Hybrid Usage of *args & *kwargs
It is possible to use both of *args & *kwargs to pass data to functions. Check the following greeting example
```python
def greeting(*args, **kwargs):
    print("args: ", args)
    print("kwargs: ", kwargs)


# Now we can use both *args ,**kwargs
greeting('Welcome', 'to', 'Kibo', first="Welcome", mid="to", last="Kibo")
```

## Multiple Return Values

We previously talked about the `return` keyword in functions and how can a function return a specific value after performing a process.
What about the cases where we need to return more than one value as an output of a process. We can always use lists and dicts to collect values and return them.
Moreover, we sometimes need to return immutable values for which we can use data type called `tuple`. A tuple is similar to a list but with immutable values.

> **_TODO:_**  Check the differences between a list and a tuple.

Example:
Let us implement a function that takes two numbers and perform addition, subtraction, multiplication, and division upon them.
It would like something like this:

```python
def basic_calculator(a, b):
    sum = a + b
    diff = a - b
    mul = a * b
    div = a / b

    return sum, diff, mul, div
```

Notice the return line -> We can return multiple values one after another with a separating comma. The calling party would get this in a form of a tuple.

How do we access that from the calling side?

```python
num1 = 5
num2 = 10

sum, diff, mul, div = operate(n1, n2)

print(
    f"The sum is {sum}\n"
    f"The difference is {diff}\n"
    f"The multiplication gives {mul}\n"
    f"The division gives {div}\n"
)
```


## Global Variables

Variables in __main__ are sometimes called global because they can be accessed from any function. Unlike local variables, which disappear when their function ends, global variables persist from one function call to the next.

It is common to use global variables for flags; that is, boolean variables that indicate (“flag”) whether a condition is true. For example, some programs use a flag named verbose to control the level of detail in the output:

verbose = True
```python
def example1():
    if verbose:
        print('Running example1')
```
If you try to reassign a global variable, you might be surprised. The following example is supposed to keep track of whether the function has been called:
```python
been_called = False

def example2():
    been_called = True         # WRONG
```
But if you run it you will see that the value of been_called doesn’t change. The problem is that example2 creates a new local variable named been_called. The local variable goes away when the function ends, and has no effect on the global variable.

To reassign a global variable inside a function you have to declare the __global__ variable before you use it:
```python
been_called = False

def example2():
    global been_called
    been_called = True
```
The global statement tells the interpreter something like, “In this function, when I say been_called, I mean the global variable; don’t create a local one.”

Here’s an example that tries to update a global variable:
```python
count = 0

def example3():
    count = count + 1          # WRONG
```
If you run it you get:
```
UnboundLocalError: local variable 'count' referenced before assignment
```
Python assumes that count is local, and under that assumption you are reading it before writing it. The solution, again, is to declare count global.
```python
def example3():
    global count
    count += 1
```