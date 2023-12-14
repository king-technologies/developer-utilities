# Python

- pyenv global 3.9.0 - changes the global Python version on your computer
- pyenv local 3.9.0 - changes the Python version for the current folder and all the sub-folder
- pyenv shell 3.9.0 - changes the Python version for the current shell session

## Course

Python is a high-level programming language, with applications in numerous areas, including web programming, scripting, scientific computing, and artificial intelligence!

It is very popular and used by organizations such as Google, NASA, the CIA, and Disney.

- REPL - Read, Evaluate, Print, Loop

  > REPL is a simple, interactive computer programming environment that takes single user inputs, executes them, and returns the result to the user; a program written in a REPL environment is executed piecewise.
  > Q. How to use REPL?
  > A. python or py or python3
  >
  > > > print("Hello World")
  > > > Hello World
  > > > exit() or quit() or Ctrl+Z then Enter

- Variables
  A variable allows you to store a value by assigning it to a name, which can be used to refer to the value later in the program.
  For example, in game development, you would use a variable to store the points of the player.

```python
user = "James"
x = 7
print(x)

print(x + 3)
print(x)
```

- Input
  Let's assume we want to take the age of the user as input.
  We know that the input() function returns a string.

```python
age = int(input())
print(age)

print("His age is " + str(age))
```

- In-place operators

In-place operators allow you to write code like 'x = x + 3' more concisely, as 'x += 3'.
The same thing is possible with other operators such as -, \*, / and % as well.

```python
x = 2
print(x)

x += 3
print(x)
```

- Walrus operator
  Walrus operator := allows you to assign values to variables within an expression, including variables that do not exist yet.

```python
num = int(input())
print(num)

print(num:=int(input()))
```

- Booleans
  There are two Boolean values: True and False.
  They can be created by comparing values, for instance by using the equal operator ==.

```python
my_boolean = True
print(my_boolean)
True

print(2 == 3)
False

print("hello" == "hello")
True
```

- Reusing Code

  - Built-in Functions
    > Python has many built-in functions that you can use directly, or by importing a module (recommended way).
  - User-defined Functions
    > You can also create your own functions to perform certain actions.

- Function

```python
def greet(name):
    print("Hello, " + name + ". Good morning!")

greet("James")
```

- IF Statement

```python
if expression:
    Statement
```

- Lists
- A Lists is a collection which is ordered and changeable. Allows duplicate members.

empty_list = []

# print(empty_list)

things = ["strings", 1, 2.0, True, None, [1, 2, 3]]

# 2D, Multi-dimensional list

# print(things[1][0])

# print(things[5][0])

# str = "Hello World"

# print(str[0])

# print(str[1])

words = ["Hello", "Worle", "Rohit", "Jain"]
print(words)
words[1] = words[3]
print(words)

nums = [1, 2, 3]
print(nums + [4, 5, 6])
print(nums \* 3)

x = "hello" + " world"
print(x \* 3)

print("z" in x)

print(not "z" in x)

# List Function

# Append

words.append("5th Element")
words.append("5th Element")
words.append("5th Element")
words.append("5th Element")
print(len(words))

# insert

# .insert(index,element)

words.insert(1, "2nd Element")
print(words)

print(x.index("h"))

- Exceptions

  > Exceptions are errors that occur during execution of the program. They interrupt the program flow, which can be problematic if you don't handle them.

- Exception Handling
  > Exception handling is a way of dealing with errors in your programs without your programs crashing.
  > We use try-except blocks for this in Python.

```python
try:
    if(num2 == 0):
        raise ImportError("You cannot divide by zero")
    print(add(num1, num2))
except ZeroDivisionError:
    print("You cannot divide by zero")
except (ValueError, TypeError):
    print(l1[0])
    print("Something went wrong")
except:
    print("Something went wrong")
    raise
finally:
    # Close your data base connection
    print("I will always run")
# - ImportError
# - ModuleNotFoundError
# - IndexError
# - NameError
# - SyntaxError
# - TypeError
# - ValueError
# - ZeroDivisionError
```

- finally

  > finally is used to execute code no matter whether an exception occurs or not.

- raise

  > raise is used to raise an exception.

- Assertions
  > Assertions are used to check if a given logical expression is True or False. Program execution proceeds only if the expression is True and raises an AssertionError when it is False.

