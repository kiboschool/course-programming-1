# 7.2 Basic Directory Operations

Estimated Time: 40 Minutes

In this section, you will be introduced to basic directory operations in python.

## Files & Directories
When you start writing wider software solutions, you may need to perform several kinds of operations and save them to files. As the scope of your software widens, several kinds of files may be needed. For instance:
- __Service Log__:You develop a backend service that has a long log file. Other developers may need to check your log for success/failure confirmations.
- __Logging__: You have a directory that has a list of logs, and you need to maintain latest five.
- __Reporting__: You may need to perform some operations for a specific input and then generate a specific report for that. With each run, one or more files are generated. So your program needs to maintain a directory of various types of files.
 
## Directory Tree
Imagine the case that you are building a service that monitors the change in number of files within a directory. New files indicate that some sort of an api is being being used.
In that case, your client wants to check a list of files at the output directory at the beginning of each run.

Python offers many useful functions from the __OS__ module that supports this.
One way to do that is by using the `os.scandir()` method. Suppose that we have a directory at our workspace that has the following contents:
- file_1.txt
- file_2.txt
- file_1.csv
- file_1.log
- file_1.mp4
- folder_1

`os.scandir()` returns at iterator object that we can loop over to get all contents within our directory:
```
import os
entries = os.scandir('check_dir/')
print(entries)

with os.scandir('check_dir/') as entries:
    for entry in entries:
        print(entry.name)
```
Output:
```
<posix.ScandirIterator object at 0x7f2c4fc27ce0>

file_1.txt
file_2.txt
file_1.csv
file_1.log
file_1.mp4
folder_1
```

Some points regarding the previous example:
- With Scope: We are performing a file operation using the `with` syntax we learnt at our previous lesson. It is useful here as it frees up acquired resources automatically after the iterator has been exhausted.
- Scan Method: This method returns a `ScandirIterator` that points to files within a current directory. We need to loop it over to get exact file names.

> **_Context Manager:_**  With scope is related to a concept called "Context Manager". We will learn about this in this as well as later courses.

> **_Iterator:_**  An Iterator is an object type that has a countable number of values, and it can be iterated upon.

Another way to get the contents of a directory is by using `pathlib` module:
```
from pathlib import Path

entries = Path('check_dir/')
for entry in entries.iterdir():
    print(entry.name)

```

> **_TODO:_** check the function __is_file()__ and use it to list files within a mixed directory (directory may have both of files and directories)

## Making a Directory
Imagine now that case that your program needs to have a directory that stores output data (files, reports, or logs). How would you create a directory at Python?
There are several ways to create a directory, one of them is by using **os.mkdir** method:
```
import os

os.mkdir('my_directory/')
```

In case the directory exists, this method will raise a `FileExistsError`. 
Now if your program needs to create a directory tree, then this method would not be suitable. What should you do?
Python offers a similar method called `os.makedirs` where you can use it to build a tree of directories.
```
import os

os.makedirs('path/to/log')
```
This will create the following tree:
.
|
└── path/
    └── to/
        └── log/
        
> **_NOTE:_** for more information about mkdirs() method, please check the following: https://www.geeksforgeeks.org/python-os-makedirs-method/  
> **_NOTE:_** for more information about difference between mkdir() and mkdires(), please check the following: https://ofstack.com/python/41275/the-difference-between-python-os.-mkdir-of-and-os.-makedirs-of.html

## Deleting a Directory
Sooner or later, you may start thinking about a clean up function within your program. The aim of this function is to clean all messy files and directories that you may have created through the program.
How would you delete a directory in Python?

One way to do that is the **os.rmdir()** 
```
import os

trash_dir = 'my_documents/bad_dir'

try:
    os.rmdir(trash_dir)
except OSError as e:
    print(f'Error: {trash_dir} : {e.strerror}')
```
Notice that this method works for empty directories only. 

> **_TODO:_** check __shutil.rmtree()__ fir deleting non empty and whole directory trees.
>
## Modifying a Directory
