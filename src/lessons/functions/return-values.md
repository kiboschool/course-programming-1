# Return Values

```python
def add(a, b):
  return a + b
```

Often, a function will take its arguments, do some computation, then return a value to be used where the function was called. The `return` keyword is used for this. In our example, the statement `return a + b` is called the *return statement*. It ends the function execution and 'sends back' the result of the function.

It is common to say that a function “takes” arguments and “returns” a result.

Note that some functions do not necessarily return a result.

You can visualize a function as a machine that takes in arguments, and spits out the return value:

![Function Inputs and Outputs](/images/function-inputs-outputs.png)

Concretely, for the `add` function that we defined and called like this:

```python
def add(a,b):
	return a + b

add(3,5)
```

![Function Return Values](/images/function-return-values.png)

Programs can use the return value for further operations:

```python
result = add(3,5)
print("the result was", result) # the result was 8
bigger_result = add(result, 10)
print("the bigger result was", bigger_result) # the bigger result was 18
```

## Return vs. Print

`print` is different from returning a value. If you use `print`, a message shows up in the console, but the rest of the program doesn’t get to see it.

```python
def add_and_print(a,b):
	print(a + b)

result = add_and_print(3,5) # 8
print("the result was", result) # the result was None
```

The `print` in the function will print out the value, but it will not return it. `None` is the value that functions return by default. If they don’t return something else, they return `None`.

![Return None](/images/return-none.png)

<aside>

⚠️ `print` is different from `return`. So far in the course, you’ve used `print` to see results, so you are used to using lots of `print`. In more complicated programs, `return` is used more often.

Most of the practice exercises from now on will require you to use `return`, not `print`

</aside>

## Practice

<aside>

👩🏿‍💻 Write two functions. The first, called `print_double`, should print out a number times two. The second, `return_double`, should return two times the argument instead of printing.

Run the code to see the results.

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/fpwp-feb2022/W42-Double-Doubles" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## Types of return values

Functions return different types of values. Here is an example of a function that checks if a given username is valid or not. It returns a boolean:

```python
def is_valid(username):
  if len(username) > 5:  #checks to see if username has more than 6 characters
    return True
  else:
    return False

print(is_valid('user'))    # will print False
print(is_valid('mhassan')) # will print True
```

You can return any of the types you’ve learned so far from a function - numbers, strings, booleans, or lists.