```python

try:
    print(1)

    assert 2 + 2 == 4

    print(2)

    assert 1 + 1 == 3

    print(3)
except AssertionError:
    print(4)
```

> None is a special constant in Python that represents the absence of a value or a null value. it is similar to null in other programming languages.

```python
None Example

x = 0
y = 5
print(y)
y = None
print(y)
z = False

print(x == y)
print(x == z)
print(y == z)
print(x == None)


def some_fun():
    print("Hello World")

print(some_fun())
```

> Dictionaries are used to store data values in key:value pairs. A dictionary is a collection which is ordered, changeable and does not allow duplicates.

```python

ages = {"Rohit": 20, "Ada": 21, "Guido": 65, "Linus": 47}

print(ages["Rohit"])
print(ages["Ada"])
print(ages["Guido"])
print(ages["Linus"])


x = "asfdasdfsaf"
x = 'asdfasdf'


primary = {
    "red": [255, 0, 0],
    "green": "asdfasdf",
    "blue": [0, 0, 255]
}

print(primary["red"])
print(primary["green"])
print(primary["blue"])
primary["yellow"] = [255, 255, 0]
print(primary)
print(primary.get("red"))

Two types of objects in python
1. Mutable (List, Dictionary)
2. Immutable (String, Integer, Float, Boolean, Tuple)

1. Mutable
> Can be changed after creation

2. Immutable
> Cannot be changed after creation


bad_dict = {
    "key1": "value1",
    "key2": "value2",
    "key3": "value3",
}

print(bad_dict.keys())
print(bad_dict.values())
print(bad_dict.items())


nums = {
    1: "one",
    2: "two",
    3: "three"
}

print(2 in nums)
print("three" in nums)
print(4 not in nums)

print(nums.get(4, "not found asdfasd asdf"))
```

> Tuples
> A tuple is a collection which is ordered and unchangeable. In Python tuples are written with round brackets.

```python
words = ("spam", "eggs", "sausages")
print(words[0])

list = ["spam", "eggs", "sausages"]
tuple = ("spam", "eggs", "sausages")
dict = {"spam": "eggs", "sausages": "spam"}

words = ("Hello", "World", "Rohit", "Jain")
print(len(words))
words[1] = "World"

words = ()
```

> List Slices
> List slices provide a more advanced way of retrieving values from a list. Basic list slicing involves indexing a list with two colon-separated integers. This returns a new list containing all the values in the old list between the indices.

```python

squares = [0,1,4,9,16,25,36,49,64,81]
print(squares[2:6])
print(squares[3:8])

squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(squares[2:6])
print(squares[3:8])
print(squares[0:1])
print(squares[:5])
print(squares[5:])
print(squares[0:10:2])
print(squares[::2])
print(squares[1:-5:2])


```

> List Comprehensions
> List comprehensions are a useful way of quickly creating lists whose contents obey a simple rule. For example, we can do the following:

```python
cubes = [i**3 for i in range(5)]
print(cubes)

cubes = [i ** 3 for i in range(10)]
print(cubes)


# What does this list comprehension do?
nums = [i*2 for i in range(10)]
print(nums)

# A. A list of even number between 0 to 18
# B. A list of even number between 0 to 10
# C. A list of all number between 0 to 10

evens = [2 * i for i in range(10)]
print(evens)
```

> String formatting
> Python uses C-style string formatting to create new, formatted strings. The "%" operator is used to format a set of variables enclosed in a "tuple" (a fixed size list), together with a format string, which contains normal text together with "argument specifiers", special symbols like "%s" and "%d".

```python
nums = [4, 5, 6]
msg = "Numbers: {0} {1} {2}".format(nums[0], nums[1], nums[2])


delim = ", "

print(delim.join(["spam", "eggs", "ham"]))

print("Hello Me".replace("Me", "World"))

print("This is a sentence.".startswith("T"))

print("This is a sentence.".endswith("a sentence."))

print("This is a sentence.".upper())
print("This is a sentence.".lower())
print("This is a sentence.".title())
print("This is a sentence.".capitalize())
print("This is a sentence.".swapcase())
print("This is a sentence.".casefold())
print("This is a sentence.".split("asdfasdf"))
```

