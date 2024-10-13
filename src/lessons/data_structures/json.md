# JSON

JSON is a common format for data. It looks a lot like a Python dictionary, and
has support across lots of different languages and tools.

In this lesson is a brief primer on using JSON in Python.

## Quick Facts

- JSON stands for "JavaScript Object Notation", but as you can see, it's not
  just used in JavaScript
- JSON is commonly used on the Web, as the format for different applications
  to communicate
- JSON is also commonly used for configuration files for applications

## Handling JSON in Python

Python has a built in package called `json` to work with JSON-formatted data.

A JSON file looks a lot like a Python dictionary:

```json
{
  "class A": {
    "students": 35,
    "location": "campus x"
  },
  "class B": {
    "students": 33,
    "location": "campus y"
  }
}
```

## Converting from JSON to Python datatypes

When you access a JSON file, it's text - a string. But, that string represents
data that has more structure and meaning. It might have numbers, strings, lists,
and dictionaries within it.

In order to work with the data in Python, you need to _parse_ the JSON string
and convert it to Python datatypes.

Python's built-in `json` module makes it pretty easy:

```python
import json
# some JSON:
json_text =  '{ "name":"John", "age":30, "city":"New York"}'
# parse it using loads
parsed = json.loads(json_text)
# the result is a Python dictionary:
print(parsed) # { "name": "John", "age": 30, "city": "New York" }
print(parsed["age"]) # 30
```

The difference is a little bit subtle, because the string and the dictionary are
visually similar!

However, when you have converted a JSON-formatted string to a python dict, you
can access the values inside.

> What result would you get if you tried to access `json_text["age"]`?

## Python to JSON

You can also go the other way and turn a Python object into JSON:

```python
import json

# a Python object (dict):
student = {
  "name": "John",
  "age": 30,
  "city": "New York"
}

# convert into JSON:
json_text = json.dumps(student)

# the result is a JSON string:
print(json_text)
```

The type of `json_text` is a _string_. It's formatted as JSON, which other
programs might be able to use, like if you saved it as a config file, or sent it
over the network to another application.

## JSON Files

If you have JSON data in a file, you can load it like this example:

```python
import json
data_file = open("data.json", "r")
data = json.load(data_file)
data_file.close()
data # Parsed data from the file
```

Or, if you wanted to write to a file, there's a corresponding function:

```python
import json
data = { "name": "John" }
target_file = open("target.json", "w")
json.dump(data, target_file)
target_file.close()
```

<div style="position: relative; padding-bottom: 56.25%; height: 0;">
<iframe src="https://www.youtube.com/embed/-51jxlQaxyA" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

## Further Reading: JSON module

> For more information about the JSON module and the functions it provides, see the Python docs: https://docs.python.org/3/library/json.html
