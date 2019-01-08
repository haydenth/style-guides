Python Styleguide Requirements
================

The goal of a styleguide/lint guide for code is to create code that is:

* Compact - Code libraries should be compact, logic should be bundled together and not spread out over many lines. 
* Easy to Read - Code should be easy to read and clearly documented when necessary.
* Not Burdensome to Write

In general, we follow the standard python `pep8` style requirements but with a few notable differences:

* ignore E111 (indentation is not a multiple of four) - we use **2 space indentation**
* ignore E302 (expected 2 blank lines, found 0/1) - we use **1 line break between function defs**
* strictly enforce E501 (line too long (82 > 79 characters)) - **strongly enforce 80 char max**
* NO spaces in import statement block
* **NO TABS EVER**

Pull requests that do not meet this linting/style guide **will be rejected**. Below is the alias I add to my `.bashrc` (or `.bash_profile` on mac) that overrides the `pep8` command

```
alias pep8="pep8 --ignore=E302,E111"
```

File Structure
=================

Below is an example file structure, please stack the import requests as seen below:

```python
from common.something import something
import requests
import os

do_something()
```

Function Definition
==================
```python
def this_is_a_function(parameter_name):
  ''' please document the function here '''
  some_function(parameter1, parameter2)
  for i in list:
    do_something_else()
```

Function Calls with Lots of Parameters
=====================
Sometimes when invoking a function with a lot of parameters, you need to go on a second or third line. When doing this, please indent two spaces on the line below. Example:

```python
do_something(parameter1, parameter2, parameter3,
  parameter4, parameter5, parameter6,
  parameter7)
```

**DO NOT** do the old python style function invocation style
```python
do_something(parameter1,
             parameter2,
             parameter3)
```

Class Definition
===============
Please note - class names should be in **CAMEL CASE** while all variables and methods should be in non-camel case underscore-based naming.

```python
import requests
import os

class ClassName:
  
  def __init__(self):
    ''' this is the constructor '''
    self._some_private_value = '1234'

  def do_something(self, i):
    ''' do some magical operations here'''
    return i ** 2
```

Please name PRIVATELY scoped attributes/methods differently from PUBLICLY scoped attributes and methods by starting the variable definition with an `_`. For instance:

```python
import requests
import os

class ClassName:
  
  def __init__(self):
    ''' this is the constructor '''
    self._some_private_value = '1234'
    self.some_public_value = 'asdf'

  def do_something_publicly(self, i):
    return i ** 2

  def _do_something_privately(self, i):
    return i ** 3

```

Clearly Name Variables
===================
Clearly name variables as much as possible.

* Using single letter variables names is appropriate in **some cases** such as when iterating in a list comprension
* Variable names that are abbreviations are usually ok. It's okay to shorten stuff like `SomeBigItem` to `sbi` as long as it's relatively clear of the origin.
* Otherwise, variable names such as `a`, `bb` or `aa` are not acceptable



Use List Comphrensions
=================
Whenever possible use list comphrenesions in lieu of a for loop. For instance the below function to compute squared values:

```python
output_list = []
for i in range(0, 10):
  output_list.append(i ** 2)

```

Can easily be stated in a single line as:

```python
output_list = [i ** 2 for i in range(0, 10)]
```

If you're not familiar with list comprhensions please [read the python documentation](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python). Using list comprhensions properly makes the code dramatically more readable and maintainable.

Sensible Comments
===================
Leave comments when necessary to explain some relevant thing but it's not necessary to leave comments if the function is clear in its purpose. Never leave frivolous comments describing what is obvious. Below is an example of a good comment:

```python
def do_something_complicated():
  ''' this function is tricky - it can sometimes return
  different results depending on the time of day. this is 
  from a specific client request that data from 12-1 be multipled
  by fourteen'''
  ...
```

And a BAD comment below. Don't write this comment, it's obvious and takes up a useless line of code.
```python
def do_something():
  ''' loop over the list and power 2 '''
  return [i ** 2 for i in range(0, 10)]