> Built-in Methods/Function
> Python contains many useful built-in functions and methods to accomplish common tasks. join is a string method that takes a list of strings as an argument, and returns a string consisting of the list elements joined by a separator string.

```python
print(", ".join(["spam", "eggs", "ham"]))


# print(min(1, 2, 3, 4, 5, 6, 7, 8, 9))
# print(max(1, 2, 3, 4, 5, 6, 7, 8, 9))
# print(abs(-10))
# print(abs(10))
# print(abs(-10.5))
# print(sum([1, 2, 3, 4, 5, 6, 7, 8, 9]))

# All, any, enumerate

# print(all([True, False, True, True, True, True, True, True, True]))

# print(any([True, False, True, True, True, True, True, True, True]))

nums = [55, 44, 33, 22, 11]

# if all([i > 11 for i in nums]):
#     print("All larger than 5")

# if any([i % 2 == 0 for i in nums]):
#     print("At least one is even")

for i, v in enumerate(nums):
    print(i, v)


for i,v in enumerate("This is a sentence."):
    print(v)

```

> Function Programming

- It is a style of programming in which we try to bind everything in pure mathematical functions style. It is a declarative type of programming style. Its main focus is on “what to solve” in contrast to an imperative style where the main focus is “how to solve”.

- Pure Function

  > A pure function is a function where the return value is only determined by its input values, without observable side effects. This is how functions in math work: Math.cos(x) will, for the same value of x, always return the same result.

- Lambda Function / Lambdas
  > A lambda function is a small anonymous function. A lambda function can take any number of arguments, but can only have one expression.

> map, filter
> The map() function in Python takes in a function and a list as argument. The function is called with a lambda function and a list and a new list is returned which contains all the lambda modified items returned by that function for each item.

> The filter() function in Python takes in a function and a list as arguments. This offers an elegant way to filter out all the elements of a sequence “sequence”, for which the function returns True.

> Generators
> Generators are a type of iterable, like lists or tuples. Unlike lists, they don't allow indexing with arbitrary indices, but they can still be iterated through with for loops. They can be created using functions and the yield statement.

> Decorators
> Decorators provide a way to modify functions using other functions. This is ideal when you need to extend the functionality of functions that you don't want to modify.

> Recursion
> Recursion is a very important concept in functional programming. The fundamental part of recursion is self-reference - functions calling themselves. It is used to solve problems that can be broken up into easier sub-problems of the same type.

> Sets
> A set is a collection which is unordered and unindexed. In Python sets are written with curly brackets. Sets are unordered, so you cannot be sure in which order the items will appear. and also set is created by set() function.

> Union > The union operation on two sets produces a new set containing all the distinct elements from both the sets.

```python
print(num_set | {3, 4, 5, 6})
```

> Intersection > The intersection operation on two sets produces a new set containing only the common elements from both the sets.

```python
print(num_set & {3, 4, 5, 6})
```

> Difference > The difference operation on two sets produces a new set containing only the elements from the first set and none from the second set.

```python
print(num_set - {3, 4, 5, 6})
```

> Symmetric Difference > The symmetric difference operation on two sets produces a new set containing only the elements that are unique to each set.

```python
print(num_set ^ {3, 4, 5, 6})
```

<!-- Data Structures -->

<!-- Lists -->
<!-- Dictionaries -->
<!-- Typles -->
<!-- Sets -->

When to use a dictionary:

- When you need a logical association between a key:value pair.
- When you need fast lookup for your data, based on a custom key.
- When your data is being constantly modified. Remember, dictionaries are mutable.

When to use the other types:

- Use lists if you have a collection of data that does not need random access. Try to choose lists when you need a simple, iterable collection that is modified frequently.
- Use a set if you need uniqueness for the elements.
- Use tuples when your data cannot change.

> Itertools
> The module itertools is a standard library that contains several functions that are useful in functional programming. One type of function it produces is infinite iterators. The function count counts up infinitely from a value. The function cycle infinitely iterates through an iterable (for instance a list or string). The function repeat repeats an object, either infinitely or a specific number of times.

> OOP (Object Oriented Programming)

