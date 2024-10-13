# Nested Conditionals

One of the coolest things about Python is that you can use pieces of syntax in lots of situations.

The code in an `if` statement's body can have any valid Python.

```python
if 5 < 15:
  print("We can do anything in here")

  possible = 10
  print("possibilities:", possible)
  possible = possible * 100
  print("possibilities:", possible)
  possible = possible * 100
  print("possibilities:", possible)
  possible = possible * 100
  print("possibilities:", possible)
  possible = possible * 100
  print("possibilities:", possible)
  print("TOO MANY POSSIBILITIES")
```

We can even put **another if statement** in the body of an if statement.

```python
if x > 10:
  print("x is greater than 10")
  if y > 10:
    print("and, y is greater than 10")
```

<details><summary>What will be printed if x = 5 and y = 15?</summary>

Nothing!

If x = 5 and y = 15, `x` is less than 10. That means the whole body below that
if statement won't run -- including the second if statement.

</details>

When there's one conditional statement inside another, it's called a **nested
conditional**. The inner conditional is _nested_ in the outer one.

The trick to reading nested conditionals in Python is to keep careful track of
the indentation. Each block keeps going until the code is no longer indented.
You sometimes have to look very carefully to match up each `else` with the
corresponding `if`, especially when there's lots of nesting and conditions.

Here's an example with lots of nesting:

```python
password = input("password: ")

if len(password) > 8:
  if any(number in password for number in "0123456789"):
    if password != password.lower():
      if password != password.upper():
        print("Password valid. Account created.")
      else:
        print("password must contain a lowercase letter")
    else:
      print("password must contain an uppercase letter")
  else:
    print("password must contain a number")
else:
  print("password too short, must be more than 8 characters.")
```

With this many levels of nesting, it's a little hard to tell which statement
goes with which, but you can still match them up.

Copy this code and try it out! You may have to practice using the tab key on
your keyboard 😉.
