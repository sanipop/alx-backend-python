# Python Variable Annotations Project

This project focuses on the use of type annotations in Python to specify function signatures and variable types, and to validate code using `mypy`.

## Resources

To help you understand and complete this project, refer to the following resources:

- [Python 3 typing documentation](https://docs.python.org/3/library/typing.html)
- [MyPy cheat sheet](https://mypy.readthedocs.io/en/stable/cheat_sheet_py3.html)

## Learning Objectives

By the end of this project, you should be able to:

- Understand and use type annotations in Python 3.
- Specify function signatures and variable types using type annotations.
- Understand the concept of duck typing.
- Validate your code with `mypy`.

## Requirements

- **Editors**: You can use `vi`, `vim`, or `emacs`.
- **Environment**: Your code will be interpreted/compiled on Ubuntu 18.04 LTS using Python 3.7.
- **Code Style**: Your code should follow the `pycodestyle` style (version 2.5.0).
- **Execution**: All your files must be executable.
- **Documentation**: Every module, class, and function must have documentation explaining its purpose.
- **File Length**: The length of your files will be tested using `wc`.
- **README**: A `README.md` file at the root of the project is mandatory.

## Tasks

### Task 0: Basic Annotations - Add

Write a type-annotated function `add` that takes two floats `a` and `b` as arguments and returns their sum as a float.

```python
def add(a: float, b: float) -> float:
    return a + b
```

### Task 1: Basic Annotations - Concat

Write a type-annotated function `concat` that takes two strings `str1` and `str2` as arguments and returns a concatenated string.

```python
def concat(str1: str, str2: str) -> str:
    return str1 + str2
```

### Task 2: Basic Annotations - Floor

Write a type-annotated function `floor` which takes a float `n` as an argument and returns the floor of the float.

```python
import math

def floor(n: float) -> int:
    return math.floor(n)
```

### Task 3: Basic Annotations - To String

Write a type-annotated function `to_str` that takes a float `n` as an argument and returns the string representation of the float.

```python
def to_str(n: float) -> str:
    return str(n)
```

### Task 4: Define Variables

Define and annotate the following variables with the specified values:

```python
a: int = 1
pi: float = 3.14
i_understand_annotations: bool = True
school: str = "Holberton"
```

### Task 5: Complex Types - List of Floats

Write a type-annotated function `sum_list` which takes a list `input_list` of floats as an argument and returns their sum as a float.

```python
from typing import List

def sum_list(input_list: List[float]) -> float:
    return sum(input_list)
```

### Task 6: Complex Types - Mixed List

Write a type-annotated function `sum_mixed_list` which takes a list `mxd_lst` of integers and floats and returns their sum as a float.

```python
from typing import List, Union

def sum_mixed_list(mxd_lst: List[Union[int, float]]) -> float:
    return sum(mxd_lst)
```

### Task 7: Complex Types - String and Int/Float to Tuple

Write a type-annotated function `to_kv` that takes a string `k` and an int or float `v` as arguments and returns a tuple. The first element of the tuple is the string `k`. The second element is the square of the int/float `v` and should be annotated as a float.

```python
from typing import Union, Tuple

def to_kv(k: str, v: Union[int, float]) -> Tuple[str, float]:
    return (k, float(v**2))
```

### Task 8: Complex Types - Functions

Write a type-annotated function `make_multiplier` that takes a float `multiplier` as an argument and returns a function that multiplies a float by `multiplier`.

```python
from typing import Callable

def make_multiplier(multiplier: float) -> Callable[[float], float]:
    def multiplier_func(x: float) -> float:
        return x * multiplier
    return multiplier_func
```

### Task 9: Duck Typing - Iterable Object

Annotate the below function’s parameters and return values with the appropriate types.

```python
from typing import Iterable, Sequence, List, Tuple

def element_length(lst: Iterable[Sequence]) -> List[Tuple[Sequence, int]]:
    return [(i, len(i)) for i in lst]
```

## Repository

Ensure your files are organized in the following structure:

- **GitHub repository**: `alx-backend-python`
- **Directory**: `0x00-python_variable_annotations`
- **Files**:
  - `0-add.py`
  - `1-concat.py`
  - `2-floor.py`
  - `3-to_str.py`
  - `4-define_variables.py`
  - `5-sum_list.py`
  - `6-sum_mixed_list.py`
  - `7-to_kv.py`
  - `8-make_multiplier.py`
  - `9-element_length.py`

Happy coding!
