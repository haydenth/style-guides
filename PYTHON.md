Python Styleguide Requirements
================

In general, we follow the standard python `pep8` style requirements but with a few notable differences:

* ignore E111 (indentation is not a multiple of four) - we use *2 space indentation*
* ignore E302 (expected 2 blank lines, found 0) - we use *1 line break between function defs*
* strictly enforce E501 (line too long (82 > 79 characters)) - strongly enforce 80 char max
* NO spaces in import statement block

Pull requests that do not meet this linting/style guide *will be rejected*

File Structure
=================

Below is an example file structure, please stack the import requests as seen below:

```
from common.something import something
import requests
import os

do_something()

```

Function Definition
==================
```
def this_is_a_function(parameter_name):
  ''' please document the function here '''
  some_function(parameter1, parameter2)
  for i in list:
    do_something_else()
```
