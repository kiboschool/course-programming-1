# Nesting

In the last lesson, you saw that sometimes it makes sense to model data using 
_both_ Lists and Dictionaries -- putting Dictionaries inside Lists, or Lists 
inside Dictionaries.

"Putting things inside each other" is called _nesting_, and you've seen it
before with nested conditionals (and maybe nested loops!). When Dictionaries and
Lists get nested in each other, the syntax can be a bit confusing to read and
write.

This lesson is just about code with nested dicts and lists.

## Lists in Lists

Lists with lists inside are sometimes called _2D Arrays_, since they can be said
to have multiple "dimensions".

Here's a list of grayscale pixel brightness values for each row in a 9x9 image:

```python
image = [
  [44, 181, 237, 0, 162, 110, 181, 121, 253],
  [106, 9, 210, 250, 135, 207, 139, 121, 237],
  [217, 36, 161, 224, 173, 183, 143, 109, 252],
  [23, 66, 136, 179, 10, 86, 9, 182, 14],
  [186, 99, 123, 213, 191, 45, 139, 146, 85],
  [214, 197, 214, 226, 39, 129, 249, 86, 215],
  [105, 182, 219, 190, 251, 15, 33, 147, 143],
  [216, 100, 234, 139, 14, 98, 249, 26, 144],
  [223, 141, 92, 194, 12, 158, 254, 48, 85]
]
```

To access the first row, you'd use `image[0]`. To access the first pixel in the
first row, you'd use `image[0][0]`.

> **Questions**
> * How would you update the 4th pixel in the 5th row?
> * How would you loop through all the pixels in the last row?
> * How would you loop through all the pixels in all the rows?

## Lists in Dicts

Dicts are useful for giving structure to data. Sometimes that structure might
include Lists! In a previous example, we used a Dictionary to model the
attributes for a Pokemon. If we wanted to keep track of the Pokemon's moves, we
might keep a list of moves in the dict:

```python
pikachu = {
  "name": "Pikachu",
  "health": 50,
  "attack": 27,
  "moves": [
    "charm",
    "growl",
    "quick attack",
    "thunder shock",
  ]
}
```

To access the list of moves, you would use `pikachu["moves"]`. To get the first
move, you would use `pikachu["moves"][0]`.

> **Questions**
> * How would you access the third move?
> * How would you change the second move to "thunder wave"?
> * How would you loop through all the moves and print out each one?

## Dicts in Lists

Often, there's a similar structure to add to many identical items. You can add
the structure using Dictionaries, then keep all the items in a List.

In a previous lesson, we modeled restaurant information using a dict. Let's see
what it would look like with a list of multiple restaurants:

```python
restaurants = [
  {
    "name": "Chicken Republic", 
    "cuisine": "Fast food",
    "expense": "$",
    "rating": 3.7,
  },
  {
    "name": "Domino's Pizza", 
    "cuisine": "Pizza",
    "expense": "$$",
    "rating": 4.1,
  },
  {
    "name": "Cold Stone Creamery", 
    "cuisine": "Ice Cream",
    "expense": "$$",
    "rating": 4.5,
  }
]
```

To access the first restaurant, you'd use `restaurants[0]`. To access the name
of that restaurant, you'd use `restaurants[0]["name"]`.

The access syntax is similar! You have to think about whether the list or the 
dict comes first.

> **Questions**
> * How would you access the cuisine of the second restaurant?
> * How would you update the expense of the last restaurant?
> * How would you loop through all the restaurants and print their names?
> * How would you loop through all the restaurants and print their names, but
>   only if the rating is above 4?

## Dicts in Dicts

Fairly often, there's structured information inside other structured
information. For instance, we might want to know the effects of each of the
pokemon's moves. Instead of a List, we could store a dictionary:

```python
pikachu = {
  "name": "Pikachu",
  "health": 50,
  "attack": 27,
  "moves": {
    "charm": "lowers the opponent's attack",
    "growl": "lowers the opponent's attack",
    "quick attack": "deals damage to the opponent, with priority",
    "thunder shock": "deals damage to the opponent, and has a chance to paralyze the target",
  }
}
```

As before, you would access the moves using `pikachu["moves"]`. You would get
the effect of the move `"charm"` with `pikachu["moves"]["charm"]`.

> **Questions**
> * How would you access the effect of the move "growl"?
> * How would you add the move "thunder wave" and its effect?
> * How would you remove the move "growl"?
> * How would you loop through all the moves and print out their names and
>   effects?
> * If you wanted to keep more information about each move (like the type,
>   level, and power), how would you structure the data?

## Deeply Nested Structures

"Dicts in Lists in Dicts in Dicts" sounds like a line straight out of Dr. Seuss,
but deeply nested structures show up all the time in real programs!

Let's see it applied to our restaurant example:

```python
restaurants = [
  {
    "name": "Chicken Republic", 
    "cuisine": "Fast food",
    "expense": "$",
    "rating": 3.7,
    "menu": [
      {
        "name": "Express Meal with Chips",
        "price": 1900,
      },
      {
        "name": "Quarter Rotisserie Chicken",
        "price": 1500,
      }
    ]
  },
  {
    "name": "Domino's Pizza", 
    "cuisine": "Pizza",
    "expense": "$$",
    "rating": 4.1,
    "menu": [
      {
        "name": "Any Medium Classic + Free Drink",
        "price": 4000,
      },
      {
        "name": "Any Large Classic Thin Crust Pizza",
        "price": 5000
      }
    ]
  },
]
```

Accessing the name of the first item on the menu at the first restaurant:

```python
restaurants[0]["menu"][0]['name']
# => "Express Meal with Chips"
```

It's sometimes helpful in these situations to use intermediate variables, so
that you can keep track of what is what:

```python
chicken_republic = restaurants[0]
cr_menu = chicken_republic["menu"]
express_meal = cr_menu[0]
express_meal["name"]
# => "Express Meal with Chips"
```

Keeping track of deep structure like this is hard! It's often helpful to use the
Python repl to navigate step by step towards your target, building up the
accessors as you go. Then, you can consolidate into one line of code if you
want.

> **Questions**
> * How would you access the price of the first item on the menu at the second
>   restaurant?
> * How would you access the rating of the second restaurant?
> * How would you loop through all the menu items at the first restaurant to
>   find the average price?
> * How would you loop through all the restaurants and find the average price of
>   all the items on the menu for that restaurant?

Note that some of these are quite tricky!

