# JSON

JSON is a syntax format that is usually used to exchange data. Sooner or later you will need to parse JSON files within your code especially when dealing with configuration files.

Python has a built in package called `json` that is used work with such files and data format.

A JSON file may look like
```
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
It sometimes can be useful to get a JSON file as an input to your program so you can tune some parameters. Examples of items that can be in a JSON configuration file:
 - Mode of operation
 - Configuration Numbers
 - Specific Metadata

### JSON to Python
How would we read and access a JSON object given to us as an input?
```
import json
# some JSON:
x =  '{ "name":"John", "age":30, "city":"New York"}'
# parse x:
y = json.loads(x)
# the result is a Python dictionary:
print(y["age"])
```

Output: `30`
You can notice from the example above that a JSON object was converted to a python dict. That way you can then apply what we have learn at dictionaries to work with JSON data.

### Python to JSON
You will sometimes need to create JSON objects as a result of an operation you perform in your program so that you can then exchange JSON data over the network.
Take a look at the following example that converts a python dict to a JSON object:
```
import json

# a Python object (dict):
x = {
  "name": "John",
  "age": 30,
  "city": "New York"
}

# convert into JSON:
y = json.dumps(x)

# the result is a JSON string:
print(y)
```
> **Try running the example by yourself**

### JSON Files
In case we have a JSON file, how would we then access it within python? The answer here is related to what we have already learnt at Files
Check the snippet below:
```
        with open(json_file_path, 'r') as f:
            data = json.loads(f.read())
        # Write your code here...
```

> **_JSON Module:_**  **For more information about JSON module and its functions, please check the docs: https://docs.python.org/3/library/json.html**


