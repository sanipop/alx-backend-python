# Python Async Comprehension Project

## Table of Contents

- [Introduction](#introduction)
- [Learning Objectives](#learning-objectives)
- [Requirements](#requirements)
- [Tasks](#tasks)
  - [Task 0: Async Generator](#task-0-async-generator)
  - [Task 1: Async Comprehensions](#task-1-async-comprehensions)
  - [Task 2: Run Time for Four Parallel Comprehensions](#task-2-run-time-for-four-parallel-comprehensions)
- [Resources](#resources)

## Introduction

This project focuses on enhancing your skills in asynchronous programming in Python. You will learn how to write asynchronous generators, use async comprehensions, and type-annotate generators. The project consists of three main tasks, each building on the previous one.

## Learning Objectives

By the end of this project, you should be able to:

- Write an asynchronous generator.
- Use async comprehensions.
- Type-annotate generators.

## Requirements

- **Editors**: vi, vim, emacs
- **Python Version**: Python 3.7
- **OS**: Ubuntu 18.04 LTS
- **Style Guide**: pycodestyle (version 2.5.x)
- All files should end with a new line.
- The first line of all your files should be `#!/usr/bin/env python3`.
- Your code should be documented, including modules, functions, and coroutines.
- All functions and coroutines must be type-annotated.
- A `README.md` file at the root of the project is mandatory.

## Tasks

### Task 0: Async Generator

**Objective**: Write a coroutine called `async_generator` that loops 10 times, each time asynchronously waiting for 1 second and yielding a random number between 0 and 10.

**File**: `0-async_generator.py`

**Example**:
```python
import asyncio
async_generator = __import__('0-async_generator').async_generator

async def print_yielded_values():
    result = []
    async for i in async_generator():
        result.append(i)
    print(result)

asyncio.run(print_yielded_values())
```

### Task 1: Async Comprehensions

**Objective**: Import `async_generator` from the previous task and write a coroutine called `async_comprehension` that collects 10 random numbers using an async comprehension over `async_generator`, then returns the 10 random numbers.

**File**: `1-async_comprehension.py`

**Example**:
```python
import asyncio
async_comprehension = __import__('1-async_comprehension').async_comprehension

async def main():
    print(await async_comprehension())

asyncio.run(main())
```

### Task 2: Run Time for Four Parallel Comprehensions

**Objective**: Import `async_comprehension` from the previous file and write a `measure_runtime` coroutine that executes `async_comprehension` four times in parallel using `asyncio.gather`. Measure and return the total runtime.

**File**: `2-measure_runtime.py`

**Example**:
```python
import asyncio
measure_runtime = __import__('2-measure_runtime').measure_runtime

async def main():
    return await measure_runtime()

print(asyncio.run(main()))
```

## Resources

- [PEP 530 – Asynchronous Comprehensions](https://www.python.org/dev/peps/pep-0530/)
- [What’s New in Python: Asynchronous Comprehensions / Generators](https://docs.python.org/3/whatsnew/3.6.html#whatsnew36-pep530)
- [Type-hints for generators](https://docs.python.org/3/library/typing.html#typing.Generator)

This README file provides an overview of the project requirements, tasks, and resources. Follow the tasks sequentially, ensuring your code adheres to the specified requirements and guidelines. Good luck!
