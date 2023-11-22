# 10 of the most common Python mistakes I see from scientist-programmers

There are many, many books and articles on writing better Python code. Please use those if you want to really desire to become a good programmer. Here, I am just focusing on some of the most basic things that I think are particularly relevant to the types of scientific programmers we get in the HackingMaterials group.

Note: I used this site: [_http://markup.su/highlighter/_](http://markup.su/highlighter/) to help write code blocks with coloring. For additional flair, you might also try using: [_http://instaco.de_](http://instaco.de)



1. **Prefer data structures that don’t require memorizing array indexes.** \
   \
   Don’t use a data structure (like a list/array) that requires one to remember that “index 8” is the species string and “index 1” is the coordination number. \
   \
   **Bad:** \
   `my_data = ["Fe2O3", 6, 5, 43, 4.1]` \
   `cell_volume = my_data[1] * my_data[2] * my_data[3]` \
   `is_insulator = my_data[4] > 3` \
   \
   **Better:** \
   `my_data = {"formula": "Fe2O3", "a": 6, "b": 5, "c": 43, "band_gap": 4.1}` \
   `cell_volume = my_data["a"] * my_data["b"] * my_data["c"]` \
   `is_insulator = my_data["band_gap"] > 3` \
   \
   Notice how much easier it is to follow the logic of the code in the second example?\
   You can also use a pandas DataFrame object if you have lots of data and don’t want to repeat the same column headers many times or a namedtuple if you just want something lightweight.\

2. **Document all classes and methods in a standard format**\
   \
   It is really important that all classes and methods are documented. Code is much more often read than written (a tenet of Guido van Rossum), so it needs to be readable and understandable. If you don’t know what format to use, try the below:\
   \
   [_http://bit.ly/2nAxlT0_ ](http://bit.ly/2nAxlT0)\
   \
   You should also pay attention to the format already being used by a particular package.\

3.  **Inside of classes/methods, write code that is readable without documentation whenever possible**\
    \
    This is usually achieved by writing descriptive variable names, function names, and good interfaces to functions. As a small example, why do this (requires documentation to tell user what my\_d represents):\
    \
    `my_d = {"Mg": 3, "Ag": 8, "Li":4} # dict of el. symbol to coord. number`

    `all_element_symbols = my_d.keys()`

    `all_coordination_numbers = my_d.values()`\
    \
    when you can do this (same clarity in first line, better clarity in last two lines, no documentation):\
    \
    `elsymbol_coordnum = {"Mg": 3, "Ag": 8, "Li":4}`

    `all_element_symbols = elsymbol_coordnum.keys()`

    `all_coordination_numbers = elsymbol_coordnum.values()`\
    \
    Of course, sometimes you will need to write documentation - but usually to explain why, rather than how. Here is the perfect article about that - it is short and sweet: \
    \
    [_http://bit.ly/2pgFQXs_ ](http://bit.ly/2pgFQXs)\
    \
    Read it!\

4. **Follow PEP formatting guidelines**\
   \
   Following proper code formatting helps clarify your code. There are a billion PEP rules and you don’t have to follow all of them. But at least get the basic ones correct. Like:&#x20;
   * functions/methods are named like this: my\_very\_first\_method()
   * classes are named by CamelCase like this: MyVeryFirstClass
   * python files are named like this: my\_very\_first\_file.py
   * python modules are named like this: my\_very\_first\_module \
     \
     If you use an IDE like PyCharm, it will detect, underline, and automatically fix most of the worst cases for you, so learn to use the feature. There are also tools like PyLint that you can use separately from IDEs (PyCharm basically has a nice wrapper around PyLint). \
     \
     Also, don’t use ugly code separator comments like “############################” or ASCII art - stay clean and professional.\

5. **Use standard file formats** \
   \
   Use JSON or YAML most of the time if you need a file format, e.g., for a settings file. XML is very heavyweight and quickly being outdated. Don’t invent your own strange conventions (like CIF or any other custom file format).\

6. **Wrap exe code in ‘if name == “main”:’** \
   \
   Python often runs your file even when you don’t intend it to, e.g. when loading a module or importing some component of your file. It is important that you don’t run code as a “side-effect” of this. Use the if **name** == “**main**” wrapper to prevent this.\

7. **Be aware of Python gotchas, in particular mutable default arguments**\
   \
   Do you see anything wrong with this? \
   \
   def append\_to(element, to=\[]): \
   &#x20;      to.append(element) \
   &#x20;      return to \
   \
   If you don’t see it, then you’re going to get hit with some strange and difficult to pinpoint bugs downstream in your code.\
   \
   This is a common Python gotcha (there is lots of discussion online about it) \
   [_http://bit.ly/2nijUdp_ ](http://bit.ly/2nijUdp)\
   [_http://bit.ly/1wfFNKa_](http://bit.ly/1wfFNKa)\

8. **Write unit tests** \
   \
   Scientific researchers often don’t write tests because (i) they don’t write large, complex code with many moving parts or many different authors, (ii) they are overconfident about their ability to write correct code, (iii) they feel this will slow them down. Professionals write unit tests because they know that the longer and more complex a codebase becomes, and the more users it has, the more likely that something is going to go wrong down the line and the greater the dividends that are paid from writing unit tests. Unit tests allow code to be automatically tested for bugs every single time anyone makes a commit (continuous integration) and has demonstrated its value many times over in the large production codes that we use and develop - even (and perhaps especially) for ones required to do complex tasks on a deadline.\

9. Throw exceptions rather than returning coded results \
   \
   One of the most common beginner mistakes is to think that their code should never throw Exceptions or Errors. Perhaps this is because in the beginner’s mindset, Exceptions are associated with bugs (e.g., they run a code with a bug and see an Exception, so Exceptions are bad). Another issue is that beginners never want their code to interrupt the operation of whomever is running it. So rather than throwing an Exception when their code is given bad inputs, they will return None, -1, or False, so that they don’t interrupt whomever is calling their code. \
   \
   This is bad. If the user gives bad or nonsensical input to a function, an exception needs to be raised and the program needs to stop immediately if the user is not explicitly catching the exception. For example, if you try to use the Python math library to compute the log of a negative number \[>> math.log(-1)], it doesn’t return None or some nonsense like False or -1. It throws an Error! As a user, the error is much more useful than any other course of option. Think of the alternatives for math.log(-1):
   1. If the function returned -1, you would have returned an incorrect result (extremely bad). For example if your function computed math.log(x) \* 3, and you gave a negative x, your function would return -3 - which looks perfectly reasonable but is completely wrong! This is the worst possible thing you can do.
   2. If you return None or False to avoid inconveniencing the user, you have just made two mistakes. First, the user doesn’t really know that their input was bad; perhaps it is simply the math.log() function has a bug leading to the strange output. The second and more important issue is that a user might want to run the math.log() function over an array of 1 million integers, and then do a lot of complex processing after that. If math.log() didn’t immediately throw an error when encountering a negative number in the 1 million integer array, then the code would keep proceeding with nonsensical results and the user might finish 5 or 6 additional processing steps downstream before the code finally chokes and dies because there are strange “Nones” or “Falses” where there should have been numbers.There are even more dangerous situations that can occur, like a second library to compute standard deviations that ignores None values in the array. Then the user has unwittingly taken the standard deviation of only a subset of the data and never even knows that there was a problem in the pipeline. At that point, it becomes extremely tedious to trace back the source of the error.\
      \
      Code should fail immediately when there is invalid input. In general, the further the “distance” from the actual place where the problem originated and the point of failure/exception in the program, the more difficult and maddening the debug task. You are doing users a favor by moving program failure right to the place of the problem.\

10. Prefer python lists to numpy for simple things \
    \
    Numpy is great, but it is often overused (leading to worse code). Numpy is great for algorithmic work, for very complex slicing of multidimensional arrays, and for a host of other things, but it is not as good for creating basic data structures. Here are some advantages that Python lists have:&#x20;
    1. Python lists have cleaner built-in functions and code. There are lot of tools for Python lists, like index slicing and iterations, or functions like sum() and all() that make them very powerful while still very clean. Numpy has even more useful functions and operations than that (e.g., a built-in mean()), and sometimes you might need numpy in order to leverage those features, but there is no need to transform to numpy arrays to (for example) take the sum of an array. Master regular Python lists first before reaching for numpy because you will have much cleaner code.&#x20;
    2. Python lists can be easily appended and modified without lots of “filler” like figuring out how long the array needs to be in advance and populating with zeros before modifying values. This again leads to much cleaner code and is much easier to write and to read.
    3. Python lists can be easily serialized and deserialized, e.g. to JSON format where they are native.\
       Despite the claim that numpy is fast, numpy lists, arrays, etc can actually take a lot of time to initialize - maybe 100X more than default Python. Of course, if you are then going to do heavy processing on that matrix, like diagonalizing a large matrix or doing large matrix multiplications, numpy will absolutely improve your overall performance, perhaps to a large degree. But for simply creating a data structure or taking the sum of a list, you will perform much worse with numpy while writing less readable code.
    4. Python lists are more universal; they don’t require dependencies and they are readable by many more programmers.\
       \
       Note that this doesn’t mean to stop using numpy. Numpy does lots of things that regular Python cannot and it is an extremely powerful and useful library. But for routine file parsing (where being able to append easily is important), data representation (where serialization is important), overall code clarity (always important), and even speed for routine tasks (usually important) the native Python lists often have the advantage.\
       \


