# 7.1 Basic File Operations

Estimated Time: 45 Minutes

In this section, you will be introduced to basic file operations in python.

## Basic Operations 
You may encounter many use cases to integrate files within your program:
- Data that somebody shared with you using a file
- A Report that you need to create by the end of your program
- List of operations that you need to process and perform within your code 
and many more..

At this section, we will check how do we perform file basic operations in python. These are:
- Opening a file
- Closing a file
- Reading from a file and access file data in code
- Deleting a file 

> **_NOTE:_** There are different ways in python to perform these operations. You are highly recommended to check modules documentation for more information

## Opening a file
There are many python functions for open a file. We will visit some of them.

### Python Open Function
Python has a built-in function called open(). It is used to open a specific file and it then returns a file object called **Handler**, that you can then use to be attached to the opened function.
The first argument of the open function is the file name. In case the file exists within the working directory, you can specifcy the nameof the file.
Otherwise you may insert the full path for the needed file.

```python
f = open("test.txt")    # open file in current directory
f = open("C:/Python38/README.txt")  # specifying full path
```
At this snippet, `f` is our file handler and we will see later how do we perform file operations using handlers.
 
### File Modes
The `open` function has more than one argument. Apart from a file name, it has a **mode** and **encoding** arguments.

The `mode` argument specifies what we want to do with the file, read **`r`**, write **`w`**, or append **`a`**. We can also specify if we want to open the file in __text mode__ or __binary mode__.
The default mode for reading is the _text_ mode. This provides contents in the form of **strings**. On the other hand, a binary mode returns **bytes** and this is usually used when dealing with image or executable files. Image processing applications for example.

Check the table below for an overview of main file modes

|MODE |DESCRIPTION|
|-----|------------------------------|
|**r**    |Opens a file for reading. (default)                             |
|**w**  |Opens a file for writing. Creates a new file if it does not exist or truncates the file if it exists.         |
|**x**  |Opens a file for exclusive creation. If the file already exists, the operation fails.         |
|**a**  |Opens a file for appending at the end of the file without truncating it. Creates a new file if it does not exist.         |
|**t**  |Opens in text mode. (default)         |
|**b**  |Opens in binary mode.         |
|**+**  |Opens a file for updating (reading and writing)         |

Some examples using file modes:
```python
f = open("test.txt")      # equivalent to 'r' or 'rt'
f = open("test.txt",'w')  # write in text mode
f = open("img.bmp",'r+b') # read and write in binary mode
```

Additionally, open function has the option to use **encoding**.
The default encoding is platform dependent. In windows, it is **cp1252** but **utf-8** in Linux.

> **_NOTE:_**  You need to take care of encoding, especially when working across platforms. It is highly recommended to specify encoding when using text mode.

```python
f = open("test.txt", mode='r', encoding='utf-8')
```
## Closing File
After performing needed operations using a file, we should close it. Why is this important? Closing the file frees up resources attached to it.
This is usually done using `close()` method.

```python
f = open("test.txt", encoding = 'utf-8')
f.close()
```

The close operation can sometimes be not that safe to perform. If an exception happens within the code before we reach closing, our program may exit without closing.
How to avoid this? By using what we call a **try..finally** block

```python
try:
   f = open("test.txt", encoding = 'utf-8')
   # perform file operations here
finally:
   f.close()
```

This block makes sure that whenever an exception happens within try scope -> the flow is directed to the finally scope and the files is closed.

> **_NOTE:_**  Try..except..finally is the way we handle exceptions within a python program. We will talk about this in detail in Programming 2.

### With Function
The most recommended way to close a file is by using `with` statement. This ensures that the file is closed when we exit a `with` block. 
When using this approach, we do not need to use the `close` function to explicitly close the file.

```python
with open("test.txt", encoding = 'utf-8') as f:
   # perform file operations
```

Most of our examples will use the `with` approach from now on.

## Reading a File
There are several ways that we can use to read from files. When reading from a file, you need to open it using the reading mode `r`. At this section, we will check the following ways reading data from a file:
- Size
- Lines

### Read using size
You can using the `read(size)` method to read the size number of data. it the size is not specified, it reads and returns till the end of the file.
Imagine that we have the following `check.txt` file:
```
Welcome to the Programming 1 at Kibo
This is the first time we use files!
The file has three lines
```
Reading a file with size would look like:
```python
> f = open("check.txt",'r',encoding = 'utf-8')
> f.read(4) # read the first 4 data
'Welc'

> f.read(4) # read the next 4 data
'ome'

> f.read() # continue till the end
'to the Programming 1 at Kibo\nThis is the first time we use files!\nThe file has three lines'
```

### Read using lines
The most convenient way to read a file is by lines through a for loop.
```python
f = open("check.txt",'r',encoding = 'utf-8')
for line in f:
  print(f"One Line: {line}")
```

Output:
```
One Line: Welcome to the Programming 1 at Kibo

One Line: This is the first time we use files!

One Line: The file has three lines
```
To avoid blank lines when printing, change the print to be `print(f"One Line: {line}", end = '')`. The line in the file includes a `\n` itself, so changing the end argument would prevent from having blank lines.
Apart from that, the method `readline()` can be used to read individual lines with no loop:

```python
>>> f.readline()
'Welcome to the Programming 1 at Kibo\n'

>>> f.readline()
'This is the first time we use files!\n'

>>> f.readline()
'The file has three lines\n'

>>> f.readline()
```

Moreover, there is sometimes the need to get all lines of a file into a list. Python provides a method called `readlines()` to perform this:
```python
>>> f.readlines()
['Welcome to the Programming 1 at Kibo\n', 'This is the first time we use files!\n', 'The file has three lines\n']
```

## Writing to and Creating a File
When writing to file, we need to use one the following modes: `w` write, `a` append, or `x` exclusive creation mode.
When using the write mode, you need to know that it wil overwrite file contents if it exists. That means that all of the content will be erased.
Writing strings or sequence of bytes to a file is performed using the `write` function. The function returns the number of characters written.

The following example creates the file `test.txt` if it does not already exist. It the file is already there, it overwrites it.
```
with open("test.txt",'w',encoding = 'utf-8') as f:
   f.write("my first file\n")
   f.write("This file\n\n")
   f.write("contains three lines\n")

```
> **_NOTE:_**  Do not forget to explicitly specify new lines when using the write method. Otherwise, you will overwriting contents.

## Deleting a File
Deleting a file is simple, you can use the os module for this:
```
import os
os.remove("check.txt")
```

## File Methods 
You can always check Google for more information about file function. 

Check the following for a [documentation of main file methods](https://python-reference.readthedocs.io/en/latest/docs/file/) we talked about many of them in this section  
