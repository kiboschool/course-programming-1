# 7.1 Basic File Operations

Estimated Time: 40 Minutes

In this section, you will be introduced to basic file operations in python.

## Open a file
This section will discuss file opening functions.

### Python Open Function
Python has a build-in function called open(). It is used to open a specific file and it then returns a file object called **Handler**.
The first argument of the open function is the file name. If you specify the name directly, that means the file exists within the working directory, otherwise you may insert the full path for the needed file.

```
f = open("test.txt")    # open file in current directory
f = open("C:/Python38/README.txt")  # specifying full path
```
At this snippet, `f` is our file handler and we will see later how do we perform file operations using handlers.
 
### File Modes
Open function has more than one argument. Apart from a file name, it has a **mode** and **encoding** arguments.

In mode, we specify what we want to do with the file, read `r`, write `w`, or append `a`. We can also specify if we want to open the file in text mode or binary mode.
The default mode for reading is the _text_ mode. This provides contents in the form of **strings**. On the other hand, a binary mode returns **bytes** and this is usually used when dealing with image or executable files. Image processing applications for example.

Check the table below for an overview of main file modes

### With Function

## Reading a file

## Writing to and Creating a File

## Deleting a File