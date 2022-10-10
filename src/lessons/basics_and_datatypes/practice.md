# Practice: Basics and Datatypes

---

> 💡 This is your chance to put what you’ve learned into action.
>
> Try solving these practice challenges to check that you understand the concepts.


## Why practice?

Practice coding helps you become a great coder. These practice problems aren't
graded, but that doesn't mean they aren't important.

You should aim to practice a lot, especially with unfamiliar concepts. Spread practice over multiple days to take advantage of the _spacing effect_, which helps you retain new knowledge.

<details><summary>More about practice</summary>

Practice helps you understand what you know, and what you don't know. It can be easy to trick yourself into thinking you understand something when you
do not -- or that you don't understand when you do. Practicing by writing code
or debugging code will help you find out what you really understand, and where
you are still confused.

Practice helps build confidence in your coding. The more programs you write, and
the more problems you solve, the more you learn that you are a capable coder and
problem-solver.

Practice doesn't always feel good - sometimes you'll be stumped! But, practice
shouldn't feel super frustrating either. If you find yourself getting angry at
yourself or the code, it's a good time to take a break and ask for help. 

On the flip side, if practice feels too easy, it means you aren't challenging yourself
enough. If the practice problems early in the course are not challenging for
you, take a look at the [Additional Practice page](lessons/additional-practice.md). You should still complete these exercises, so that you can confirm that you 

The **solutions** to each challenge are available, and you can view a video of the solution below each challenge.

* Try to go through the whole challenge without using the solution.
* If you can’t do the challenge without looking the solution, it means you don’t understand the material well enough yet.
* Try the next practice challenges without looking at the solution. If you need more practice challenges, reach out on Discord.

</details>

<aside>

**If you get stuck**
1. Read the instructions again.
2. Remember **G**o **C**limb **K**ibo - first Google, then ask the Community on Discord, then reach out to Kibo instructional team.

</aside>

## Submission

**Reminder**: This practice is not graded. You should submit your work on Github
Classroom so that your instructor can check your code, but you will not normally
get feedback on the practice assignments.

This video shows how to get assignment code onto your computer, and how to
submit it to Github Classroom. You can ignore the parts about submitting in
Gradescope and Woolf for the practice exercises.

<details><summary>Video</summary>

<div style="position: relative; padding-bottom: 62.5%; height: 0;"><iframe src="https://www.loom.com/embed/b6f344e3887d46d7a63d5cafac2fc21e" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

</details>

## Currency Conversion

🏦 Create a program that asks a user for a value in US Dollars, then converts to Nigerian Naira.

[![usd-to-naira-conversion](https://img.shields.io/static/v1?label=Open%20Project&message=usd%20to%20naira%20conversion&color=blue)](https://classroom.github.com/a/ZnWyZy0q)

Watch the video below to see the full solution.

Make sure you give yourself enough time to solve the practice without watching the video. It is really important for your learning.

<details><summary>Currency Conversion Solution Video</summary>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.youtube.com/embed/urMYOnhxOiI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
</details>


## AC Load Estimator

👩🏿‍💻 Write a program to build an AC unit load estimator.

Your program should get input from the user, use the formula to calculate the horsepower, then print the horsepower.

[![ac-load-estimator](https://img.shields.io/static/v1?label=Open%20Project&message=ac%20load%20estimator&color=blue)](https://classroom.github.com/a/s2-DiaVB)

Watch the video below to see the full solution.

Make sure you give yourself enough time to solve the practice without watching the video. It is really important for your learning.

<details><summary>Load Estimator Solution Video</summary>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.youtube.com/embed/66tvjwqNiRU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

    ******There is a typo in the code at the end of the video ("numbe" should be "number").*

</details>


## Body Mass Index

💪🏿 Create a program that calculates body mass index, which is used to determine if a person's weight is a healthy proportion for their height.

[![body-mass-index](https://img.shields.io/static/v1?label=Open%20Project&message=body%20mass%20index&color=blue)](https://classroom.github.com/a/ZWmrKX-j)

Watch the video below to see the full solution.

Make sure you give yourself enough time to solve the practice without watching the video. It is really important for your learning.

<details><summary>Body Mass Index Solution</summary>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.youtube.com/embed/vuy5ScUuMYk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
</details>

## Decryption

Encryption and decryption play an important role in information security and computer science. It’s used everywhere to secure the transmitted data between two entities. In this exercise, we have a sample program that decrypts secret messages. In this task, you will follow some steps to decrypt a secret message.

[![decrypt-me](https://img.shields.io/static/v1?label=Open%20Project&message=decrypt%20me&color=blue)](https://classroom.github.com/a/KZUCkenD)

<details><summary><strong>Watch the video to see the full solution. </strong></summary>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/bd70ce6e605a48fbad8742da64b9a03d" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

</details>

<aside>

### Importing Packages

As the course moves on, you'll write more and more complicated programs. So far,
each program has been made of just one file. Python allows you to split code
into different files, and then use functions from a different file in your code.

To use a function from another file, you'll use the `import` keyword.

Here's an example:

```python
# import
import random

# print a random int between 1 and 100
print(random.randint(1,100))
```

This code imports the `random.randint` function to generate random numbers.

In the practice exercise on Decryption and the bonus task for the week
1 project, you'll to see `import` in action. You'll learn more about functions,
files, and packages later on in the course.

</aside>
