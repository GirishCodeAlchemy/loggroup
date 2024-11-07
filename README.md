# pyloggroup

`pyloggroup` is a Python package that provides decorators for creating log groups for a functions. This package can be used to enhance logging in your Python projects.

## Installation

You can install `pyloggroup` using pip:

```sh
pip install pyloggroup
```

## Usage

Here is how you can use the decorators provided by `pyloggroup` in your Python code:

1. Log groups

```python

from pyloggroup import log_group
import logging

# Ensure the logger level is set to INFO
logging.getLogger(__name__).setLevel(logging.INFO)

@log_group("MainGroup")
def main_function():
    print("Inside main function")
    print("*"*20)
    logging.info("Inside main function")
    inner_function()

@log_group("InnerGroup")
def inner_function():
    print("Inside inner function")
    print("*"*20)
    logging.info("Inside inner function")
    innermost_function()

@log_group("InnermostGroup")
def innermost_function():
    print("Inside innermost function")
    print("*"*20)
    logging.info("Inside innermost function")
    print("Innermost function executed")

main_function()
```

![image](https://github.com/user-attachments/assets/ddebb993-66ba-4bad-89ab-498a8cee08f5)


### Decorators

- **`log_group(group_name)`**: This decorator logs entry and exit points of the decorated function, grouping logs under a specified group name.

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more details.