> Classes
> Classes are a fundamental part of modern programming languages. Python makes it easy to make a class and use it to create objects. Today you will learn the essentials of programming with classes: how to initialize them, write methods, store fields, and more.
> Imperative (Using Statememts, Loops, Function as subroutines)
> Functional ( Using Pure Functions, Recursion, Higher Order Functions)
> Object-Oriented (Using Classes, Objects, Methods)

> Inheritance
> Inhritance is a way of creating a new class for using details of an existing class without modifying it. The newly formed class is a derived class (or child class). Similarly, the existing class is a base class (or parent class).

> Magic Methods
> Magic methods in Python are the special methods that start and end with the double underscores. They are also called dunder methods. Magic methods are not meant to be invoked directly by you, but the invocation happens internally from the class on a certain action.

```python
__add__ for +
__sub__ for -
__mul__ for *
__truediv__ for /
__floordiv__ for //
__mod__ for %
__pow__ for **
__and__ for &
__xor__ for ^
__or__ for |
```

<!-- > Object Lifecycle
  - Creation
  - Manipulation
  - Destruction

__init__

__new__.

__del__

del statement -->

> Data Hiding
> A key part of OOP is Encapsulation, Which involves the packaging of lreated variables and function into a single easy-to-use object - an instance of a class. A related concept is data hiding, which states that implementation details of a class should be hidden, and a clean standard interface be presented for those who want to use the class. In other programming languages, this is usually done with private methods and attributes, which block external access to certain methods and attributes in a class.

> Class methods are methods (with the @classmethod decorator) that are not concerned with instances, but the class itself. They can be used, for example, as alternative constructors for creating objects.

```python

class Array20:
  def __init__(self, lst):
    self.lst = lst

  @classmethod
  # for validation the list always have 20 elements
  def from_input(cls):
    lst = []
    for _ in range(20):
      lst.append(int(input()))
    return cls(lst)


arr = Array20.from_input()
print(arr.lst)

```

```

> Static methods are methods (with the @staticmethod decorator) that do not take the instance of a class as their first argument. They can be called by using the full class name and don't require an instance of that class.

"Create a Python class with a class method that takes in a list of dictionaries, where each dictionary has 'name' and 'age' as keys. The class method should return the count of dictionaries where the age is greater than a specified value."

"Implement a Python class with a class method that takes in a list of tuples, where each tuple contains two integers. The class method should return the count of tuples where the sum of the integers is even."

"Design a Python class with a class method that takes in a list of strings as input. The class method should return the count of strings that contain a specific substring."

"Write a Python class with a static method that takes in a list of strings as input and returns the concatenation of all the strings."

"Create a Python class with a static method that takes in a list of tuples, where each tuple contains two integers. The static method should return a list of the sums of the integers in each tuple."

"Implement a Python class with a static method that takes in a dictionary as input, where the keys are strings and the values are integers. The static method should return the sum of all the values in the dictionary."



> Properties
> Properties provide a way of customizing access to instance attributes. They are created by putting the property decorator above a method, which means when the instance attribute with the same name as the method is accessed, the method will be called instead. One common use of a property is to make an attribute read-only.
```

> Regular expression

> Regular expressions are a powerful language for matching text patterns. This page gives a basic introduction to regular expressions themselves sufficient for our Python exercises and shows how regular expressions work in Python. The Python "re" module provides regular expression support.

1. Start by understanding the special characters used in regular expressions. such as . ^ $ \* + ? { } [ ] \ | ( )

^ - Matches the beginning of a line
$ - Matches the end of the line
. - Matches any character
\s - Matches whitespace
\S - Matches any non-whitespace character for example, \S\w\* matches any word without spaces.

- - Repeats a character zero or more times
    _? - Repeats a character zero or more times (non-greedy) for example, <._?> matches any characters inside angle brackets.

