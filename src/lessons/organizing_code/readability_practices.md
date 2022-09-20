# 6.3 Readability Practices

Estimated Time: 20 Minutes

In this section, you will learn more about functions documentation and readability.

## Argument Annotation
Up to this lesson, we were using functions with direct arguments.

Python 3.5+ allows us to use type hints and argument annotations as follows:

```python
# No Argument Annotation
def greeting(name):
  return 'Hello, {}'.format(name)

# With Argument Annotation
def greeting(name: str) -> str:
  return 'Hello, {}'.format(name)
```

Why would you use `Argument Annotation`:
- **Faster Development:** Argument annotation will uncover mistakes more quickly and protects from passing wrong values.
- **Users of your code:** This syntax will be more clear for members who are trying to use your code.
- **Documentation:** This can be part of your function documentation - some people consider it the whole documentation of the function.

> **_NOTE:_**  Argument Annotation is NOT mandatory and it is NOT a performance booster

## Function Documentation
Python's convention for a function or module documentation is called `Docstring`

__Docstring__ is a string that is usually written as the first statement of a function or module explaining the main functionality of this function or module. 
Docstrings can take the form of one line or multiple lines depends on the information it includes.

### Dcostring example

#### One Line Docstring
One line simple description of the function.
```python
def divide(a, b) -> float:
    """This function divides the value of a by b and returns a float result"""
    pass
```
#### Multi-line Docstring
A paragraph that explains the functionality by adding an explanation of each argument as well as return value options.

```python
def divide(a, b) -> float:
    """
    This function divides the value of a by b and returns a float result

    :param a: First number for division in the form of float (Numerator)
    :param b: Second number for division in the form of float (Denominator)

    :returns: float as the result of a divided by b
    """
    pass
```
