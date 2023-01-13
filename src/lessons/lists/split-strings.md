# Split strings

You've learned how to do some useful operations with strings, like concatenating and combining. There’s one more operation — splitting — that will help you work more powerfully with strings.

### Key ideas

- Using split() method to convert string into a list

## Video: Splitting strings

<aside>

Watch this video to learn how to use the `split()` function to turn a string
into a list of strings.

</aside>

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.youtube.com/embed/mPrVU1bMDeQ?rel=0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## String Split Example

As you saw in the video, the string `split` function divides a string into a
list of parts of that string, based on a separator.

```python
groceries = "rice,beans,oil,peppers,meat,greens"
groceries_list = groceries.split(",")
print(groceries_list) #=> ['rice', 'beans', 'oil', 'peppers', 'meat', 'greens']
```

## Exploration

Python has another string function to go the other direction: from a list of strings
to a single string, with a separator. 

Have you seen that function before? Can you find it by searching the web or the Python docs?
