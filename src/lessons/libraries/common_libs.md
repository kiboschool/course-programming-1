# 9.2 Libraries

In this section, we will check some common python libs, and their basic functionality.

## OS Module
We already touched this module at previous lessons and you may know what is the main functionality for it by now. We have seen how to use this module to interact with directories and maybe files.
OS is one of the most useful modules that comes with the standard python utility. It provides methods to interact with the operating system. This module provides a portable way of using operating system-dependent functionality. The *os* and *os.path* modules include many functions to interact with the file system.

### Working Directory
The folder where the Python script is running is known as the Current Directory. This is not the path where the Python script is located. Usind OS we can locate the current working directory using `os.getcwd()`
```
# Python program to explain os.getcwd() method

# importing os module
import os

# Get the current working
# directory (CWD)
cwd = os.getcwd()

# Print the current working
# directory (CWD)
print("Current working directory:", cwd)
```

> **_NOTE:_**  **Whenever you call files by their direct names, python starts looking in the current working directory**

What about the case when we need to change the current working directory? For that, OS module has another method called `os.chdir()`.

```
# Python program to change the
# current working directory
import os
# Function to Get the current
# working directory
def current_path():
    print("Current working directory before")
    print(os.getcwd())
    print()


# Driver's code
# Printing CWD before
current_path()

# Changing the CWD
os.chdir('../')

# Printing CWD after
current_path()
```
The example above changes the current working directory to one parent folder in tree.

 > **_OS Module:_**  **For more information about OS module and its functions, please check the docs: https://www.geeksforgeeks.org/os-module-python-examples/**
## JSON Module
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

## Requests Module
Requests module implements main web methods that you need to communicate using HTTP protocol. You may have learnt about these main request types by now at the `Web Foundations` course.
Basic methods provided by this module are:
- GET: indicates that you’re trying to get or retrieve data from a specified resource.
- POST: indicates that you are trying to alter data on a resource.
- DELETE: remove a resource.
- PUT: change the state of resource or update it.

Each request that we make has a response. What usually happens is that we choose a suitable type of request to make and parse the response object that we get in return.
Example:
```
import requests
response = requests.get('https://api.github.com')
```
In this example, we have captured the return value of get(), which is an instance of `Response`, and stored it in a variable called response. You can now use response to see a lot of information about the results of your __GET__ request.

### Request
The main part of the request is the method, and depends on what method you use, there is the body of the request.
For `Post` and `Put` requests for example, you need to pass a body with the request:
```
requests.post('https://httpbin.org/post', data={'key':'value'})
```

### Response
Response is an object that you get in return. You can save this object within a variable and parse its contents.
#### Status Codes
One of the first pieces of information that we check in a response object is the status code. There are specific codes for specific cases. For example, `200` maans that the request was successful and `404` means the page was not found!
```
if response.status_code == 200:
    print('Success!')
elif response.status_code == 404:
    print('Not Found.')
```
There are many other status codes withing this module, it is highly recommended to check the documentation.

#### Payload
Another important part of the response object is the payload (content). While `.content` gives you access to the raw bytes of the response payload, you will often want to convert them into a string using a character encoding such as UTF-8. response will do that for you when you access .text:
```
response.text
'{"current_user_url":"https://api.github.com/user","current_user_authorizations_html_url":"https://github.com/settings/connections/applications{/client_id}","authorizations_url":"https://api.github.com/authorizations","code_search_url":"https://api.github.com/search/code?q={query}{&page,per_page,sort,order}","commit_search_url":"https://api.github.com/search/commits?q={query}{&page,per_page,sort,order}","emails_url":"https://api.github.com/user/emails","emojis_url":"https://api.github.com/emojis","events_url":"https://api.github.com/events","feeds_url":"https://api.github.com/feeds","followers_url":"https://api.github.com/user/followers","following_url":"https://api.github.com/user/following{/target}","gists_url":"https://api.github.com/gists{/gist_id}","hub_url":"https://api.github.com/hub","issue_search_url":"https://api.github.com/search/issues?q={query}{&page,per_page,sort,order}","issues_url":"https://api.github.com/issues","keys_url":"https://api.github.com/user/keys","notifications_url":"https://api.github.com/notifications","organization_repositories_url":"https://api.github.com/orgs/{org}/repos{?type,page,per_page,sort}","organization_url":"https://api.github.com/orgs/{org}","public_gists_url":"https://api.github.com/gists/public","rate_limit_url":"https://api.github.com/rate_limit","repository_url":"https://api.github.com/repos/{owner}/{repo}","repository_search_url":"https://api.github.com/search/repositories?q={query}{&page,per_page,sort,order}","current_user_repositories_url":"https://api.github.com/user/repos{?type,page,per_page,sort}","starred_url":"https://api.github.com/user/starred{/owner}{/repo}","starred_gists_url":"https://api.github.com/gists/starred","team_url":"https://api.github.com/teams","user_url":"https://api.github.com/users/{user}","user_organizations_url":"https://api.github.com/user/orgs","user_repositories_url":"https://api.github.com/users/{user}/repos{?type,page,per_page,sort}","user_search_url":"https://api.github.com/search/users?q={query}{&page,per_page,sort,order}"}'
```
> **_Requests Module:_**  **For more information about Requests module and its functions, please check the docs: https://requests.readthedocs.io/en/latest/**

## Encoding Module - Base64
The Base64 encoding is used to convert bytes that have binary or text data into ASCII characters. Encoding prevents the data from getting corrupted when it is transferred or processed through a text-only system.
Main methods to understand here are the encode and decode.

### Encoding
Encoding data has mainly teo steps:
- Convert string data into byte-like objects
- Encode using base64 module

```
import base64

sample_string = "Welcome to Programming 1 at KIBO"
sample_string_bytes = sample_string.encode("ascii")

base64_bytes = base64.b64encode(sample_string_bytes)
base64_string = base64_bytes.decode("ascii")

print(f"Encoded string: {base64_string}")
```

Output:
`Encoded string: V2VsY29tZSB0byBQcm9ncmFtbWluZyAxIGF0IEtJQk8=`

### Decoding
Decoding would be the opposite of the two steps wen mentioned earlier. Let us take the output from the previous example and try to decode it back to its original form.

```
import base64


base64_string ="V2VsY29tZSB0byBQcm9ncmFtbWluZyAxIGF0IEtJQk8="
base64_bytes = base64_string.encode("ascii")

sample_string_bytes = base64.b64decode(base64_bytes)
sample_string = sample_string_bytes.decode("ascii")

print(f"Decoded string: {sample_string}")
```
Output:
`Decoded string: Welcome to Programming 1 at KIBO`

> **_Base64:_**  **For more information about Base64 module and its functions, please check the docs: https://docs.python.org/3/library/base64.html**