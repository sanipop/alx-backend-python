# 0x03. Unittests and Integration Tests

## Overview

This project focuses on writing unit and integration tests for Python code. The goal is to ensure that individual functions work correctly and that various parts of the code interact as expected when integrated. The project emphasizes testing techniques such as mocking, parameterization, and the use of fixtures.

## Unit Testing

Unit testing involves testing individual functions to ensure they return expected results for different inputs, including standard and corner cases. The tests should focus on the logic within the function, mocking any external dependencies like network or database calls.

## Integration Testing

Integration tests check the interaction between different parts of the code, testing code paths end-to-end. While external calls such as HTTP requests and file I/O are mocked, the rest of the code interactions are tested in a realistic environment.

## Execution

Execute the tests using the following command:

```bash
$ python -m unittest path/to/test_file.py
```

## Resources

- [unittest — Unit testing framework](https://docs.python.org/3/library/unittest.html)
- [unittest.mock — mock object library](https://docs.python.org/3/library/unittest.mock.html)
- [How to mock a readonly property with mock?](https://stackoverflow.com/questions/11836436/mock-a-readonly-property)
- [parameterized](https://pypi.org/project/parameterized/)
- [Memoization](https://en.wikipedia.org/wiki/Memoization)

## Learning Objectives

By the end of this project, you should be able to:

- Differentiate between unit and integration tests.
- Understand and apply common testing patterns such as mocking, parameterization, and fixtures.

## Requirements

- Files will be interpreted/compiled on Ubuntu 18.04 LTS using Python 3.7.
- Each file should end with a new line and start with `#!/usr/bin/env python3`.
- Follow the pycodestyle style guide (version 2.5).
- All files must be executable.
- Modules, classes, and functions must have documentation.
- All functions and coroutines must be type-annotated.

## Required Files

- `utils.py`
- `client.py`
- `fixtures.py`

## Tasks

### Task 0: Parameterize a Unit Test

Write unit tests for `utils.access_nested_map`. Use `@parameterized.expand` to test various inputs.

### Task 1: Parameterize a Unit Test Exception

Write tests to ensure `utils.access_nested_map` raises `KeyError` for invalid paths using `@parameterized.expand`.

### Task 2: Mock HTTP Calls

Write tests for `utils.get_json` using `unittest.mock.patch` to mock `requests.get`.

### Task 3: Parameterize and Patch

Write tests for the `utils.memoize` decorator, ensuring the method is called only once even when accessed multiple times.

### Task 4: Parameterize and Patch as Decorators

Write tests for `client.GithubOrgClient.org`, ensuring `get_json` is called correctly using `@patch` and `@parameterized.expand`.

### Task 5: Mocking a Property

Write tests for `GithubOrgClient._public_repos_url`, using patch as a context manager.

### Task 6: More Patching

Write tests for `GithubOrgClient.public_repos`, mocking `get_json` and `_public_repos_url`.

### Task 7: Parameterize

Write tests for `GithubOrgClient.has_license`, parameterizing the inputs and expected results.

### Task 8: Integration Test: Fixtures

Write integration tests for `GithubOrgClient.public_repos`, mocking external requests and using fixtures for payloads.

## Repository Structure

```
alx-backend-python/
├── 0x03-Unittests_and_integration_tests/
│   ├── test_utils.py
│   ├── test_client.py
│   ├── utils.py
│   ├── client.py
│   └── fixtures.py
```

Ensure all tasks are implemented in their respective files as specified.
