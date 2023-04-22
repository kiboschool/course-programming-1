# Function basics

<aside>

📗 A **function** is a named sequence of statements that performs some useful operation.

</aside>

You’ve used functions like `print`, `random.randint`, and `append` in your programs already, to output values, get random numbers, and add items to lists. Under the hood, those functions are just more code -- code that someone else wrote, and you can use. As you’ll see, a function is like a recipe. Python follows the steps in the recipe when you tell it to.

We’ll see two sources of functions in this lesson. The authors of Python built many useful functions into the language. They’re called *built-in functions.* You can see the full list [here](https://docs.python.org/3/library/functions.html) (fair warning - it's really long!). We can also build our own functions, as you saw in the video. Functions we write ourselves are called _user-defined_ functions.

Both kinds of functions work the same way. They execute the code for that function. The only difference is who wrote them.

### Built-in functions

Built-in functions are functions that are pre-defined in Python, and always available for us to use in our programs. We've seen many built-in functions already, like `print()`, `str()`, `input()`, and more.

One group of built-in functions are type conversion functions. They convert values from one type to another. For example, the function `int()`  takes a value and tries to convert it to an integer.

```python
>>> int('32')
32
>>> int('Hello')
ValueError: invalid literal for int(): Hello
>>> int(3.99999)
3
>>> int(-2.3)
-2
```

### Function call syntax

As you’ve seen already, you call a function by it’s name and parentheses. For some functions, you also need to put some data in between the parentheses for the function to use.

```python
some_function(data1, data2, data3) # a function called 'some_function' that takes in three pieces of data
```

If you just use the function’s name, it doesn’t run the function:

```python
input # doesn't run the function
print # doesn't run the function
int # doesn't run the function
```

You need parentheses, and whatever data is needed to run the function.

```python
input()
print("Hello, world!")
int("32")
```

### Vocabulary

You’ve already learned the word *function.* Let’s cover the other words for associated concepts:

- **Run** a function, also called **executing, invoking** or **calling** a function. *Run*, *execute*, *invoke*, and *call* all mean the same thing: tell Python to follow the instructions — do the action for the function. For `print`, actually print something. The syntax for running (calling, executing) a function is the name, plus the parentheses, so `print()`.
- The data that goes in between the parentheses are called **arguments.** So, for a function call `print("Hello", 12345)`, you’d say that `"Hello"` and `12345` are the *arguments to the function.* As you’ll see, functions take in arguments, and use the arguments in their operation.
- Functions like `int("32")` **return** a value. After running the function, the code “gets back” a value that it can store in a variable, or use in some other expression.
- Sometimes, you’ll see functions called  **methods**. **Method** is a name for a function that’s associated with some type of data. In `"Hello".upper()`, we would say the function `upper` is a method. It’s available to use with strings like  `"Hello"`, and it uses the `.` syntax, instead of a freestanding call like `upper("Hello")`.

### Investigate: Built-in Functions

<aside>

❓ Take a look at the list of built-in Python functions [here](https://docs.python.org/3/library/functions.html). Choose a function that you have not already seen in the class, and do a bit of research into its use. You should tell us:

- The name of the function.
- What it does (in your own words).
- The arguments (i.e. inputs) it requires.
- The results it gives.
- At least two examples of its use.

Share your findings below. Click the `+` in the pink circle to add your response

</aside>

<aside>

🧪 **Try it out!**
After you’ve found a built-in function, open a Python repl and test out the function. Copy and paste or take a screenshot of what the function does, and add it to your answer.

</aside>

<div style="border:1px solid rgba(0,0,0,0.1);border-radius:2px;box-sizing:border-box;overflow:hidden;position:relative;width:100%;background:#F4F4F4"><iframe src="https://padlet.com/embed/wvz0a2bij7sqvfgl" frameborder="0" allow="camera;microphone;geolocation" style="width:100%;height:608px;display:block;padding:0;margin:0"></iframe></div>

