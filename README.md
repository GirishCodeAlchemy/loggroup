# PyLogGroup

[![PyPI version](https://img.shields.io/pypi/v/pyloggroup)](https://pypi.org/project/pyloggroup/)
![License](https://img.shields.io/pypi/l/pyloggroup)
![Python versions](https://img.shields.io/pypi/pyversions/pyloggroup)

`pyloggroup` is a lightweight Python package designed to improve logging readability by creating structured log groups for functions. This package is particularly useful for projects with nested or complex functions, where understanding the flow of function calls is essential.

With `pyloggroup`, you can use decorators to group log entries under specific names, allowing for a tree-like view of log output. This helps make logs more organized and easier to analyze, especially in debugging and monitoring scenarios.

## Features

- **Log Grouping**: Easily group related logs for nested function calls.
- **Tree Structure**: Organizes log entries in a hierarchical structure.
- **Simple Integration**: Use decorators to seamlessly integrate with existing functions.

## Installation

Install `pyloggroup` using pip:

```sh
pip install pyloggroup
```

## Usage

To start using `pyloggroup`, import the decorator and add it to any function you wish to log. Ensure that the logger level is set to `INFO` or higher to see the log output.

### Example

Here's an example showing how to use `pyloggroup` to create structured log groups for functions:

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

When running the example, the logs will be grouped in a nested structure, providing a clear view of the sequence of function calls.

### Output Example

When using `pyloggroup`, the log output will look something like this:

![image](https://github.com/user-attachments/assets/ddebb993-66ba-4bad-89ab-498a8cee08f5)

This structured format helps you understand the call hierarchy and follow the flow of your code more easily.

## API Reference

### Decorators

- **`@log_group(group_name)`**: This decorator logs the entry and exit points of a function, grouping the logs under the specified `group_name`. It can be applied to any function to create a hierarchical log group structure, helping you track the nested execution flow.

### Configuration Options

`pyloggroup` can be customized by setting the logging level in your application. By default, it uses Python's `logging` library, which allows you to configure log levels, formats, and handlers.

## Contributing

Contributions are welcome! If you'd like to improve or expand this package, feel free to submit a pull request on GitHub.

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more details.

## Contact

For questions or suggestions, please contact [GirishCodeAlchemy](mailto:girishcodealchemy@gmail.com).
