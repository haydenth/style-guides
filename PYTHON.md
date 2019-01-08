Python Styleguide Requirements
================

In general, we follow the standard python `pep8` style requirements but with a few notable differences:

* ignore E111 (indentation is not a multiple of four)
* ignore E302 (expected 2 blank lines, found 0)
* strictly enforce E501 (line too long (82 > 79 characters))
* NO spaces in import statement block

Example File
=================

Below is an example file structure, please stack the import requests as seen below:

```
from common.something import something
import requests
import os

do_something()

```

Example Function
==================
```
def this_is_a_function(parameter_name):
  ''' please document the function here '''
  some_function(parameter1, parameter2)
  for i in list:
    do_something_else()
```
