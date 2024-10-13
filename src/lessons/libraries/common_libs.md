# Common Libraries

In this section, you'll be introduced to several common python libraries and 
what they can do.

## Libraries you've already seen

We won't cover them in depth here, but you've used modules before in some of
your projects:

- `random`
- `json`
- `math`
- `time`

## OS Module

We already touched this module in your lessons about files, so you may already know a bit about the `os` module. 

You have seen this module can interact with directories and files.

`os` is one of the most useful modules in the standard library. It provides methods to interact with the operating system. 

The Operating System controls resources on every computer. That includes things
like files, network access, hardware, and communication between processes.
Sometimes other libraries (like `json` or `requests`) will handle dealing with
the operating system for you, but if you need to deal directly with the
operating system, this is the module for you.

The `os` and `os.path` modules include many functions to interact with the file system, which is the most common way that you'll use the module right now.

Here's a sample of uses for the `os` module:

The folder where the Python script is running is known as the Current Directory. 
Whenever you use a relative name for a file, Python starts looking in the 
current working directory. 

Note that the cwd is not always the path where the Python script is located! You can
run a Python program from some other location, and that location will be the
cwd.

You can locate the cwd using `os.getcwd()`

```python
import os

# Get the current working directory
cwd = os.getcwd()

# Print the cwd
print("Current working directory:", cwd)
```

What if you want to change the cwd? For that, there is `os.chdir()`.

```python
import os
# Get the current working directory
def current_path():
    print(os.getcwd())

# Printing CWD before
current_path()

# Changing the CWD
os.chdir('../')

# Printing CWD after
current_path()
```

The example above changes the current working directory to the parent folder,
but you could change directory to any other folder by passing in the path.

### Further Reading: OS Module

Read more about the `os` library in the docs: https://docs.python.org/3/library/os.html

## Requests

The `requests` library makes it easy to get or send data over the internet.

It has functions that correspond to the basic HTTP verbs:

- GET: get or retrieve data from a specified resource.
- POST: alter data on a resource.
- DELETE: remove a resource.
- PUT: update a resource

request to make and parse the response object that we get in return.

```python
import requests
response = requests.get('https://api.github.com')
print(response.text)
```

You can use the `response` to see a lot of information about the results of the GET request.

### Request

The main part of the request is the method, and depends on what method you use, there is the body of the request.
For `Post` and `Put` requests for example, you need to pass a body with the request:
```
requests.post('https://httpbin.org/post', data={'key':'value'})
```

### Further Reading: Requests Library

For more information about Requests and its functions, check out its documentation: [https://requests.readthedocs.io/en/latest](https://requests.readthedocs.io/en/latest/)

## Base64

Base64 encoding is used to convert binary data into ASCII characters. Encoding 
prevents the data from getting corrupted when it is transferred or processed 
through a text-only system.

### Encoding

Encoding data has two basic steps:
- Convert string data into byte-like objects
- Encode using base64 module

```python
import base64

sample_string = "Welcome to Programming 1 at KIBO"
sample_string_bytes = sample_string.encode("ascii")

base64_bytes = base64.b64encode(sample_string_bytes)
base64_string = base64_bytes.decode("ascii")

print(f"Encoded string: {base64_string}")
```

Output:
```
Encoded string: V2VsY29tZSB0byBQcm9ncmFtbWluZyAxIGF0IEtJQk8=
```

### Decoding

Decoding is opposite of encoding. 

Take the output from the previous example and decode it back to its original form.

```python
import base64

base64_string ="V2VsY29tZSB0byBQcm9ncmFtbWluZyAxIGF0IEtJQk8="
base64_bytes = base64_string.encode("ascii")

sample_string_bytes = base64.b64decode(base64_bytes)
sample_string = sample_string_bytes.decode("ascii")

print(f"Decoded string: {sample_string}")
```
Output:
`Decoded string: Welcome to Programming 1 at KIBO`

### Further Reading: Base64

See the docs for Base64: [https://docs.python.org/3/library/base64.html](https://docs.python.org/3/library/base64.html)
