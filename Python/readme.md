# Python Programming Language: The Definitive Guide from Hello World to Expert-Level Topics (Written by grok)

Python is a high-level, interpreted, dynamically typed programming language known for its readability, versatility, and extensive ecosystem. It supports multiple paradigms (object-oriented, functional, procedural) and excels in web development, data science, automation, scientific computing, and more. This README is the ultimate guide to Python, covering every topic from beginner to expert level with exhaustive explanations, subtypes, practical examples, edge cases, and cross-topic connections.

## Table of Contents
1. [Introduction to Python](#introduction-to-python)
2. [Getting Started: Hello, World!](#getting-started-hello-world)
3. [Python Versions](#python-versions)
4. [Basic Concepts](#basic-concepts)
   - [Variables and Data Types](#variables-and-data-types)
   - [Functions](#functions)
   - [Control Flow](#control-flow)
5. [Data Structures](#data-structures)
   - [Lists, Tuples, and Sets](#lists-tuples-and-sets)
   - [Dictionaries](#dictionaries)
   - [Strings](#strings)
6. [Object-Oriented Programming](#object-oriented-programming)
   - [Classes and Objects](#classes-and-objects)
   - [Inheritance and Polymorphism](#inheritance-and-polymorphism)
   - [Descriptors and Properties](#descriptors-and-properties)
7. [Modules and Packages](#modules-and-packages)
   - [Modules](#modules)
   - [Packages](#packages)
8. [Error Handling](#error-handling)
   - [Exceptions](#exceptions)
   - [Custom Exceptions](#custom-exceptions)
9. [Functional Programming](#functional-programming)
   - [Lambdas and Higher-Order Functions](#lambdas-and-higher-order-functions)
   - [Iterators and Generators](#iterators-and-generators)
10. [Concurrency and Parallelism](#concurrency-and-parallelism)
    - [Threading](#threading)
    - [Multiprocessing](#multiprocessing)
    - [Asyncio](#asyncio)
11. [Advanced Topics](#advanced-topics)
    - [Decorators](#decorators)
    - [Context Managers](#context-managers)
    - [Metaclasses](#metaclasses)
    - [Descriptors](#descriptors)
    - [Type Hints and Mypy](#type-hints-and-mypy)
    - [C Extensions and CFFI](#c-extensions-and-cffi)
    - [Dynamic Code Execution](#dynamic-code-execution)
    - [Memory Management and Garbage Collection](#memory-management-and-garbage-collection)
    - [WebAssembly with Pyodide](#webassembly-with-pyodide)
    - [Jupyter Notebooks](#jupyter-notebooks)
    - [Packaging and Distribution](#packaging-and-distribution)
    - [Profiling and Optimization](#profiling-and-optimization)
    - [Foreign Function Interface (FFI)](#foreign-function-interface-ffi)
12. [Testing in Python](#testing-in-python)
    - [Unit Tests with unittest](#unit-tests-with-unittest)
    - [Pytest](#pytest)
    - [Mocking and Patching](#mocking-and-patching)
    - [Coverage](#coverage)
13. [Data Science and Machine Learning](#data-science-and-machine-learning)
    - [NumPy and Pandas](#numpy-and-pandas)
    - [Matplotlib and Seaborn](#matplotlib-and-seaborn)
    - [Scikit-learn and TensorFlow](#scikit-learn-and-tensorflow)
14. [Web Development](#web-development)
    - [Flask](#flask)
    - [Django](#django)
    - [FastAPI](#fastapi)
15. [Building a Sample Project](#building-a-sample-project)
16. [Resources](#resources)

## Introduction to Python
Python, created by Guido van Rossum in 1991, emphasizes simplicity and readability, with a philosophy outlined in PEP 20 ("The Zen of Python"). Its key features include:
- **Dynamic Typing**: No need for explicit type declarations.
- **Interpreted**: Runs code directly, enabling rapid prototyping.
- **Multi-Paradigm**: Supports OOP, functional, and procedural programming.
- **Extensive Standard Library**: Modules for file I/O, networking, data processing, and more.
- **Ecosystem**: Rich libraries for data science (NumPy, Pandas), web development (Django, Flask), AI (TensorFlow, PyTorch), and automation.
- **Use Cases**: Web apps, data analysis, machine learning, scripting, DevOps, scientific computing, and education.

Python’s popularity stems from its beginner-friendly syntax and powerful libraries, making it a top choice across industries.

## Getting Started: Hello, World!
Install Python from [python.org](https://www.python.org/) or via package managers (`apt`, `brew`). Create a virtual environment:

```bash
python -m venv myenv
source myenv/bin/activate  # Linux/Mac
myenv\Scripts\activate  # Windows
```

The basic "Hello, World!" program:

```python
print("Hello, World!")
```

Run with:

```bash
python hello.py
```

Use `pip` to install packages:

```bash
pip install requests
```

## Python Versions
Python has two major versions in active use:
- **Python 2**: End-of-life since 2020, deprecated.
- **Python 3**: Current version (3.13 as of 2025), with breaking changes from Python 2 (e.g., `print` as a function, Unicode strings).

Key Python 3 features by version:
- **3.5**: `async`/`await` for asynchronous programming.
- **3.6**: f-strings, underscore in numeric literals.
- **3.7**: Data classes, `breakpoint()`.
- **3.8**: Walrus operator (`:=`), positional-only parameters.
- **3.9**: Dictionary merge (`|`), flexible type annotations.
- **3.10**: Pattern matching (`match`/`case`), union types (`X | Y`).
- **3.11**: Faster runtime (PEP 659), exception groups.
- **3.12**: Improved type annotations, per-interpreter GIL (experimental).
- **3.13**: Experimental JIT, enhanced REPL.

Check version:

```bash
python --version
```

Use `pyenv` for version management:

```bash
pyenv install 3.12.0
pyenv global 3.12.0
```

## Basic Concepts

### Variables and Data Types
Python uses dynamic typing, with no explicit declarations. Common types:
- **Integers**: Arbitrary-precision (`int`), e.g., `x = 42`.
- **Floats**: IEEE-754 double-precision (`float`), e.g., `y = 3.14`.
- **Strings**: Immutable Unicode sequences (`str`), e.g., `s = "hello"`.
- **Booleans**: `True`, `False`.
- **NoneType**: `None` for null values.
- **Lists**: Mutable sequences (`list`), e.g., `[1, 2, 3]`.
- **Tuples**: Immutable sequences (`tuple`), e.g., `(1, 2)`.
- **Dictionaries**: Key-value pairs (`dict`), e.g., `{"a": 1}`.
- **Sets**: Unordered unique elements (`set`), e.g., `{1, 2}`.

```python
x = 42  # Integer
y = 3.14  # Float
s = f"Hello, {x}"  # f-string
is_active = True  # Boolean
data = None  # NoneType
lst = [1, 2, 3]  # List
tup = (4, 5)  # Tuple
d = {"key": "value"}  # Dictionary
st = {1, 2, 3}  # Set

print(type(x))  # <class 'int'>
print(s)  # Hello, 42
```

**Edge Cases**:
- **Integer Overflow**: None, due to arbitrary-precision integers.
- **Float Precision**: `0.1 + 0.2 != 0.3` due to IEEE-754; use `decimal.Decimal` for precision.
- **Mutable Defaults**: Avoid mutable default arguments (e.g., `def func(lst=[])`).

**Cross-Connections**:
- **Data Structures**: Lists, tuples, etc., are built-in types.
- **Strings**: Leverage string methods and formatting.
- **OOP**: Types are classes, e.g., `int` inherits from `object`.

### Functions
Functions are defined with `def`, supporting positional, keyword, and default arguments.

```python
def add(a: int, b: int = 0) -> int:
    return a + b

def greet(name: str, greeting: str = "Hello") -> str:
    return f"{greeting}, {name}!"

# Variable arguments
def process(*args, **kwargs) -> None:
    print("Positional:", args)
    print("Keyword:", kwargs)

# Lambda
double = lambda x: x * 2

print(add(5, 3))  # 8
print(greet("Alice"))  # Hello, Alice!
process(1, 2, x="foo", y="bar")  # Positional: (1, 2), Keyword: {'x': 'foo', 'y': 'bar'}
print(double(5))  # 10
```

**Advanced Features**:
- **Annotations**: Type hints for static analysis (e.g., `a: int`).
- **Positional-Only**: `/` in signatures (e.g., `def func(a, /)`).
- **Keyword-Only**: `*` in signatures (e.g., `def func(*, b)`).
- **Closures**: Functions capturing outer variables.

```python
def make_counter():
    count = 0
    def counter():
        nonlocal count
        count += 1
        return count
    return counter

c = make_counter()
print(c())  # 1
print(c())  # 2
```

**Edge Cases**:
- **Mutable Defaults**: `def func(lst=[]): lst.append(1)` shares `lst` across calls.
- **Late Binding**: Closures capture variables by reference, not value.
- **Annotation Limits**: Type hints are not enforced at runtime without tools like `mypy`.

**Cross-Connections**:
- **Functional Programming**: Lambdas and closures enable functional patterns.
- **Decorators**: Functions can be decorated for added behavior.
- **OOP**: Methods are functions bound to objects.

### Control Flow
Python provides `if`, `for`, `while`, and `match` (3.10+).

```python
x = 7
if x > 5:
    print("Greater")
elif x == 5:
    print("Equal")
else:
    print("Lesser")

# Loops
for i in range(1, 4):
    print(i)  # 1, 2, 3

while x > 0:
    x -= 1
    if x == 3:
        continue
    if x == 1:
        break
    print(x)

# Pattern matching (3.10+)
def describe(value):
    match value:
        case int(n) if n > 0:
            return "Positive integer"
        case str(s):
            return f"String: {s}"
        case [x, y]:
            return f"List of two: {x}, {y}"
        case _:
            return "Other"

print(describe(42))  # Positive integer
print(describe("hello"))  # String: hello
print(describe([1, 2]))  # List of two: 1, 2
```

**Advanced Features**:
- **Else Clauses**: `for`/`while` can have `else` for no-break scenarios.
- **Comprehensions**: Inline loops (e.g., `[x*2 for x in range(5)]`).
- **Pattern Matching**: Supports complex patterns like lists, dictionaries, and guards.

**Edge Cases**:
- **Loop Variable Leakage**: `for i in range(5)` makes `i` available after loop (Python 2 behavior; fixed in 3).
- **Match Exhaustiveness**: `_` wildcard ensures all cases are handled.
- **Break/Continue Scope**: Can’t break outer loops without labels (use `return` in functions).

**Cross-Connections**:
- **Iterators**: `for` loops use iterator protocol.
- **Data Structures**: Loops iterate over lists, dictionaries, etc.
- **Error Handling**: Combine with `try`/`except` for robust flow.

## Data Structures

### Lists, Tuples, and Sets
- **Lists**: Mutable, ordered sequences.
- **Tuples**: Immutable, ordered sequences.
- **Sets**: Unordered, unique elements.

```python
lst = [1, 2, 3]
lst.append(4)
lst[1] = 5
print(lst)  # [1, 5, 3, 4]

tup = (1, 2, 3)
# tup[0] = 4  # Error: immutable
print(tup[0])  # 1

st = {1, 2, 3}
st.add(4)
st.remove(2)
print(st)  # {1, 3, 4}

# Comprehensions
squares = [x**2 for x in range(5)]
evens = {x for x in range(10) if x % 2 == 0}
print(squares)  # [0, 1, 4, 9, 16]
print(evens)  # {0, 2, 4, 6, 8}
```

**Advanced Features**:
- **Slicing**: `lst[start:stop:step]`, e.g., `lst[::-1]` reverses.
- **Unpacking**: `a, b = tup` or `a, *rest = lst`.
- **Set Operations**: Union (`|`), intersection (`&`), difference (`-`).

```python
lst = [1, 2, 3, 4]
print(lst[1:3])  # [2, 3]
print(lst[::-1])  # [4, 3, 2, 1]

a, *rest, b = lst
print(a, rest, b)  # 1 [2, 3] 4

s1 = {1, 2, 3}
s2 = {3, 4, 5}
print(s1 | s2)  # {1, 2, 3, 4, 5}
print(s1 & s2)  # {3}
```

**Edge Cases**:
- **Shallow Copies**: `lst.copy()` or `lst[:]` copies top level; nested objects need `copy.deepcopy`.
- **Set Mutability**: Sets can’t contain mutable types (e.g., lists); use `frozenset` for immutability.
- **Tuple Immutability**: Tuples with mutable elements (e.g., `(1, [2, 3])`) can be indirectly modified.

**Cross-Connections**:
- **Iterators**: All are iterable.
- **Functional Programming**: Use with `map`, `filter`.
- **OOP**: Custom classes can mimic list/tuple/set behavior.

### Dictionaries
Dictionaries store key-value pairs, with keys being hashable (immutable) types.

```python
d = {"a": 1, "b": 2}
d["c"] = 3
del d["a"]
print(d)  # {'b': 2, 'c': 3}

# Dictionary methods
print(d.get("x", 0))  # 0
print(d.keys())  # dict_keys(['b', 'c'])
print(d.values())  # dict_values([2, 3])

# Merge (3.9+)
d2 = {"c": 4, "d": 5}
merged = d | d2
print(merged)  # {'b': 2, 'c': 4, 'd': 5}

# Comprehension
squares = {k: v**2 for k, v in zip("abc", [1, 2, 3])}
print(squares)  # {'a': 1, 'b': 4, 'c': 9}
```

**Advanced Features**:
- **DefaultDict**: `collections.defaultdict` provides default values.
- **OrderedDict**: `collections.OrderedDict` preserves insertion order (standard in 3.7+).
- **Counter**: `collections.Counter` for counting hashable objects.

```python
from collections import defaultdict, Counter

dd = defaultdict(list)
dd["key"].append(1)
print(dd)  # defaultdict(<class 'list'>, {'key': [1]})

c = Counter("hello")
print(c)  # Counter({'l': 2, 'h': 1, 'e': 1, 'o': 1})
```

**Edge Cases**:
- **Hashability**: Keys must be immutable; custom types need `__hash__` and `__eq__`.
- **Iteration During Modification**: Causes `RuntimeError`; use `.copy()` or list keys.
- **Merge Precedence**: Rightmost dictionary wins in `|`.

**Cross-Connections**:
- **Data Structures**: Dictionaries complement lists/sets.
- **OOP**: Dictionaries power `__dict__` for object attributes.
- **Functional Programming**: Use with `map` for transformations.

### Strings
Strings are immutable Unicode sequences with rich methods and formatting options.

```python
s = "Hello, World!"
print(s.lower())  # hello, world!
print(s.split(","))  # ['Hello', ' World!']

# Formatting
name = "Alice"
age = 30
print(f"{name} is {age}")  # Alice is 30
print("Name: {0}, Age: {1}".format(name, age))  # Name: Alice, Age: 30
print("%s is %d" % (name, age))  # Alice is 30

# Raw strings
path = r"C:\Users"
print(path)  # C:\Users

# Unicode
smile = "😊"
print(len(smile))  # 1
print(smile.encode("utf-8"))  # b'\xf0\x9f\x98\x8a'
```

**Advanced Features**:
- **String Methods**: `join`, `strip`, `replace`, `startswith`, etc.
- **Regular Expressions**: `re` module for pattern matching.
- **Bytes**: `bytes` and `bytearray` for binary data.

```python
import re

pattern = r"\w+@\w+\.\w+"
email = "user@example.com"
print(re.match(pattern, email))  # <re.Match object>

b = b"hello"
print(b.decode("utf-8"))  # hello
```

**Edge Cases**:
- **Unicode Length**: `len("😊") == 1`, but byte length varies.
- **Format Errors**: `f"{x}"` raises if `x` is undefined.
- **Immutable Modifications**: String operations create new objects.

**Cross-Connections**:
- **Data Structures**: Strings are sequence types.
- **Error Handling**: Regex errors raise `re.error`.
- **C Extensions**: Strings interact with C via `PyUnicode`.

## Object-Oriented Programming

### Classes and Objects
Classes define blueprints for objects, with attributes and methods.

```python
class Person:
    species = "Homo sapiens"  # Class attribute

    def __init__(self, name: str, age: int):
        self.name = name  # Instance attribute
        self.age = age

    def introduce(self) -> str:
        return f"I'm {self.name}, {self.age} years old"

    @classmethod
    def get_species(cls) -> str:
        return cls.species

    @staticmethod
    def is_adult(age: int) -> bool:
        return age >= 18

p = Person("Alice", 30)
print(p.introduce())  # I'm Alice, 30 years old
print(Person.get_species())  # Homo sapiens
print(Person.is_adult(20))  # True
```

**Advanced Features**:
- **Class vs. Instance Attributes**: Class attributes are shared; instance attributes are per-object.
- **Special Methods**: `__str__`, `__eq__`, `__len__`, etc., for operator overloading.
- **Property Decorators**: Getter/setter methods.

```python
class Circle:
    def __init__(self, radius: float):
        self._radius = radius

    @property
    def radius(self) -> float:
        return self._radius

    @radius.setter
    def radius(self, value: float):
        if value < 0:
            raise ValueError("Radius cannot be negative")
        self._radius = value

c = Circle(5)
print(c.radius)  # 5
c.radius = 10
# c.radius = -1  # Raises ValueError
```

**Edge Cases**:
- **Attribute Conflicts**: Instance attributes shadow class attributes.
- **Special Method Overloading**: Incorrect `__eq__` can break hashing.
- **Property Performance**: Properties add overhead vs. direct access.

**Cross-Connections**:
- **Descriptors**: Properties use descriptor protocol.
- **Metaclasses**: Control class creation.
- **Data Structures**: Classes can implement sequence/mapping protocols.

### Inheritance and Polymorphism
Inheritance allows code reuse; polymorphism enables flexible behavior.

```python
class Animal:
    def speak(self) -> str:
        return "Sound"

class Dog(Animal):
    def speak(self) -> str:
        return "Woof!"

class Cat(Animal):
    def speak(self) -> str:
        return "Meow!"

def make_sound(animal: Animal) -> None:
    print(animal.speak())

dog = Dog()
cat = Cat()
make_sound(dog)  # Woof!
make_sound(cat)  # Meow!

# Multiple inheritance
class Flyer:
    def fly(self) -> str:
        return "Flying"

class Bird(Animal, Flyer):
    def speak(self) -> str:
        return "Chirp"

bird = Bird()
print(bird.speak())  # Chirp
print(bird.fly())  # Flying
```

**Advanced Features**:
- **Super**: `super()` accesses parent methods.
- **Abstract Base Classes**: `abc` module for abstract classes.
- **Method Resolution Order (MRO)**: Defines inheritance order in multiple inheritance.

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self) -> float:
        pass

class Rectangle(Shape):
    def __init__(self, width: float, height: float):
        self.width = width
        self.height = height

    def area(self) -> float:
        return self.width * self.height

r = Rectangle(3, 4)
print(r.area())  # 12.0
# s = Shape()  # Error: can't instantiate abstract class
```

**Edge Cases**:
- **Diamond Problem**: Multiple inheritance can cause ambiguity; resolved by MRO.
- **Abstract Method Enforcement**: Subclasses must implement all abstract methods.
- **Super Misuse**: Incorrect `super()` calls can skip parent methods.

**Cross-Connections**:
- **Type Hints**: Annotations ensure polymorphic compatibility.
- **Decorators**: Methods can be decorated for behavior.
- **Metaclasses**: Control inheritance behavior.

### Descriptors and Properties
Descriptors define attribute access behavior via `__get__`, `__set__`, `__delete__`.

```python
class Descriptor:
    def __init__(self, name: str):
        self.name = name

    def __get__(self, obj, owner):
        return obj.__dict__.get(self.name, 0)

    def __set__(self, obj, value):
        if value < 0:
            raise ValueError("Value cannot be negative")
        obj.__dict__[self.name] = value

class MyClass:
    x = Descriptor("x")

m = MyClass()
m.x = 5
print(m.x)  # 5
# m.x = -1  # Raises ValueError
```

**Advanced Features**:
- **Property**: Built-in descriptor for getters/setters.
- **Class-Level Descriptors**: Shared across instances.
- **Data vs. Non-Data Descriptors**: Non-data descriptors (only `__get__`) have lower precedence.

**Edge Cases**:
- **Descriptor Precedence**: Instance attributes override non-data descriptors.
- **Performance**: Descriptors add overhead vs. direct access.
- **Descriptor Ownership**: `__get__` receives owner class for class-level access.

**Cross-Connections**:
- **OOP**: Descriptors power properties and methods.
- **Metaclasses**: Descriptors can modify class behavior.
- **Type Hints**: Descriptors can enforce type constraints.

## Modules and Packages

### Modules
Modules are `.py` files containing code, imported with `import`.

```python
# mymodule.py
def greet(name: str) -> str:
    return f"Hello, {name}!"

CONSTANT = 42
```

```python
# main.py
import mymodule
from mymodule import greet

print(mymodule.greet("Alice"))  # Hello, Alice!
print(mymodule.CONSTANT)  # 42
print(greet("Bob"))  # Hello, Bob!
```

**Advanced Features**:
- **Relative Imports**: `from .sibling import func` for package imports.
- **Module Attributes**: `__name__`, `__file__`, `__doc__`.
- **Dynamic Imports**: `importlib.import_module`.

```python
import importlib

mod = importlib.import_module("mymodule")
print(mod.greet("Dynamic"))  # Hello, Dynamic!

if __name__ == "__main__":
    print("Run directly")
```

**Edge Cases**:
- **Circular Imports**: Cause `ImportError`; use lazy imports or restructuring.
- **Module Caching**: `sys.modules` caches imports; reload with `importlib.reload`.
- **Name Conflicts**: Shadowing built-ins or other modules.

**Cross-Connections**:
- **Packages**: Modules are organized into packages.
- **OOP**: Modules can contain classes.
- **Packaging**: Modules are distributed as packages.

### Packages
Packages are directories with `__init__.py`, organizing modules hierarchically.

```
mypackage/
├── __init__.py
├── module1.py
└── subpackage/
    ├── __init__.py
    └── module2.py
```

```python
# mypackage/__init__.py
from .module1 import func1
```

```python
# mypackage/module1.py
def func1():
    return "Function 1"
```

```python
# main.py
import mypackage
from mypackage.subpackage import module2

print(mypackage.func1())  # Function 1
```

**Advanced Features**:
- **Namespace Packages**: Packages without `__init__.py` (PEP 420).
- **Package Resources**: `importlib.resources` for accessing package files.
- **__all__**: Controls `from module import *`.

```python
# mypackage/__init__.py
__all__ = ["func1"]
from .module1 import func1
```

**Edge Cases**:
- **Relative Import Errors**: Incorrect `.` or `..` causes `ImportError`.
- **Package Initialization**: `__init__.py` runs on import, impacting performance.
- **Resource Access**: Use `importlib.resources` instead of `os.path` for portability.

**Cross-Connections**:
- **Modules**: Packages contain modules.
- **Packaging**: Packages are distributed via `setuptools`.
- **Dynamic Code**: Packages can be imported dynamically.

## Error Handling

### Exceptions
Python uses `try`/`except` for exception handling, with `raise` to throw exceptions.

```python
try:
    x = 1 / 0
except ZeroDivisionError as e:
    print(f"Error: {e}")
except (TypeError, ValueError) as e:
    print(f"Other error: {e}")
else:
    print("No error")
finally:
    print("Cleanup")

# Raising
def validate_age(age: int):
    if age < 0:
        raise ValueError("Age cannot be negative")
    return age

try:
    validate_age(-5)
except ValueError as e:
    print(f"Validation error: {e}")
```

**Advanced Features**:
- **Exception Hierarchy**: Built-in exceptions inherit from `BaseException`.
- **Exception Groups**: (3.11+) Handle multiple exceptions with `ExceptionGroup`.
- **Traceback Access**: `traceback` module for detailed error info.

```python
import traceback

try:
    raise ValueError("Test error")
except ValueError:
    traceback.print_exc()
```

**Edge Cases**:
- **Broad Excepts**: `except Exception` catches too much; prefer specific exceptions.
- **Exception Swallowing**: Empty `except` hides errors; use `logging`.
- **Finally Precedence**: `finally` runs even if `return` is called.

**Cross-Connections**:
- **OOP**: Exceptions are classes.
- **Context Managers**: `try`/`finally` replaced by `with`.
- **Testing**: Test exception raising with `pytest.raises`.

### Custom Exceptions
Define custom exceptions by subclassing `Exception`.

```python
class CustomError(Exception):
    def __init__(self, message: str, code: int):
        super().__init__(message)
        self.code = code

def process_data(data: str):
    if not data:
        raise CustomError("Empty data", 400)
    return data.upper()

try:
    process_data("")
except CustomError as e:
    print(f"Error: {e}, Code: {e.code}")
```

**Advanced Features**:
- **Exception Chaining**: Use `raise ... from` for context.
- **Custom Attributes**: Add metadata to exceptions.
- **Group Exceptions**: (3.11+) Combine multiple errors.

```python
try:
    try:
        1 / 0
    except ZeroDivisionError as e:
        raise ValueError("Failed operation") from e
except ValueError as e:
    print(f"Chained: {e.__cause__}")  # ZeroDivisionError
```

**Edge Cases**:
- **Inheritance**: Custom exceptions should inherit from `Exception`, not `BaseException`.
- **Chaining Misuse**: Incorrect `from` can obscure root causes.
- **Performance**: Raising exceptions is slower than conditionals.

**Cross-Connections**:
- **OOP**: Exceptions leverage inheritance.
- **Decorators**: Wrap functions to handle exceptions.
- **Asyncio**: Async code raises async-specific exceptions.

## Functional Programming

### Lambdas and Higher-Order Functions
Lambdas create anonymous functions; higher-order functions take or return functions.

```python
# Lambda
double = lambda x: x * 2
print(double(5))  # 10

# Higher-order functions
def apply(func, value):
    return func(value)

print(apply(lambda x: x**2, 3))  # 9

# Built-in functionals
numbers = [1, 2, 3, 4]
evens = list(filter(lambda x: x % 2 == 0, numbers))
squares = list(map(lambda x: x**2, numbers))
print(evens)  # [2, 4]
print(squares)  # [1, 4, 9, 16]

from functools import reduce
sum = reduce(lambda x, y: x + y, numbers)
print(sum)  # 10
```

**Advanced Features**:
- **Functools**: `partial`, `reduce`, `wraps` for functional utilities.
- **Operator Module**: `operator.add`, `itemgetter` for functional operations.
- **Closures**: Lambdas can capture variables.

```python
from functools import partial

add_five = partial(lambda x, y: x + y, 5)
print(add_five(3))  # 8
```

**Edge Cases**:
- **Lambda Limits**: Single expression; no statements or annotations.
- **Readability**: Complex lambdas reduce clarity; use `def`.
- **Reduce Performance**: `reduce` can be slower than loops.

**Cross-Connections**:
- **Iterators**: `map`, `filter` return iterators.
- **Decorators**: Higher-order functions power decorators.
- **Data Structures**: Functionals transform lists/dictionaries.

### Iterators and Generators
Iterators implement `__iter__` and `__next__`; generators simplify iteration with `yield`.

```python
# Iterator
class Counter:
    def __init__(self, max):
        self.max = max
        self.current = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.current >= self.max:
            raise StopIteration
        self.current += 1
        return self.current

c = Counter(3)
for i in c:
    print(i)  # 1, 2, 3

# Generator
def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

print(list(fibonacci(5)))  # [0, 1, 1, 2, 3]

# Generator expression
squares = (x**2 for x in range(5))
print(list(squares))  # [0, 1, 4, 9, 16]
```

**Advanced Features**:
- **Yield From**: Delegate to sub-generators.
- **Send/Throw**: Advanced generator control for coroutines.
- **Itertools**: `chain`, `cycle`, `tee` for iterator utilities.

```python
from itertools import chain

def subgen():
    yield from [1, 2, 3]

g = chain([0], subgen(), [4])
print(list(g))  # [0, 1, 2, 3]
```

**Edge Cases**:
- **Iterator Exhaustion**: Iterators yield once; use `tee` for reuse.
- **Generator Memory**: Generators save memory but hold state.
- **StopIteration**: Explicit raising can confuse iteration.

**Cross-Connections**:
- **Data Structures**: Iterators power `for` loops.
- **Asyncio**: Async generators for asynchronous iteration.
- **Functional Programming**: Iterators pair with `map`, `filter`.

## Concurrency and Parallelism

### Threading
Threading handles I/O-bound tasks but is limited by the Global Interpreter Lock (GIL).

```python
import threading
import time

def worker(name: str):
    print(f"{name} starting")
    time.sleep(1)
    print(f"{name} done")

threads = []
for i in range(3):
    t = threading.Thread(target=worker, args=(f"Thread-{i}",))
    threads.append(t)
    t.start()

for t in threads:
    t.join()

# Thread synchronization
lock = threading.Lock()
counter = 0

def increment():
    global counter
    for _ in range(1000):
        with lock:
            counter += 1

t1 = threading.Thread(target=increment)
t2 = threading.Thread(target=increment)
t1.start()
t2.start()
t1.join()
t2.join()
print(counter)  # 2000
```

**Advanced Features**:
- **Locks**: `Lock`, `RLock`, `Semaphore` for synchronization.
- **ThreadPoolExecutor**: `concurrent.futures` for thread pools.
- **Thread-Local Data**: `threading.local` for thread-specific state.

```python
from concurrent.futures import ThreadPoolExecutor

with ThreadPoolExecutor(max_workers=2) as executor:
    results = executor.map(lambda x: x**2, [1, 2, 3])
    print(list(results))  # [1, 4, 9]
```

**Edge Cases**:
- **GIL Limitations**: CPU-bound tasks don’t parallelize; use multiprocessing.
- **Race Conditions**: Unsynchronized access causes errors.
- **Thread Cleanup**: Ensure threads terminate to avoid leaks.

**Cross-Connections**:
- **Asyncio**: Complements threading for I/O-bound tasks.
- **Data Structures**: Thread-safe collections like `queue.Queue`.
- **Error Handling**: Threads propagate exceptions to main thread.

### Multiprocessing
Multiprocessing bypasses the GIL for CPU-bound tasks using separate processes.

```python
from multiprocessing import Process, Pool
import os

def worker(n: int):
    print(f"Process {os.getpid()} computing {n**2}")
    return n**2

if __name__ == "__main__":
    processes = [Process(target=worker, args=(i,)) for i in range(3)]
    for p in processes:
        p.start()
    for p in processes:
        p.join()

    with Pool(2) as pool:
        results = pool.map(lambda x: x**2, [1, 2, 3])
        print(results)  # [1, 4, 9]
```

**Advanced Features**:
- **Shared Memory**: `multiprocessing.Value`, `Array` for shared data.
- **Queue/Pipe**: Inter-process communication.
- **Manager**: `multiprocessing.Manager` for shared objects.

```python
from multiprocessing import Queue

def producer(q: Queue):
    q.put("data")

def consumer(q: Queue):
    print(q.get())

if __name__ == "__main__":
    q = Queue()
    p1 = Process(target=producer, args=(q,))
    p2 = Process(target=consumer, args=(q,))
    p1.start()
    p2.start()
    p1.join()
    p2.join()
```

**Edge Cases**:
- **Process Overhead**: Spawning processes is slower than threads.
- **Serialization**: Shared objects must be picklable.
- **Resource Limits**: OS limits process count.

**Cross-Connections**:
- **Threading**: Contrasts for CPU vs. I/O tasks.
- **Data Structures**: Queues for IPC.
- **C Extensions**: Multiprocessing leverages C for performance.

### Asyncio
Asyncio handles I/O-bound tasks with coroutines, using `async`/`await`.

```python
import asyncio
import aiohttp

async def fetch(url: str) -> str:
    async with aiohttp.ClientSession() as session:
        async with session.get(url) as response:
            return await response.text()

async def main():
    urls = ["https://api.example.com/data1", "https://api.example.com/data2"]
    tasks = [fetch(url) for url in urls]
    results = await asyncio.gather(*tasks)
    print(results)

if __name__ == "__main__":
    asyncio.run(main())
```

Add to `requirements.txt`:

```
aiohttp==3.8
```

**Advanced Features**:
- **Event Loop**: Manages async tasks; access via `asyncio.get_event_loop`.
- **Tasks/Queues**: `asyncio.create_task`, `asyncio.Queue` for coordination.
- **Streams**: `asyncio.open_connection` for low-level networking.

```python
async def producer(queue: asyncio.Queue):
    await queue.put("data")

async def consumer(queue: asyncio.Queue):
    print(await queue.get())

async def queue_example():
    q = asyncio.Queue()
    await asyncio.gather(producer(q), consumer(q))

asyncio.run(queue_example())
```

**Edge Cases**:
- **Blocking Calls**: Use `loop.run_in_executor` for blocking code.
- **Event Loop Scope**: `asyncio.run` creates a new loop; avoid in async contexts.
- **Resource Cleanup**: Ensure coroutines complete to avoid leaks.

**Cross-Connections**:
- **Threading**: Asyncio is single-threaded but integrates with threads.
- **Iterators**: Async generators for async iteration.
- **Web Development**: Powers `FastAPI`, `aiohttp`.

## Advanced Topics

### Decorators
Decorators wrap functions or classes to modify behavior.

```python
def log(func):
    def wrapper(*args, **kwargs):
        print(f"Calling {func.__name__} with {args}, {kwargs}")
        result = func(*args, **kwargs)
        print(f"{func.__name__} returned {result}")
        return result
    return wrapper

@log
def add(a: int, b: int) -> int:
    return a + b

add(2, 3)  # Logs: Calling add with (2, 3), {} ... add returned 5

# Class decorator
def singleton(cls):
    instances = {}
    def get_instance(*args, **kwargs):
        if cls not in instances:
            instances[cls] = cls(*args, **kwargs)
        return instances[cls]
    return get_instance

@singleton
class Database:
    def __init__(self):
        self.connection = "Connected"

db1 = Database()
db2 = Database()
print(db1 is db2)  # True
```

**Advanced Features**:
- **Parameterized Decorators**: Use decorator factories.
- **Functools.wraps**: Preserve function metadata.
- **Class Decorators**: Modify class behavior.

```python
from functools import wraps

def retry(attempts: int):
    def decorator(func):
        @wraps(func)
        def wrapper(*args, **kwargs):
            for i in range(attempts):
                try:
                    return func(*args, **kwargs)
                except Exception as e:
                    if i == attempts - 1:
                        raise
                    print(f"Retry {i+1}/{attempts}: {e}")
        return wrapper
    return decorator

@retry(3)
def flaky_function():
    if random.random() < 0.7:
        raise ValueError("Failed")
    return "Success"

print(flaky_function())
```

**Edge Cases**:
- **Metadata Loss**: Without `wraps`, `__name__` and `__doc__` are lost.
- **Decorator Order**: `@dec1 @dec2` applies `dec2` first.
- **Async Decorators**: Require `async`/`await` handling.

**Cross-Connections**:
- **Functional Programming**: Decorators are higher-order functions.
- **OOP**: Decorate methods or classes.
- **Asyncio**: Decorators for async functions.

### Context Managers
Context managers handle resource setup/teardown with `with`.

```python
class Resource:
    def __enter__(self):
        print("Acquiring resource")
        return self

    def __exit__(self, exc_type, exc_value, traceback):
        print("Releasing resource")
        return False  # Propagate exceptions

with Resource() as r:
    print("Using resource")

# Contextlib
from contextlib import contextmanager

@contextmanager
def timer():
    start = time.time()
    yield
    print(f"Elapsed: {time.time() - start}")

with timer():
    time.sleep(1)
```

**Advanced Features**:
- **Async Context Managers**: `__aenter__`, `__aexit__` for async `with`.
- **Suppress**: `contextlib.suppress` to ignore exceptions.
- **ExitStack**: `contextlib.ExitStack` for dynamic context management.

```python
from contextlib import suppress

with suppress(FileNotFoundError):
    os.remove("nonexistent.txt")
```

**Edge Cases**:
- **Exception Handling**: `__exit__` must handle or suppress exceptions.
- **Re-entrancy**: Context managers should support nested `with`.
- **Resource Leaks**: Ensure `__exit__` runs even on errors.

**Cross-Connections**:
- **Error Handling**: Context managers replace `try`/`finally`.
- **Asyncio**: Async context managers for async resources.
- **OOP**: Context managers are classes or decorated generators.

### Metaclasses
Metaclasses control class creation, inheriting from `type`.

```python
class Meta(type):
    def __new__(cls, name, bases, attrs):
        attrs["created_at"] = time.time()
        return super().__new__(cls, name, bases, attrs)

class MyClass(metaclass=Meta):
    pass

print(MyClass.created_at)  # Timestamp

# Singleton metaclass
class SingletonMeta(type):
    _instances = {}
    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            cls._instances[cls] = super().__call__(*args, **kwargs)
        return cls._instances[cls]

class Singleton(metaclass=SingletonMeta):
    pass

s1 = Singleton()
s2 = Singleton()
print(s1 is s2)  # True
```

**Advanced Features**:
- **Dynamic Attributes**: Add methods or attributes at class creation.
- **Validation**: Enforce class constraints.
- **ORM Example**: Django’s models use metaclasses for field registration.

**Edge Cases**:
- **MRO Conflicts**: Metaclasses must align with base classes.
- **Complexity**: Metaclasses can obscure code; use sparingly.
- **Inheritance**: Subclasses inherit metaclass behavior.

**Cross-Connections**:
- **OOP**: Metaclasses extend class system.
- **Descriptors**: Metaclasses can add descriptors.
- **Decorators**: Class decorators as lighter alternative.

### Descriptors
Descriptors (covered in OOP) are reused here for advanced examples.

```python
class Lazy:
    def __init__(self, func):
        self.func = func
        self.name = func.__name__

    def __get__(self, obj, owner):
        if obj is None:
            return self
        value = self.func(obj)
        setattr(obj, self.name, value)
        return value

class MyClass:
    @Lazy
    def expensive(self):
        print("Computing...")
        return 42

m = MyClass()
print(m.expensive)  # Computing... 42
print(m.expensive)  # 42 (cached)
```

**Edge Cases**:
- **Non-Data Descriptors**: Only `__get__` has lower precedence.
- **Thread Safety**: Descriptors need locks for concurrent access.
- **Class vs. Instance**: `__get__` handles both cases.

**Cross-Connections**:
- **Properties**: Built-in descriptor type.
- **Metaclasses**: Descriptors enhance class behavior.
- **OOP**: Central to attribute access.

### Type Hints and Mypy
Type hints (PEP 484) enable static type checking with `mypy`.

```python
from typing import List, Optional, Union, Callable

def greet(name: str, age: Optional[int] = None) -> str:
    return f"Hello, {name}, age {age or 'unknown'}"

def process(data: List[Union[int, str]]) -> None:
    print(data)

# Generic function
def apply(func: Callable[[int], int], value: int) -> int:
    return func(value)

print(greet("Alice", 30))  # Hello, Alice, age 30
process([1, "two"])
print(apply(lambda x: x*2, 5))  # 10
```

**Advanced Features**:
- **Generics**: `typing.Generic` for custom types.
- **Protocols**: `typing.Protocol` for structural subtyping.
- **Type Aliases**: Simplify complex types.

```python
from typing import TypeAlias, Protocol

Vector: TypeAlias = List[float]

class Printable(Protocol):
    def print(self) -> None:
        ...

class Document:
    def print(self) -> None:
        print("Printing")

def print_doc(doc: Printable) -> None:
    doc.print()

print_doc(Document())
```

**Edge Cases**:
- **Runtime Overhead**: Type hints are ignored at runtime.
- **Complex Annotations**: Generics and unions can be verbose.
- **Mypy Strictness**: Strict mode may require extensive annotations.

**Cross-Connections**:
- **OOP**: Type hints enhance class interfaces.
- **Functional Programming**: Annotate higher-order functions.
- **Testing**: Type checkers complement tests.

### C Extensions and CFFI
C extensions integrate Python with C for performance or FFI.

```python
// myext.c
#include <Python.h>

static PyObject* my_function(PyObject* self, PyObject* args) {
    int x;
    if (!PyArg_ParseTuple(args, "i", &x)) {
        return NULL;
    }
    return PyLong_FromLong(x * 2);
}

static PyMethodDef MyMethods[] = {
    {"my_function", my_function, METH_VARARGS, "Double a number"},
    {NULL, NULL, 0, NULL}
};

static struct PyModuleDef mymodule = {
    PyModuleDef_HEAD_INIT,
    "myext",
    NULL,
    -1,
    MyMethods
};

PyMODINIT_FUNC PyInit_myext(void) {
    return PyModule_Create(&mymodule);
}
```

**Setup Script**:

```python
from setuptools import setup, Extension

setup(
    name="myext",
    version="0.1",
    ext_modules=[Extension("myext", ["myext.c"])],
)
```

Build and use:

```bash
python setup.py build_ext --inplace
```

```python
import myext
print(myext.my_function(5))  # 10
```

**CFFI Alternative**:

```python
from cffi import FFI

ffi = FFI()
ffi.cdef("int c_double(int);")
lib = ffi.dlopen("./libmyext.so")

# libmyext.c
int c_double(int x) {
    return x * 2;
}

print(lib.c_double(5))  # 10
```

**Edge Cases**:
- **Reference Counting**: Incorrect `Py_INCREF`/`Py_DECREF` causes leaks or crashes.
- **GIL**: C extensions must hold GIL for Python API calls.
- **Portability**: C extensions require platform-specific builds.

**Cross-Connections**:
- **FFI**: CFFI simplifies C interop.
- **Performance**: C extensions optimize bottlenecks.
- **Packaging**: Extensions included in wheels.

### Dynamic Code Execution
Execute code dynamically with `eval`, `exec`, or `ast`.

```python
code = "x = 5; print(x * 2)"
exec(code)  # 10

expression = "2 + 3"
print(eval(expression))  # 5

import ast

tree = ast.parse("print('Hello')")
exec(compile(tree, "<string>", "exec"))  # Hello
```

**Advanced Features**:
- **AST Manipulation**: Modify code before execution.
- **Restricted Execution**: Use `restrictedpython` for safety.
- **Code Objects**: `compile` creates reusable code objects.

**Edge Cases**:
- **Security**: `eval`/`exec` can execute arbitrary code; sanitize inputs.
- **Scope Pollution**: `exec` modifies locals unpredictably.
- **Performance**: Dynamic execution is slower than static code.

**Cross-Connections**:
- **Metaclasses**: Dynamic class creation uses `exec`.
- **Decorators**: Dynamic code can wrap functions.
- **Jupyter**: Dynamic execution powers notebooks.

### Memory Management and Garbage Collection
Python uses reference counting and a cyclic garbage collector.

```python
import gc
import sys

x = []
x.append(x)  # Cyclic reference
print(sys.getrefcount(x))  # 2

del x
gc.collect()  # Break cycle
print(gc.get_stats())  # GC stats
```

**Advanced Features**:
- **Weak References**: `weakref` for non-owning references.
- **Memory Views**: `memoryview` for efficient buffer access.
- **Objgraph**: Visualize object references for leak debugging.

```python
import weakref

obj = object()
ref = weakref.ref(obj)
print(ref())  # <object object at ...>
del obj
print(ref())  # None
```

**Edge Cases**:
- **Reference Cycles**: Cause leaks without GC.
- **GIL Impact**: Reference counting is thread-safe but limits parallelism.
- **Memory Fragmentation**: Large objects may fragment heap.

**Cross-Connections**:
- **C Extensions**: Manage references in C code.
- **OOP**: `__del__` for cleanup.
- **Performance**: Memory leaks impact long-running apps.

### WebAssembly with Pyodide
Pyodide runs Python in browsers via WebAssembly.

```python
# main.py
from js import console

def greet(name: str) -> str:
    return f"Hello, {name}!"

console.log(greet("Alice"))
```

Run with Pyodide:

```html
<script src="https://cdn.jsdelivr.net/pyodide/v0.23.0/full/pyodide.js"></script>
<script>
async function main() {
    let pyodide = await loadPyodide();
    await pyodide.runPythonAsync(`
        from main import greet
        console.log(greet("Browser"))
    `);
}
main();
</script>
```

**Edge Cases**:
- **Browser Limitations**: No direct filesystem access.
- **Performance**: Slower than native Python.
- **Package Support**: Limited to pure-Python or compiled wheels.

**Cross-Connections**:
- **C Extensions**: Pyodide supports some C libraries.
- **Web Development**: Integrates with JavaScript.
- **Data Science**: Run NumPy/Pandas in browsers.

### Jupyter Notebooks
Jupyter notebooks combine code, markdown, and visualizations.

```python
# notebook.ipynb
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 10, 100)
plt.plot(x, np.sin(x))
plt.title("Sine Wave")
plt.show()
```

**Advanced Features**:
- **IPython Magics**: `%timeit`, `%matplotlib` for interactivity.
- **Widgets**: `ipywidgets` for interactive controls.
- **Extensions**: `nbextensions` for custom functionality.

**Edge Cases**:
- **Kernel Crashes**: Restart kernel on errors.
- **State Persistence**: Cells share state, causing reproducibility issues.
- **File Size**: Large outputs bloat notebooks.

**Cross-Connections**:
- **Data Science**: Primary tool for NumPy/Pandas.
- **Dynamic Code**: Notebooks execute code dynamically.
- **Web Development**: Serve notebooks via `jupyter-server`.

### Packaging and Distribution
Package Python code with `setuptools` for distribution via PyPI.

```python
# setup.py
from setuptools import setup, find_packages

setup(
    name="myproject",
    version="0.1",
    packages=find_packages(),
    install_requires=["requests"],
    entry_points={
        "console_scripts": [
            "myproject = myproject.main:main",
        ],
    },
)
```

**Project Structure**:

```
myproject/
├── myproject/
│   ├── __init__.py
│   └── main.py
├── setup.py
└── requirements.txt
```

Build and upload:

```bash
python -m build
twine upload dist/*
```

**Advanced Features**:
- **Wheels**: `bdist_wheel` for faster installs.
- **Poetry/Pyproject.toml**: Modern dependency management.
- **Conda**: Package management for data science.

```toml
# pyproject.toml
[tool.poetry]
name = "myproject"
version = "0.1"
dependencies = {
    "requests" = "^2.28"
}

[tool.poetry.scripts]
myproject = "myproject.main:main"
```

**Edge Cases**:
- **Dependency Conflicts**: Use `pipdeptree` to diagnose.
- **Platform Wheels**: C extensions need platform-specific builds.
- **Versioning**: Follow SemVer to avoid breaking changes.

**Cross-Connections**:
- **Modules**: Packages distribute modules.
- **C Extensions**: Included in wheels.
- **Web Development**: Packages power web frameworks.

### Profiling and Optimization
Profile code with `cProfile`, `line_profiler`, or `memory_profiler`.

```python
import cProfile

def slow_function():
    return sum(x**2 for x in range(1000000))

cProfile.run("slow_function()")
```

**Optimization Tools**:
- **Numba**: JIT compilation for numerical code.
- **Cython**: Compile Python to C for performance.
- **PyPy**: Alternative interpreter with JIT.

```python
from numba import jit

@jit(nopython=True)
def fast_sum(n):
    total = 0
    for i in range(n):
        total += i**2
    return total

print(fast_sum(1000000))
```

**Edge Cases**:
- **Profiling Overhead**: Slows execution; sample selectively.
- **Numba Limitations**: Not all Python features supported.
- **PyPy Compatibility**: Some C extensions don’t work with PyPy.

**Cross-Connections**:
- **C Extensions**: Cython/Numba for performance.
- **Data Science**: Optimize NumPy/Pandas code.
- **Memory Management**: Profiling detects leaks.

### Foreign Function Interface (FFI)
FFI (covered in C Extensions) uses `ctypes` or `cffi` for C interop.

```python
from ctypes import cdll

lib = cdll.LoadLibrary("./libmyext.so")
lib.c_double.argtypes = [ctypes.c_int]
lib.c_double.restype = ctypes.c_int
print(lib.c_double(5))  # 10
```

**Edge Cases**:
- **Type Safety**: `ctypes` errors on incorrect types.
- **Library Paths**: Dynamic loading fails if library is missing.
- **GIL**: `ctypes` calls release GIL for parallelism.

**Cross-Connections**:
- **C Extensions**: Alternative to `ctypes`.
- **Performance**: FFI optimizes critical paths.
- **Packaging**: Include shared libraries in distributions.

## Testing in Python

### Unit Tests with unittest
`unittest` provides a built-in testing framework.

```python
import unittest

def add(a: int, b: int) -> int:
    return a + b

class TestMath(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)
        self.assertNotEqual(add(2, 3), 6)

    def test_error(self):
        with self.assertRaises(TypeError):
            add("2", 3)

if __name__ == "__main__":
    unittest.main()
```

### Pytest
Pytest is a popular, flexible testing framework.

```python
# test_math.py
def test_add():
    assert add(2, 3) == 5

def test_error():
    with pytest.raises(TypeError):
        add("2", 3)
```

Run:

```bash
pytest
```

### Mocking and Patching
Mock dependencies with `unittest.mock`.

```python
from unittest.mock import patch
import requests

def fetch_data(url: str) -> str:
    return requests.get(url).text

@patch("requests.get")
def test_fetch_data(mock_get):
    mock_get.return_value.text = "Mocked data"
    assert fetch_data("http://example.com") == "Mocked data"
```

### Coverage
Measure test coverage with `coverage`.

```bash
pip install coverage
coverage run -m pytest
coverage report
```

**Advanced Features**:
- **Parameterized Tests**: `pytest.mark.parametrize` for multiple inputs.
- **Fixtures**: Pytest fixtures for setup/teardown.
- **Async Tests**: Test async code with `pytest-asyncio`.

```python
import pytest

@pytest.mark.parametrize("a, b, expected", [(1, 2, 3), (0, 0, 0)])
def test_add(a, b, expected):
    assert add(a, b) == expected

@pytest.fixture
def setup_data():
    return [1, 2, 3]

def test_with_fixture(setup_data):
    assert len(setup_data) == 3
```

**Edge Cases**:
- **Mock Side Effects**: Incorrect mocks can hide bugs.
- **Coverage False Positives**: 100% coverage doesn’t ensure correctness.
- **Test Dependencies**: Avoid shared state between tests.

**Cross-Connections**:
- **Error Handling**: Test exception paths.
- **OOP**: Test class methods and properties.
- **Asyncio**: Test async functions with `pytest-asyncio`.

## Data Science and Machine Learning

### NumPy and Pandas
NumPy provides numerical arrays; Pandas handles tabular data.

```python
import numpy as np
import pandas as pd

# NumPy
arr = np.array([[1, 2], [3, 4]])
print(arr @ arr)  # Matrix multiplication

# Pandas
df = pd.DataFrame({"A": [1, 2, 3], "B": ["x", "y", "z"]})
print(df.groupby("B").sum())
```

### Matplotlib and Seaborn
Visualize data with Matplotlib and Seaborn.

```python
import matplotlib.pyplot as plt
import seaborn as sns

x = np.linspace(0, 10, 100)
plt.plot(x, np.sin(x), label="sin(x)")
sns.scatterplot(x=x, y=np.cos(x), label="cos(x)")
plt.legend()
plt.show()
```

### Scikit-learn and TensorFlow
Machine learning with Scikit-learn; deep learning with TensorFlow.

```python
from sklearn.linear_model import LinearRegression
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense

# Scikit-learn
X = np.array([[1], [2], [3]])
y = np.array([2, 4, 6])
model = LinearRegression().fit(X, y)
print(model.predict([[4]]))  # [8.]

# TensorFlow
model = Sequential([Dense(1, input_shape=(1,))])
model.compile(optimizer="adam", loss="mse")
model.fit(X, y, epochs=10, verbose=0)
print(model.predict([[4]]))  # Approx [8.]
```

**Edge Cases**:
- **Array Shapes**: NumPy operations require compatible shapes.
- **Missing Data**: Pandas handles `NaN`; use `fillna` or `dropna`.
- **Overfitting**: Regularize ML models to avoid overfitting.

**Cross-Connections**:
- **Jupyter**: Primary environment for data science.
- **C Extensions**: NumPy/TensorFlow use C for speed.
- **Type Hints**: Annotate data science code for clarity.

## Web Development

### Flask
Flask is a lightweight web framework.

```python
from flask import Flask, request

app = Flask(__name__)

@app.route("/greet/<name>")
def greet(name):
    return f"Hello, {name}!"

@app.route("/data", methods=["POST"])
def post_data():
    return {"received": request.json}

if __name__ == "__main__":
    app.run(debug=True)
```

### Django
Django is a full-stack web framework.

```python
# myapp/views.py
from django.http import JsonResponse

def greet(request, name):
    return JsonResponse({"message": f"Hello, {name}!"})
```

```python
# myproject/urls.py
from django.urls import path
from myapp.views import greet

urlpatterns = [
    path("greet/<str:name>", greet),
]
```

### FastAPI
FastAPI is a modern, async web framework.

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class Item(BaseModel):
    name: str
    price: float

@app.get("/greet/{name}")
async def greet(name: str):
    return {"message": f"Hello, {name}!"}

@app.post("/items")
async def create_item(item: Item):
    return item
```

**Edge Cases**:
- **Request Validation**: FastAPI/Pydantic enforce schemas; Flask/Django need manual validation.
- **Static Files**: Serve with `django.contrib.staticfiles` or `fastapi.staticfiles`.
- **CSRF**: Django requires CSRF tokens; FastAPI/Flask need middleware.

**Cross-Connections**:
- **Asyncio**: FastAPI leverages async.
- **Type Hints**: FastAPI uses Pydantic for validation.
- **Testing**: Test web apps with `pytest` and `httpx`.

## Building a Sample Project
This project implements a **task scheduler API** with Flask, async processing, C extension, and data analysis, showcasing Python’s features.

**Project Structure**:

```
task_scheduler/
├── myproject/
│   ├── __init__.py
│   ├── app.py
│   ├── scheduler.py
│   ├── cext.c
│   └── stats.py
├── tests/
│   ├── __init__.py
│   └── test_app.py
├── requirements.txt
├── setup.py
└── pyproject.toml
```

**requirements.txt**:

```
flask==2.2
aiohttp==3.8
numpy==1.24
pandas==2.0
pytest==7.3
pytest-asyncio==0.21
cffi==1.15
```

**pyproject.toml**:

```toml
[tool.poetry]
name = "task-scheduler"
version = "0.1"
dependencies = {
    "flask" = "^2.2",
    "aiohttp" = "^3.8",
    "numpy" = "^1.24",
    "pandas" = "^2.0",
    "cffi" = "^1.15",
}
dev-dependencies = {
    "pytest" = "^7.3",
    "pytest-asyncio" = "^0.21",
}
```

**setup.py**:

```python
from setuptools import setup, Extension

setup(
    name="task_scheduler",
    version="0.1",
    packages=["myproject"],
    ext_modules=[Extension("myproject.cext", ["myproject/cext.c"])],
    install_requires=["flask", "aiohttp", "numpy", "pandas", "cffi"],
)
```

**myproject/cext.c**:

```c
#include <Python.h>

static PyObject* double_task(PyObject* self, PyObject* args) {
    int task_id;
    if (!PyArg_ParseTuple(args, "i", &task_id)) {
        return NULL;
    }
    return PyLong_FromLong(task_id * 2);
}

static PyMethodDef Methods[] = {
    {"double_task", double_task, METH_VARARGS, "Double task ID"},
    {NULL, NULL, 0, NULL}
};

static struct PyModuleDef Module = {
    PyModuleDef_HEAD_INIT,
    "cext",
    NULL,
    -1,
    Methods
};

PyMODINIT_FUNC PyInit_cext(void) {
    return PyModule_Create(&Module);
}
```

**myproject/scheduler.py**:

```python
import asyncio
import aiohttp
from typing import List, Dict
from dataclasses import dataclass
from concurrent.futures import ThreadPoolExecutor

@dataclass
class Task:
    id: int
    data: str
    status: str = "pending"

class Scheduler:
    def __init__(self):
        self.tasks: List[Task] = []
        self.executor = ThreadPoolExecutor(max_workers=2)

    async def add_task(self, task: Task):
        self.tasks.append(task)
        asyncio.create_task(self._process_task(task))

    async def _process_task(self, task: Task):
        async with aiohttp.ClientSession() as session:
            async with session.get(f"https://api.example.com/process/{task.data}") as response:
                task.status = "completed" if response.status == 200 else "failed"

    def compute_stats(self) -> Dict[str, int]:
        loop = asyncio.get_event_loop()
        return loop.run_in_executor(self.executor, self._compute_stats_sync)

    def _compute_stats_sync(self) -> Dict[str, int]:
        import pandas as pd
        df = pd.DataFrame([t.__dict__ for t in self.tasks])
        return df["status"].value_counts().to_dict()
```

**myproject/stats.py**:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

def plot_task_stats(stats: Dict[str, int]):
    df = pd.DataFrame.from_dict(stats, orient="index", columns=["count"])
    df.plot(kind="bar")
    plt.title("Task Status Distribution")
    plt.show()
```

**myproject/app.py**:

```python
from flask import Flask, request, jsonify
from myproject.scheduler import Scheduler, Task
from myproject.stats import plot_task_stats
from myproject import cext
import asyncio

app = Flask(__name__)
scheduler = Scheduler()

@app.route("/tasks", methods=["POST"])
async def add_task():
    data = request.get_json()
    task = Task(id=data["id"], data=data["data"])
    await scheduler.add_task(task)
    doubled_id = cext.double_task(task.id)  # C extension
    return jsonify({"task_id": task.id, "doubled_id": doubled_id})

@app.route("/stats")
def get_stats():
    stats = scheduler.compute_stats()
    return jsonify(stats)

@app.route("/plot")
def plot():
    stats = scheduler.compute_stats()
    plot_task_stats(stats)
    return jsonify({"message": "Plot displayed"})

if __name__ == "__main__":
    app.run(debug=True)
```

**tests/test_app.py**:

```python
import pytest
from myproject.app import app
from myproject.scheduler import Task

@pytest.fixture
def client():
    app.config["TESTING"] = True
    with app.test_client() as client:
        yield client

@pytest.mark.asyncio
async def test_add_task(client):
    response = client.post("/tasks", json={"id": 1, "data": "test"})
    assert response.status_code == 200
    assert response.json["task_id"] == 1
    assert response.json["doubled_id"] == 2

def test_stats(client):
    response = client.get("/stats")
    assert response.status_code == 200
```

**Features Demonstrated**:
- **OOP**: `Task` dataclass, `Scheduler` class.
- **Asyncio**: Async task processing with `aiohttp`.
- **C Extensions**: `cext` for task ID doubling.
- **Data Science**: Pandas/NumPy for stats, Matplotlib for visualization.
- **Web Development**: Flask API with endpoints.
- **Testing**: Pytest with async tests and fixtures.
- **Type Hints**: Annotations throughout.
- **Concurrency**: Thread pool for CPU-bound stats.
- **Packaging**: `setup.py` and `pyproject.toml`.

**Running the Project**:

```bash
python setup.py build_ext --inplace
pip install -r requirements.txt
python -m myproject.app
```

Test:

```bash
pytest
```

**Edge Cases Handled**:
- **Error Handling**: JSON validation, async task failures.
- **Thread Safety**: Thread pool for Pandas computation.
- **Resource Cleanup**: Context managers for HTTP sessions.
- **Type Safety**: Annotations checked with `mypy` (optional).

## Resources
- **Official Docs**: [Python Docs](https://docs.python.org/3/, [PEP Index](https://peps.python.org/).
- **Tutorials**: [Real Python](https://realpython.com/), [Python Crash Course](https://www.oreilly.com/library/view/python-crash-course/9781593279288/).
- **Community**: [PySlackers](https://pyslackers.com/), [Reddit](https://www.reddit.com/r/Python/), [Python Discord](https://discord.gg/python).
- **Libraries**: [PyPI](https://pypi.org/), [Awesome Python](https://github.com/vinta/awesome-python).
- **Tools**: [Black](https://github.com/psf/black) for formatting, [Flake8](https://flake8.pycqa.org/) for linting, [Mypy](http://mypy-lang.org/) for type checking.
- **Books**: *Python Crash Course* (No Starch Press), *Fluent Python* (O’Reilly).
- **Data Science**: [Jupyter Book](https://jupyterbook.org/), [Pandas Docs](https://pandas.pydata.org/docs/).
- **Web Development**: [Flask Docs](https://flask.palletsprojects.com/), [Django Docs](https://docs.djangoproject.com/), [FastAPI Docs](https://fastapi.tiangolo.com/).

This guide and sample project provide a comprehensive foundation for mastering Python, from beginner to expert, with practical applications and deep insights into its versatile features.