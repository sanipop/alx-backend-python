# 0x01. Python - Async

## Overview

This project focuses on asynchronous programming in Python using the `asyncio` module. You will learn how to write asynchronous code, manage concurrency, and utilize tasks to improve the efficiency of your programs.

## Learning Objectives

By the end of this project, you should be able to:
- Understand and use the `async` and `await` syntax.
- Execute an asynchronous program using `asyncio`.
- Run concurrent coroutines.
- Create and manage `asyncio` tasks.
- Utilize the `random` module effectively in asynchronous code.

## Resources

To complete this project, you will need to read or watch the following resources:
- [Async IO in Python: A Complete Walkthrough](https://realpython.com/async-io-python/)
- [asyncio - Asynchronous I/O](https://docs.python.org/3/library/asyncio.html)
- [random.uniform](https://docs.python.org/3/library/random.html#random.uniform)

## Requirements

- A `README.md` file, at the root of the folder of the project, is mandatory.
- Allowed editors: `vi`, `vim`, `emacs`.
- All files will be interpreted/compiled on Ubuntu 18.04 LTS using `python3` (version 3.7).
- All files should end with a new line.
- All files must be executable.
- The length of files will be tested using `wc`.
- The first line of all files should be exactly `#!/usr/bin/env python3`.
- Code should use the `pycodestyle` style (version 2.5.x).
- All functions and coroutines must be type-annotated.
- All modules should have documentation.
- All functions should have documentation that explains their purpose.

## Tasks

### Task 0: The Basics of Async

Write an asynchronous coroutine `wait_random` that takes an integer argument (`max_delay`, with a default value of 10). This coroutine should wait for a random delay between 0 and `max_delay` (inclusive, float value) seconds and eventually return it.

**File:** `0-basic_async_syntax.py`

```python
import asyncio
import random

async def wait_random(max_delay: int = 10) -> float:
    delay = random.uniform(0, max_delay)
    await asyncio.sleep(delay)
    return delay
```

### Task 1: Execute Multiple Coroutines Concurrently

Import `wait_random` and write an async routine `wait_n` that takes in 2 integer arguments: `n` and `max_delay`. This routine should spawn `wait_random` n times with the specified `max_delay` and return the list of all the delays in ascending order without using `sort()`.

**File:** `1-concurrent_coroutines.py`

```python
import asyncio
from typing import List

wait_random = __import__('0-basic_async_syntax').wait_random

async def wait_n(n: int, max_delay: int) -> List[float]:
    delays = await asyncio.gather(*(wait_random(max_delay) for _ in range(n)))
    return sorted(delays)
```

### Task 2: Measure the Runtime

Create a function `measure_time` with integers `n` and `max_delay` as arguments. This function should measure the total execution time for `wait_n(n, max_delay)` and return `total_time / n`.

**File:** `2-measure_runtime.py`

```python
import time
import asyncio
from typing import List

wait_n = __import__('1-concurrent_coroutines').wait_n

def measure_time(n: int, max_delay: int) -> float:
    start_time = time.time()
    asyncio.run(wait_n(n, max_delay))
    end_time = time.time()
    total_time = end_time - start_time
    return total_time / n
```

### Task 3: Tasks

Write a function `task_wait_random` that takes an integer `max_delay` and returns an `asyncio.Task`.

**File:** `3-tasks.py`

```python
import asyncio
from typing import Any

wait_random = __import__('0-basic_async_syntax').wait_random

def task_wait_random(max_delay: int) -> asyncio.Task:
    return asyncio.create_task(wait_random(max_delay))
```

### Task 4: Task Concurrency

Alter the code from `wait_n` into a new function `task_wait_n`. The code should be nearly identical to `wait_n`, but you should call `task_wait_random`.

**File:** `4-tasks.py`

```python
import asyncio
from typing import List

task_wait_random = __import__('3-tasks').task_wait_random

async def task_wait_n(n: int, max_delay: int) -> List[float]:
    tasks = [task_wait_random(max_delay) for _ in range(n)]
    delays = await asyncio.gather(*tasks)
    return sorted(delays)
```

## Repository

**GitHub Repository:** [alx-backend-python](https://github.com/yourusername/alx-backend-python)  
**Directory:** `0x01-python_async_function`

---

Ensure that all your code files are executable, properly type-annotated, and well-documented as per the requirements. This README provides a structured overview of the project, tasks, and resources to guide you through the asynchronous programming concepts in Python.
