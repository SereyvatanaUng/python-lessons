# Overview

This repo summarizes lessons of python from section 1 to 10.

# 1. Sequential Programming Plan

What we've learnt:

- Sequential Flow of a program
- [Pseudocode](#11-pseudocode)
- [Flowchart](#12-flowchart)
- [Anaconda](#13-conda-command)

## 1.1. Pseudocode

Example: Print 'pass' if score >= 60 otherwise print 'fail'

```
input score
if score >= 60:
    print('pass')
else:
    print('fail')
```

## 1.2. Flowchart

Some flow chart shapes:  
![flowchat img](/assets/flowcharts.png)

## 1.3. Conda command

- Create a new virtual env, run: `conda create --name <env-name> python=<py-version>`
- List all environments, run: `conda env list`
- Activate an environment, run: `conda activate <env-name>`
- Deactivate an environment, run: `conda deactivate`
- For more commands, see [here](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)

# 2. Variables and Data Type operators

What we've learnt:

- [Data types](#21-data-types) like: string, numerical, boolean
- [Operators](#22-operators): arithmetic, ....
- [Naming conventions](#23-naming-conventions)

## 2.1. Data Types

Overview of python data types:
![data types img](/assets/data-type.png)

### 2.1.1. `type()` function

Use `type()` to check the data type.
Example:

```python
type(10) # Output: int
type(10.0) # Output: float
```

### 2.1.2. Data type conversion

Example:

```python
# Covert to string
str(2) # Output: '2'

# Convert to integer
int('10') # Output: 10
```

## 2.2. Operators

### 2.2.1. Arithmetic Operators

- `+`, `-`, `*`, `/` : We all know these...
- `%` : returns the **_remainder_** of the division. (រកសំណល់)
- `//` : returns the **_integer part_** of the division.
- `**` : Exponentiation (ស្វ័យគុណ)

### 2.2.2. Arithmetic on string

Example:

```python
'Hello' * 2 # Output:'HelloHello'

'Hello' + 'World' # Output: 'Hello World'
```

### 2.2.3. Assignment Operators

Example of **Multiple Assignment**:

```python
num1, num2, num3 = 200
# How it works:
# 200 assigned to 'num3' assigned to 'num2' then assigned to 'num1'
```

Example of **Simultaneous Assignment**:

```python
x, y = 100, 200
# 100 is assigned to x. 200 is assigned to y.
```

### 2.2.4. Shorthand Operators

`result = result * 2` can be written as `result *= 2`.

## 2.3.🔥 Naming Conventions

Rules to name a variable in python:

- Use letters and numbers
- Use underscore
- 1st char of a name must NOT be a number.
- Do not use **python keywords** for naming.

For more rules and styles, see the **PEP8** documentation.

# 3. String input output, Built-in functions and modules

What we've learnt:

- [String](#31-string)
- [Input function](#32-input-function)
- [Print function](#33-print-function)
- [Built-in functions](#34-built-in-function)
- [Built-in modules](#35-built-in-module)

## 3.1. String

We can do many things with strings such as:

- Indexing:

  ```python
  'hello'[2] # Output: 'l'
  'hello'[-1] # Output: '0'
  ```

- Multi line string:
  ```python
  text = '''This string occurs
  on multiple lines.'''
  ```

### 3.1.1. Escape Sequence

It is a way to escape the special meaning of some characters so that they can be used like normal string.  
Example: This is how to use quotes in string

```python
text = 'I don\'t like cookies.'
```

### 3.1.2.🔥 String Formatting

There are two ways that I know:

- From the school (`.format` method):

  ```python
  val1 = '1'
  val2 = 2
  print('first val is {} and second val is {}'.format(val1, val2))

  # Output: 'first val is 1 and second val is 2'


  print('I like {1} and {0}').format('python', 'java')

  # Output: 'I like java and python'


  print('{:10}').format(123)
  # Output: '       123'
  # It will output 123 in the 10 spaces.
  ```

- From the internet (`f''` expression):
  ```python
  val1 = '1'
  val2 = 2
  print(f'first val is {val1} and second val is {val2}')
  ```

### 3.1.3. `split()` method

We can use `.split()` method to split strings. It returns a list of splitted strings.  
Example:

```python
'python is cool'.split()
# Output: ['python', 'is', 'cool']
# It splits based on whitespace by default.

'2023.3.13'.split('.')
# Output: ['2023', '3', '13']
# It splits based on the dot.
```

### 3.1.4. `isdigit()` method

This is a method on a string that returns `True` if the string looks like integer. If there is decimal point or negative signs, it returns `False`.

## 3.2. `input()` function

It gets input from user and returns it as `string`.  
Example:

```python
x = int(input('first int: '))
y = int(input('second int: '))
print(x + y)

# Output:
'''
first int: 12
second int: 11
23
'''
```

Example of splitting inputs:

```python
num1, num2 = input('numbers separated by space: ').split()
print(num1, num2)

# Output:
'''
numbers separated by space: 12 23
12 23
'''
# num1, num2 are still strings.
```

## 3.3. `print()` function

By default, it separates each input by whitespace. Example:

```python
print('hello', 'world')
# Output: hello world
```

`end` parameter of the function. By default, it is a line break (\n). Example:

```python
print('hello')
print('world')
# Output:
'''
hello
world
'''
```

`sep` parameter of the function. By default, it is a whitespace. Example:

```python
print('hello', 'world', sep='**')
# Output: hello**world
```

## 3.4. Built-in Function

Function receives input (aka. argument), does some operation and then it outputs result (aka. return results).

Functions that can be called without importing are called **built-in functions**. Example: `print` and `input` functions that we've learnt.

[Here](https://docs.python.org/3/library/functions.html) are all **built-in functions** in python.

Some useful functions:

- `input`
- `print`
- `min` : it takes a list or tuple as argument and returns the smallest element in the list.
- `max` : returns the biggest element.

  ```python
  print(min(3,4,5))
  # Output: 3

  print(max(3,4,5))
  # Output: 5
  ```

- `abs` : it returns the absolute value.
- `sorted` : it returns a new sorted list. (Not to be confused with `.sort` method of `list`)

  ```python
  sorted('bcade')
  # Output: ['a', 'b', 'c', 'd', 'e']

  sorted('bcade', reverse=True)
  # Output: ['e', 'd', 'c', 'b', 'a']
  ```

## 3.5. Built-in Module

A module is a python file that collects functions, methods, classes .etc.  
Python has many **built-in modules** aka. **Standard Library**.

### 3.5.1. How to import a module

Example: multiple imports

```python
import module1, module2, ....
```

Example: import and assign an alias

```python
import random as rd
```

Example: `from`...`import` statement

```python
from [module_name] import [class_name].[method_name]
```

## 3.6. `random()` vs `randrange()` vs `randint()`

- `random()` returns a float between 0 (inclusive) and 1 (exclusive)
- `randrange(a, b, step)` does NOT include `b`
- `randint(a, b)` includes `b`

# 4. Boolean Expression

What we've learnt:

- [boolean data type](#41-boolean-data-type)
- [Operators](#42-types-of-operators) that return boolean: comparison, logical, membership, identity.

## 4.1. Boolean data type

Example:

```python
bool('')
# Output: False

bool(-1)
# Output: True

bool(0)
# Output: False

bool(123)
# Output: True

bool(None)
# Output: False
```

## 4.2. Types of operators

Comparison operators include: ==, !=, <, >, <=, >=

```python
1 > 2
# Output: False

n = 10
1 < n < 11
# Output: True
```

Logical Operators include: `and`, `or`, `not`

```python
True and False
# Output: False
```

Membership Operators include: `in`, `not in`

```python
'a' in 'halo'
# Output: True
```

🔥Identity Operators include: `is`, `not is`

```python
a = 'a'
b = 'a'
a is b
# Output: True

a = 1
b = 1.0
a == b
# Output: True

a is b
# Output: False
```

## 4.3. Operator Precedence

The upper operators have higher precedence (power)
![table-img](/assets/precedence-table.png)

# 5. Conditional-1

What we've learnt:

- if condition
- `pass` keyword

## 5.1. `if` statement

Example:

```python
age = 18
if age < 20:
    print('youth discount')

# Output: youth discount
```

## 5.2. `pass` keyword

It is used when we want to skip the block. It is useful when we don't know what to write in that block yet.  
Example:

```python
age = 18
if age < 20:
    pass

# I don't know what to code in if block yet, so I wrote 'pass'
```

# 6. Conditional-2

What we've learnt:

- `else` statement
- `elif` statement
- Nested conditions

# 7. List data type

What we've learnt:

- [list indexing](#71-list-indexing)
- [list slicing](#73-list-slicing)
- [membership operator](#74-in-operator)
- [list methods](#75-list-methods)

## 7.1. List indexing

Example:

```python
score_list = [20, 50, 60, 80, 12]
print(score_list[0])
# Output: 20

print(score_list[-3])
# Output: 60
```

## 7.2. Add items into list

### 7.2.1 Using `.append()` method

Example

```python
bts = ['v']
bts.append('jimin')
print(bts)
# Output: ['v', 'jimin']
```

### 7.2.2. Using `+` operator

To use + sign, the element to be added must be a list
Example:

```python
bts = ['v']
bts = bts + 'jimin'
# Output: ERROR

bts = bts + ['jimin']
# Output: ['v', 'jimin']
```

## 7.3. List Slicing

It is a process of select a portion of a list and output it as a new list.  
**Syntax:** `a_list[start:stop:step]`

- start is included
- stop is not included

Example:

```python
a_list = [12, 14, 15, 66, 17]
a_list[1:3]
# Output: [14,15]

a_list[:3]
# Output: [12,14,15]

a_list[:-2]
# Output: [12,14,15]
# 66 is on index -2, so it is not included
```

## 7.4. `in` operator

Example:

```python
a_list = [10, 20, 30, 40]

10 in a_list
# Output: True

10 not in a_list
# Output: False
```

## 7.5. List Methods

![list-methods](/assets/list-methods.png)

### 7.5.1. `.append` method

Its argument is anything. It adds item to the original list.  
Example:

```python
lst = [1,2,3]
lst.append('abc')
print(lst)
# Output: [1,2,3,'abc']
```

### 7.5.2. `.extend` method

Its argument is only iterable (like: string, list, tuple...). It adds each element of the `iterable` to the original list.  
Example:

```python
lst = [1,2,3]
lst.extend('abc')
print(lst)
# Output: [1,2,3,'a','b','c']
```

### 7.5.3. `.insert` method

Syntax: `.insert(index, obj)`. It adds any item to the original list at the specified index.  
Example:

```python
lst = [1,2,3]
lst.insert(1, 'haha')
print(lst)
# Output: [1, 'haha', 2, 3]
```

### 7.5.4. `.remove` method

Its argument is the element/value to be removed. It will remove the first element that occurs.  
Example:

```python
lst = [1,2,3,1]
lst.remove(1)
print(lst)
# Output: [2,3,1]
```

**Warning**: It can throw `ValueError` if the input element is not found.

How to safely remove an element:

```python
lst = [1,2,3]
if 2 in lst:
    lst.remove(2)
```

### 7.5.5. `.pop` method

It removes the last element in a list and returns that last element. Example:

```python
lst = [1,2,3]
last_itm = lst.pop()
print(last_itm)
# Output: 3

print(lst)
# Output: [1,2]
```

### 7.5.6. Python's `del` keyword

Syntax: `del list[index]`. It deletes item at the specified index.

## 7.6. Built-in functions used with list

They are:

- `len()` function
- `max()`, `min()` functions
- `sum()` function
- `any()` function returns True if there's at least one non-zero element in the list.

# 8. Loop-1: `for` loop

What we've learnt:

- [for loop](#81-for-loop)
- `range` function

## 8.1. `for` loop

Syntax:

```python
for var_name in iterable:
    # your code here...
```

Example:

```python
# Use underscore (_) if we don't use the variable
for _ in range(3):
    print('haha')
# Output: 'haha' 3 times

# Use variable name when we need it:
for i in range(3):
    print(i)
# Output: 0, 1, 2
```

## 8.2. `range` function

Syntax: `range(start=0, stop, step=1)`. Its arguments are all integers.

- `start` is included
- `stop` is not included

# 9. Loop-2: `while` loop

What we've learnt:

- `while` loop
- `break`, `continue` keywords

## 9.1. `while` loop

Unlike `for` loop, we need to initialize i first before we can use `while` loop.  
Example:

```python
i = 0
while i < 3:
    print(i)
    i += 1

# Output: 0,1,2
```

## 9.2. `break` or `continue`

- `break` keyword will exit the loop.
- `continue` will stop the CURRENT iteration and go to the next iteration if there's still one.

**Warning**: These 2 must be inside a loop. Otherwise, it will show errors.
