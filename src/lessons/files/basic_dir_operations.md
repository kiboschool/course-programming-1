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
One way to do that is by using the `os.scandir()` method. Suppose that we have a directory called `data` at our workspace that has the following contents:
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

Another way to get the contents of a directory is by using `os.listdir(input_dir)` module:
```
import os

for filename in os.listdir(input_dir):
    print(filename)
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

## Modifying a Directory
As we have mentioned at the beginning of the lesson, you will notice with time that designing software programs need to modify some directories and paths for various reasons like storing data or generating reports.
At some applications you may need to:
- Categorize files based on extension type.
- Process a series of images in a directory and create a new tree of directories based on the path.

At this section, we will target the problem of modifying directories including copying, moving, and renaming files.
As you may already know, python is rich with modules. One main module that we will take a closer look at here is called `shutil`.

### Copying Files & Directories
A simple copy operation from one path to another can be performed as follows:
```
import shutil

src = 'path/to/file.txt'
dst = 'path/to/dest_dir'
shutil.copy(src, dst)
``` 
`src` stands for the source location of the file, while `dst` is the destination where want to copy to. We have two options here. If the destination is a file, then the contents of that file are going to be replaced by the source file. 
On the other hand, if the destination is a directory, then the source file will be copied into that directory.

> **_NOTE:_** shutil.copy() copies file contents and permissions only. Other metadata like creation and modification time is not part of the copy.

What about copying the whole directory not just a file? __Shutil__ offers a method called `shutil.copytree`. A common case to use this is when you want to create a backup for your directory tree before you start developing.
An example to achieve this would be something like:
```
import shutil
shutil.copytree('data_1', 'data1_backup')
```

As we notice here, shutil.copytree() takes two arguments; source and destination. It copies the contents of the source to the new destination ('data1_backup' at our example). One note here is that the destination directory must not exist.

### Moving Files & Directories
When we need to move the whole file or the needed directory, we can perform that using `shutil.move(src, dst)`. Clearly, src is the file or directory to be moved and dst is the destination.
```
import shutil
shutil.move('data/', 'backup/')
```
`shutil.move()` will move __data__ directory into backup if backup exists. It not, __data__ will be renamed to backup.

### Renaming Files & Directories
Renaming a file or a directory is simple. OS module offers a method called __rename()__ that can be used for that aim.
`os.rename('file_1.csv', 'file_2.csv')` will change the name of the file. In case the destination is a directory, an OS error will pop up.

## Shutil Documentation
As we have experienced in this lesson, shutil module is useful when we are dealing with files and directories problems. You can refer to this documentation for info about this module:
`https://docs.python.org/3/library/shutil.html`

### File Metadata
A common case to process a directory is that you loop over the whole contents and decide what to do with each file/folder. We talked about about looping over the contents of a directory. At this section we will apply this and take a step further.
Let us learn how would we check file mtadata within a directory. We will use the same `data` directory contents we referred to at the beginning of this lesson.

Take a look at the following example:
```
import os

for filename in os.listdir(data):
    print(os.path.splitext(filename)[1])
```
We used the method `os.path.splitext` here to split the filename into two parts, the first one is the name of the file, while the second one is the file extension. 

> **_TODO:_** Modify the example to print files with .txt extension only.

Let us now modify the example to show more file metadata:
```
import os

for filename in os.listdir(data):
    print(os.path.splitext(filename)[1]) # File extension
    print(os.stat(f"{file_dir}/{filename}").st_size) # File Size 
    print(os.path.getmtime(path)) # File Creation Time
    
```
At this example, we added:
- File Size: we used the `os.stat()` function to get file statistics where we used them to get the size using `st_size`. Notice that this function needs the whole file path as an argument to work properly.
__os.stat__ has plenty os useful metadata that we can use, check: https://docs.python.org/3/library/stat.html
- File Creation Timestamp: Shows a timestamp related to when this file was created. For more context on how to use such functions, please refer to: https://pynative.com/python-file-creation-modification-datetime/

> **_NOTE:_** Project and Exercises will assist you to apply these functions into real world problems as well as searching for more functions to provide suitable solutions.