---
title: "Improve Python Unit Testing with a Helper Package"
date: 2023-05-04T08:48:23+01:00
ShowToc: true
ShowCodeCopyButtons: true
ShowReadingTime: true
tags: [Python]
draft: false
---


{{< details "**TL;DR**" >}}
- Create a `helpers` folder in `tests` with an `__init__.py`
- Add a function to the `__init__.py` file to return the path to test data files [resolve_test_data_path](#adding-the-resolve_test_data_path-function)
- Update [pytest configuration](#updating-the-pytest-configuration) to ignore the helpers folder when searching for tests
{{< /details >}}


Using a helper package can help keep your test files organized and focused on testing the actual code. By storing necessary functions and data in a separate `helpers` package, you can reduce clutter and make your tests easier to read and understand. 

## Creating the Helpers Package

To create a helper package, you'll first need to create a `helpers` folder under your `tests` directory. Since this folder will be a package, you must include a `__init__.py `file in it. You may also want to create a subfolder for your test data, as I do in this example:

```
tests/
├── helpers/
│   ├── __init__.py
│   ├── data/
└── conftest.py
```

## Adding the `resolve_test_data_path` Function

Next, add a function to the `__init__.py` file to return the path to your test data files. This function will be used by your tests to find the data directory:

```python
# helpers/__init__.py

import pathlib

def resolve_test_data_path(file_name: str):
    path = pathlib.Path(__file__).parent / "data" / file_name
    return path

```

## Importing the Helpers Package

To import the `helpers` package in your tests, you'll need to add the path to the `helpers` folder to your `sys.path`. You can do this by adding the following code to your conftest.py file:

```python
# tests/conftest.py

import pathlib
import sys

helpers_path = str(pathlib.Path(__file__).parent)
sys.path.append(helpers_path)

```

## Updating the pytest Configuration

Finally, you'll need to update your `pytest` configuration to ignore the `helpers` folder when searching for tests. This can be done by adding the following line to your `pyproject.toml` file:

```
[tools.pytest.ini.options]
norecursedirs = "tests/helpers"
```

## Using the Helpers Package

Now that you've created and imported your `helpers` package, you can use it in your tests. For example, you can use the `resolve_test_data_path` function to get the path to a test data file:

```python
import pytest
import helpers


@pytest.fixture
def fixt_test_data_file():
    path = helpers.resolve_test_data_path("my_test_data.csv")
    return path

def test_can_read_file(fixt_test_data_file):
    my_file_reader_func(fixt_test_data_file)
    ...

```

Using a `helpers` package can make your test files cleaner, easier to read, and more focused on testing the actual code. You can use the helpers package to contain test data files and definitions of mocked or fake objects.

