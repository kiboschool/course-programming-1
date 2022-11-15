# Functions

One of the core purposes of functions is to split programs up into pieces that _make sense_.

Good functions should represent just one task that a program has to do. Instead of
doing every operation one line after the other, functions isolate parts
of the problem, so that your code can be simpler.

## Helper Functions

You might use functions just to **help** other functions work, making it easier to read and organize your code without so much thinking about reusability. Sometimes we call such functions **helper functions**. Some people use the names "function" and "helper function" to mean the same thing, as functions always help.

## Decomposition

One of the main concepts to approach solving problems is **Decomposition**.
That means taking a big problem and decomposing it into smaller ones.

A task like _"build a simulator for a microprocessor"_ sounds really
complicated! But, if you break it down into small pieces, like "add two numbers"
and "find which of two numbers is greater than the other", each of those small
pieces seems much more manageable.

Approaching each step as a standalone problem makes the whole program easier to implement.

<!-- A function that solves just one piece of a larger program is called a **helper function**. -->

## Case Study: Geometry Tutor

Let's apply the **Decomposition** strategy to design a program.

Imagine you are asked to build a program to assist 7th grade students in understanding how to calculate area of various shapes.

The program should ask the user to enter a shape from a list, for example:

```txt
Rectangle
Circle
Triangle
```

Depending on the choice the user enters, it asks the user to enter the to calculate the area of the needed shape.

One option is to implement the whole code into one long file without splitting it into functions.

<aside>
As a practice, implement the above program without using functions and try to answer the below questions:
</aside>

- What would need to change about the program if it needed to support another shape?
- What would need to change about the program if it needed to display the _perimeter_ as well as the area?
- If you wanted to use the shape functions in another project, how would you do that?
- A team member of yours wants to give you a hand in implementation - how would you organise this?

Let's explore what the code would look like if we used functions.

- Part 1: **Functions** - operations that program would need
- Part 2: **Main Flow** - steps for user interaction, using the helper functions

We will start functions into an internal module called `utilities.py`:

```python
from math import pi

def circle_area(radius):
    area = float(pi*r*r)
    return area

def rectangle_area(length, width):
    area = float(length * width)
    return area

def triangle_area():
    are = float((base*height)/2)
    return area
```

Once the helper functions are ready, we can write the main flow:

```python
from utilities import circle_area, rectangle_area, triangle_area

area = 0
shape_choice = input("Enter a shape to find its area: \nCircle \nRectangle \nTriangle")

if shape_choice.lower() == 'circle':
    radius = input("Please enter the radius of the needed circle")
    area = circle_area(radius=radius)

elif shape_choice.lower() == 'rectangle':
    length = input("Please enter the lenght of the needed rectangle")
    width = input("Please enter the width of the needed rectangle")
    area = rectangle_area(length=length, width=width)

elif shape_choice.lower() == 'triangle':
    height = input("Please enter the height of the needed triangle")
    base = input("Please enter the base of the needed triangle")
    area = circle_area(base=base, height=height)

else:
    print(f"Selected shape is not supported {shape_choice.lower()} - Please choose an item from the list")

print(f"Calculated area for {shape_choice} is {area}")
```

This design has very different answers to our questions above!

> What would need to change about the program if it needed to support another shape?

A new shape function will be added to the utility module, so you can import it anywhere in your code.

> If you wanted to use the shape functions in another project, how would you do that?

You could import the utilities module using `import utilities` after having a clear path for module.

> A team member of yours wants to give you a hand in implementation - how would you organise this?

Working with other team members will be easier. Team members can use functions the others have written, and add or change functions without all editing the core driving logic.

## What makes good functions?

**Reusability:** Functions should be reusable. Since they can be called from
somewhere else in the program, it's important to make sure that they are
reusable. Usually, that means writing functions whose inputs and outputs are
clear, and don't depend on or affect anything outside of the function.

**Readability:** Other programmers will read your functions to tell what your
code does. Choosing good names for your functions and arguments will make
your code more clear to them (or to you!)

Usually, you want functions to be short, do just one job, and be named
based on what they do.
