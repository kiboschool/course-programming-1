# Variables and assignment

_Estimated Time: 15 minutes_

---

## What you need to know about variables

- A _variable_ is a name you give to data, so you can use it later in the program
- You assign a variable with `=`
- There are lots names you can use for variables, but there are some rules
- Using meaningful variable names makes your program better

## Video: What are variables?

<aside>

📺 This video explains variables in Python

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.youtube.com/embed/ZDjxKGNfJKo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

<aside>

### Video Notes

- Working with variables and data is a core part of learning programming
- A **Variable** is a named place in memory. We can use it to store data and manipulate it, using its name.
- An **assignment statement** assigns some value (on the right-hand side) to the variable name on the left-hand side. Technically this means putting this value in memory and point to it using that variable name.

</aside>

## Variable Names

<aside>

📺 Watch this video to learn about variable naming rules

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.youtube.com/embed/csYYlAITTzU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

<aside>

### Video Notes

Variable names in Python must follow some rules:

  - We cannot use **reserved words** variables names. Reserved words include words like `if`, `for,` `return`, which have specific meanings in Python
  - Names can start with letters or underscores, and can only contain letters, numbers, and underscores. They can’t have spaces.
  - Variable names are case-sensitive. That means `shop` and `Shop` can refer to different values.

</aside>

### Good and Bad Variable Names

Variable names should be descriptive and help a reader understand the code.

For example, take a look at the code below:

```python
x1q3z9ocd = 35.0
x1q3z9afd = 12.50
x1q3p9afd = x1q3z9ocd * x1q3z9afd
print(x1q3p9afd) # 437.5
```

The variable names above are allowed in Python, but they are **not helpful**.

**Contrast with:**

```python
hours = 35.0
pay_rate = 12.50
pay = hours * pay_rate
print(pay) # 437.5
```

These variable names are descriptive and helpful!

## Practice: Assigning and printing variables

<aside>

👩🏿‍💻 Let's practice assigning values to variables and printing variables. Read the code below, and make the changes requested in the comments.

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/kibo-fpwp6/W11-Practice-Variables-and-Assignment-Practice" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

<details>
<summary><strong>Solution</strong> (try for 5 minutes before looking!)</summary>

```python
books_read = 13
print(books_read)

meals_eaten = 4
meals_eaten = meals_eaten + 1
print(meals_eaten)
```

</details>