- - Repeats a character one or more times
    +? - Repeats a character one or more times (non-greedy)
    [aeiou] - Matches a single character in the listed set
    [^XYZ] - Matches a single character not in the listed set
    [a-z0-9] - The set of characters can include a range
    ( - Indicates where string extraction is to start
    ) - Indicates where string extraction is to end
    {m} - Matches the preceding character m times for example, \d{3} matches three digits.
    {m,n} - Matches the preceding character m to n times for example, \d{3,4} matches three or four digits.
    \d - Matches any decimal digit; equivalent to the set [0-9]
    \D - Matches any non-digit character; equivalent to the set [^0-9]
    \w - Matches any alphanumeric character; equivalent to the set [a-zA-Z0-9_]
    \W - Matches any non-alphanumeric character; equivalent to the set [^a-zA-Z0-9_]
    \b - Matches the empty string, but only at the start or end of a word
    \B - Matches the empty string, but not at the start or end of a word
    \\ - Matches a literal backslash
    | - Matches either the expression before or the expression after the operator
    (?i) - Ignores case
    (?m) - Makes begin/end line anchors match at beginning/end of any line respectively, instead of just the beginning/end of the whole string
    (?s) - Makes a period (dot) match any character, including a newline
    (?x) - Permits "insignificant" whitespace in the regular expression to make it more readable
    (?P<name>) - Matches whatever matched previously named group <name>
    (?P=name) - Matches whatever matched previously named group <name>
    (?#...) - A comment; ignored.
    (?=...) - Matches if ... matches next, but doesn't consume any of the string. This is called a lookahead assertion
    (?!...) - Matches if ... doesn't match next. This is a negative lookahead assertion
    (?<=...) - Matches if preceded by ... (must be fixed length). This is called a lookbehind assertion
    (?<!...) - Matches if not preceded by ... (must be fixed length). This is called a negative lookbehind assertion
    (?(id/name)yes-pattern|no-pattern) - Matches yes-pattern if the group with id/name matched, the (optional) no-pattern otherwise; matches the empty string if the group did not participate in the match at all. This is called a conditional expression

123
564
789
8974
"Ada" === "Ada",
'Ada' == '.d.',

> Regular Expression for Email Validation

```
import re
pattern = r"^[a-zA-Z0-9+_.-]+@[a-zA-Z0-9.-]+$"

email = input()

match = re.match(pattern, email)

if match:
    print("Valid Email")
else:
    print("Invalid Email")
```

1. How would you match a string that starts with "hello" and ends with "world"?
2. Create a regular expression that matches a valid email address.
3. How would you match a string that contains only alphanumeric characters?
4. Write a regular expression that matches a 10-digit phone number, allowing for an optional country code at the beginning.
5. How would you extract all the words from a sentence, ignoring punctuation and special characters?
6. Create a regular expression that matches strings containing both "cat" and "dog" in any order.
7. Write a regular expression that matches a string containing a sequence of three or more consecutive vowels (a, e, i, o, u) or consonants.
8. How would you extract all the URLs from a text file?
9. Create a regular expression that matches strings containing a repeating sequence of characters (e.g., "abab", "1212", "abcabc").
10. Write a regular expression that matches strings containing a specific number of consecutive repeating characters (e.g., "111", "22", "333").

> MetaCharacters
> Metacharacters are characters with a special meaning:

patterns = r"";
^ - Starts with
$ - Ends with
. - Any character
\s - Whitespace

> Chacter Classes
> Chacter classes provide a way to match only one of a specific set of charcaters.
> A Character class is craeted by putting the characters it matches inside square brackets.

pattern = r"[aeiou]"
pattern = r"[a-zA-Z]"
pattern = r"[G-P]" => G to P
pattern = r"[0-9]" => 0 to 9

> Not Character Classes

pattern = r"[^A-Z]" => Not A to Z

Some more metacharacters are _, +, ?, { and }. These specify numbers of repetitions. The metacharacter_ means "zero or more repetitions of the previous thing". It tries to match as many repetitions as possible. The "previous thing" can be a single character, a class, or a group of characters in parentheses.

> Groups ()
> A group can be created by surrounding part of a regular expression with parentheses. This means that a group can be given as an argument to metacharacters such as \* and ?.

pattern = r"egg(spam)\*"

| - Either or

> Special Sequences
> A special sequence is a \ followed by one of the characters in the list below, and has a special meaning:

\1 \17

pasdfasdf= r"asdfas"
pattern = r"(.+) \1"

x: string
x = "asdfads"

x = "adfas"
y = "asdfasdf"

a= 65 => in binary 01000001
b= 66 => in binary 01000010
c= 67 => in binary 01000011
d= 68 => in binary 01000100
f = 70 => in binary 01000110
s = 83 => in binary 01010011

x = ""

> The Zen of Python

> The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability Counts
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than right now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!

> Space complexity

> Space complexity is a measure of the amount of working storage an algorithm needs. It is one of the most important factors to consider when choosing an algorithm to use for a particular task.

> Home you measure Space complexity?
> Answer. By counting the number of memory cells an algorithm needs to use.

> Time complexity

> Time complexity is a measure of the amount of time an algorithm needs to run to completion. It is one of the most important factors to consider when choosing an algorithm to use for a particular task.

> PEP (Python Enhancement Proposal)
> PEP stands for Python Enhancement Proposal. A PEP is a design document providing information to the Python community, or describing a new feature for Python or its processes or environment. The PEP should provide a concise technical specification of the feature and a rationale for the feature.
> PEP 8 is a style guide that provides a set of rules for how to format Python code. It was written in 2001 by Guido van Rossum, Barry Warsaw, and Nick Coghlan. The PEP contains the guidelines for how to format your Python code. It discusses topics like how you should name variables, how you should use indentation in your code, how you should use whitespace, etc.

PEP 8 is a style guide on the subject of writing readable code. It contains a number of guidelines in reference to variable names, which are summarized here:

- modules should have short, all-lowercase names;
- class names should be in the CapWords style; RohitJain rohitjain rohitJain
- most variables and function names should be lowercase_with_underscores;
- constants (variables that never change value) should be CAPS_WITH_UNDERSCORES;
- names that would clash with Python keywords (such as 'class' or 'if') should have a trailing underscore.
- lines shouldn't be longer than 80 characters;
- 'from module import \*' should be avoided;
- there should only be one statement per line.

PEP 8 also recommends using spaces around operators and after commas to increase readability.

PEP 20: The Zen of Python
PEP 257: Docstring Conventions

> **main** > **name** is a built-in variable which evaluates to the name of the current module. Thus it can be used to check whether the current script is being run on its own or being imported somewhere else by combining it with if statement, as shown below.

> **main** is the name of the scope in which top-level code executes. A module’s **name** is set equal to '**main**' when read from standard input, a script, or from an interactive prompt.

> Tuple Unpacking
> Tuple unpacking allows you to assign each item in an iterable (often a tuple) to a variable.

> Function Arguments
> Python allows to have function with Varying number of arguments. Using \*args as a function parameter enables you to pass an arbitrary number of arguments to that function. The arguments are then accessible as the tuple args in the body of the function.

> Else More
> The else statement is most commonly used along with the if Statement. but it can also follow a for or while loop, which gived it a different meaning. With the for or while loop, the code within it is called if the loop finishes normally (when a break statement does not cause an exit from the loop).

> Major 3-rd Party Libraries
> The Python standart alone contains many built-in libraries and functions to support the language. However, Python also has a rich set of libraries that are not part of the standard distribution. They are maintained by third-party developers and can be easily installed using pip, the package manager for Python.
> Django: Django is a high-level Python Web framework that encourages rapid development and clean, pragmatic design.
> CherryPy: CherryPy is a pythonic, object-oriented HTTP framework.
> Flask: Flask is a lightweight WSGI (Web Server Gateway Interface) web application framework.
> BeautifulSoup: Beautiful Soup is a Python library for pulling data out of HTML and XML files.
> matplotlib: matplotlib is a Python 2D plotting library which produces publication quality figures in a variety of hardcopy formats and interactive environments across platforms.
> NumPy: NumPy is the fundamental package for scientific computing with Python.
> ScyPy: SciPy is a Python-based ecosystem of open-source software for mathematics, science, and engineering.
> Panda3d: Panda3D is a game engine, a framework for 3D rendering and game development for Python and C++ programs.
> Pygame: Pygame is a cross-platform set of Python modules designed for writing video games.

> API Development

> API stands for Application Programming Interface. An API is a software intermediary that allows two applications to talk to each other. In other words, an API is the messenger that delivers your request to the provider that you're requesting it from and then delivers the response back to you. In addition to accessing the data, APIs can be used to share the application's capabilities and features with other developers. For example, Google has an API for Gmail. This API allows developers to integrate Gmail with their own systems. APIs are also used by companies to expose their services and data to other developers, for example, Twitter has an API that allows you to post tweets (among other things) from your own application.
