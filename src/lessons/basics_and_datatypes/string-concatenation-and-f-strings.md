# String concatenation and f strings

## Key ideas

- Using formatted strings
- Concatenating strings

## String Concatenation and f-strings

When there’s a variable we want to combine with a string to print out a message, so far we’ve added the strings with `+`.

```python
name = "Mercy"
print("Hello, " + name) # Hello, Mercy
```

When the message is longer, this becomes more confusing and harder to type.

```python
name = "Mercy"
print("The alarm went off at exactly 6:00 AM as it had every morning for the past five years. " + name + " began her morning and was ready to eat breakfast by 7:00 AM. The day appeared to be as normal as any other, and " + name + " was not expecting anything to change.")
```

There’s another way to format long text that uses variables, called **f-strings.**

```python
name = "Mercy"
print(f"Hello, {name}") # Hello, Mercy
print(f"The alarm went off at exactly 6:00 AM as it had every morning for the past five years. {name} began her morning and was ready to eat breakfast by 7:00 AM. The day appeared to be as normal as any other, and {name} was not expecting anything to change.")
```

Instead of using `+` to combine the variable and the string, we start the string with `f` and we use `{}` to insert the variable right inside the string. That way, there’s less confusion about quote marks and spaces.


<div style="position: relative; padding-bottom: 62.5%; height: 0;"><iframe src="https://www.loom.com/share/1d6800ff8c9f479f9a3ffd03f89e3c34" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>


### Other f-string uses

We can also use f-strings for rounding.

```python
one_third = 1/3
print(one_third)# 0.3333333333333333
print(f"{one_third:.2}") # 0.33
```

f-strings have other formatting powers, but we’ll leave it at rounding floats for now.

## Practice: f-strings

<aside>

👩🏿‍💻 Practice using f-strings to format results.

</aside>

Open a new file in VSCode to practice with f-strings.

* Try printing some messages using f-strings and variables
* Try rounding a float to a specific number of digit

Looking at the f-strings documentation, what other tricks do you want to try? If
you find something you think is particularly useful or interesting, share it
with your classmates in Discord.

<details><summary>Solution: F-strings practice</summary>

```python
first_num = float(input("enter first number: "))
second_num = float(input("enter second number: "))

result = first_num / second_num

print(f"the result is {result:.3} ")
```

</details>
