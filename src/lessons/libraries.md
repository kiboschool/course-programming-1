# Libraries

> “If I have seen further it is by standing on the shoulders of Giants”
> _Isaac Newton, letter to Robert Hooke in 1675_

We might not be Isaac Newton, but the shoulders keep getting better and better.

Libraries are other people's code. They let us do tasks that we wouldn't be able to do otherwise -- at least, not without great effort.

For a small example: you've used `random.randint` throughout the course. How would you write a function that returns a random integer? The python standard library uses a pseudorandom number generation algorithm called the Mersenne Twister, in python and c. It's a few hundred lines of pretty complicated code, especially because the C code and Python code have to interact. (You can take a look here: [Python](https://github.com/python/cpython/blob/main/Lib/random.py) and [C code](https://github.com/python/cpython/blob/6f6a4e6cc5cd76af4a53ffbb62b686142646ac9a/Modules/_randommodule.c))

Thankfully, you don't have to read that code, and _definitely_ don't have to write that code. Someone else figured out a good way to generate random numbers, and now you can just use that, instead of having to figure it out yourself.

This week you'll learn more about the Python standard library, how to manage external libraries, and how to use some of the most common and powerful libraries (JSON, Requests, and Flask) to accomplish tasks.

## Learning Objectives

After these lessons, you'll be able to:

- Explain what a library is and the difference between the standard library and external libraries
- Install and manage external libraries for your projects
- Use the `json` module from the standard library to handle JSON data
- Fetch data from the web using the `requests` library
- Run a basic web server using the Flask library