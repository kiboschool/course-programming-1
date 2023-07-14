# Mutating Lists

Lists are **mutable.**

In programming, 'mutate' means ‘change’. _Mutable_ means we can change the lists.

We can:

- assign a new value to a list index
- add and remove items from a list
- change the order of items

## Assigning new values

We can change any element of a list by assigning at an index.

For example, to change the second item in the list above to the `"Nigeria"`, we can assign to index `1`, like this:

```python
# The old list
countries = ["Kenya", "Ghana", "Ethiopia", "Zimbabwe"]
# Change the second item
countries[1] = 'Nigeria'
# The new list
print(countries) # ['Kenya', 'Nigeria', 'Ethiopia', 'Zimbabwe']
```

## Adding an item to the end of a list

To add a new element to the end of the list, you use `.append()`

```python
countries.append("Cameroon")
print(countries) # ['Kenya', 'Nigeria', 'Ethiopia', 'Zimbabwe', 'Cameroon']
```

## Removing an item

To remove an item from a list, you use `pop()`. With no arguments, pop removes the last element.

```python
countries = ['Kenya', 'Nigeria', 'Ethiopia', 'Zimbabwe', 'Cameroon']
print(countries) # ['Kenya', 'Nigeria', 'Ethiopia', 'Zimbabwe', 'Cameroon']
countries.pop() # removes the last element, "Cameroon"
print(countries) # ['Kenya','Nigeria', 'Ethiopia', 'Zimbabwe']
```

Or, you can specify an index to remove, and `pop()` will remove the element at that index.

```python
print(countries) # ['Kenya','Nigeria', 'Ethiopia', 'Zimbabwe']
countries.pop(1) # Removes the element at index 1, "Nigeria"
print(countries) # ['Kenya', 'Ethiopia', 'Zimbabwe']
```

You can also remove an item by value, using `.remove()`. This will remove the first item in the list that matches the value you pass in.

```python
countries = ['Kenya', 'Ethiopia', 'Zimbabwe']
print(countries) # ['Kenya', 'Ethiopia', 'Zimbabwe']
countries.remove("Kenya")
print(countries) # ['Ethiopia', 'Zimbabwe']
```

## Check your understanding

Try this quiz to check how well you understand what list operations will do.

<div data-tf-widget="zKMVM3FL" data-tf-medium="snippet" style="width:100%;height:600px;"></div><script src="//embed.typeform.com/next/embed.js"></script>

## Practice

<aside>

👩🏿‍💻 Modify the code below to perform operations on a list.

</aside>

<iframe src="https://trinket.io/embed/python/0839b74c22" width="100%" height="400" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

<details><summary>Solution Code (try for 5 minutes before peeking)</summary>

```python
my_list = [10, 20, 30, 40, 50]
print(my_list)

# Assign the first list item the value 5
my_list[0] = 5
print(my_list)

# Assign the last list item the value 'dog'
my_list[4] = 'dog'
print(my_list)

# Remove the second item in the list
my_list.pop(1)
print(my_list)

# Add another item to the end of the list with value False
my_list.append(False)
print(my_list)

print("The number of items in the list is", len(my_list))
```

</details>
