---
title: Python
layout: default
nav_order: 6
permalink: /python/
---

# Python General

## Variables

### Assignment

The expression on the right side of the assignment operator ('=') is evaluated and then assigned to the variable on the left side of the assignment.

```python
count = 22              # count = 22
count = count + 1       # count = 23
```

## Data Types

|Type   |Example                                        |Notes                          |
|-------|-----------------------------------------------|-------------------------------|
|int    |`7`                                            |Integer                        |
|float  |`7.11`                                         |Real number                    |
|str    |`"apple"`, `'apple'`                           |String, text                   |
|list   |`["apple", "banana", "coconut"]`               | Sequence of values, list      |
|dict   |`{"apple": 1.5, "banana": 1.7, "coconut": 3.2}`| Key-value mapping, dictionary |
|bool   |`True, False`                                  |boolean                        |

### Conversions of Data Types

```python
int("7")           # → 7
float("7.11")      # → 7.11
str(7)             # → '7'
list("abc")        # → ['a', 'b', 'c']
```

### Formatting strings

```python
name = "John"
age = 23
message = "My name is %s and I'm %d years old." % (name, age)
# message = "My name is John and I'm 23 years old."
```

### Lists

```python
nums = [4, 3, 2, 1]     # Create array
count = len(nums)       # count = 4
nums.append(5)          # nums = [4, 3, 2, 1, 5]
nums.sort()             # nums = [1, 2, 3, 4, 5]
for num in nums:
    print(num)
```

### Dictionary

```python
item_prices = {         # Initialize dictionary
    "carrot": 1.52,
    "bread" : 3.48,
    "milk"  : 3.82
}
item_prices["egg"] = 0.91   # Add key/value pair
count = len(item_prices)    # count = 4

for item in item_prices:
    price = item_prices[item]
    print("Item '%s' costs %.2f" % (item, price))

del item_prices["milk"]     # Remove entry by key
```

### Binary

```python
num = 4
result = num & 1        # Binary And. result = 1
result = num | 1        # Binary Or. result = 5
result = num << 3       # Shift bits 3 times to the left. result = 32
result = num >> 2       # Shift bits 2 times to the right. result = 1
result = num ^ 2        # Binary Xor. result = 6
```


## Operators

- Arithmetic: `+ - * / // % **`
- Comparison: `== != > < >= <= is is not`
- Logical: `and or not`
- Bitwise: `& | ^ ~ << >>`
- Walrus (3.8+): `:=`

### Arithmetic

```python
result = 2 + 2          # Addition. result = 4
result = 2 - 2          # Subtraction. result = 0
result = 3 * 4          # Multiplication. result = 12
result = 9 / 2          # Floating Division. result = 4.5
result = 9 // 2         # Integer Division (round down). result = 4
result = 7 % 2          # Remainder/Modulo. result = 1
result = 4 ** 3         # Exponentiation (i.e. 4^3). result = 64
```

### Short-hand

```python
result += 1             # Increase result by 1 (e.g. 9 -> 10)
result -= 1             # Decrease result by 1 (e.g. 9 -> 8)
result *= 4             # Multiply result by 4 (e.g. 9 -> 36)
result /= 2             # Divide result by 2   (e.g. 9 -> 4.5)
result //= 2            # Divide result by 2   (e.g. 9 -> 4)
```

### Comparison

Comparing values yields a boolean.

```python
2 == 3                  # False
2 == 2                  # True

a = 10
b = 12
result = a > b          # result = False
result = a < b          # result = True

a == 10 or b == 10      # True
a >= 10 and b <= 20     # True
```

## Control Flow

```python
# if-elif-else
if condition:
    ...
elif other:
    ...
else:
    ...

# for loop with enumerate
for i, item in enumerate(items, start=1):
    ...

# Basic for-loop
for i in range(10):
    print(i)            # prints numbers 0 through 9


# For-each loop
nums = [1, 2, 3, 4]
for num in nums:
    print(num)          # prints each value in nums


# while
while condition:
    ...
```


### Comprehensions

```python
squares = [x**2 for x in range(10)]
evens = {x for x in range(10) if x % 2 == 0}
squared_dict = {x: x**2 for x in range(5)}
```

## Functions

```python
def func(a, b=2, *, c=3):   # * forces keyword-only
    """Docstring here."""
    return a + b + c

# Lambda
add = lambda x, y: x + y

# Type hints (recommended)
from typing import Any, Sequence

def process(items: Sequence[Any]) -> int:
    ...

# Nested functions
def main() -> None:     # The function is named 'main' and returns nothing

    def sub_function(value : int) -> int:   # Functions can be defined within functions
        return value * 2

    num = 10
    num = sub_function(num)
```


## Classes

```python
class Solution:
    def __init__(self): # Constructor
        pass            # 'pass' does nothing (i.e. no-op)

    def get_average(self, numbers : list[int]) -> int:
        count = len(numbers)
        sum = self.sum_array(numbers)   # Must use 'self.method_name' when calling other functions
        return sum // count

    def sum_array(self, numbers : list[int]) -> int:
        sum = 0
        for num in numbers:
            sum += num
        return sum
```

## Exceptions

```python
try:
    ...
except (ValueError, TypeError) as e:
    ...
except Exception as e:      # broad but with logging
    ...
else:
    # no exception
    ...
finally:
    ...
```

## Main entry point

Runs only when the file is executed directly (`python file.py`), not when it is imported.

```python
if __name__ == "__main__":
    main()
```

## Packages
```python
# Import styles
import os
import numpy as np
from pathlib import Path
from collections import defaultdict, Counter

# Relative imports in packages
from .utils import helper
```

**Standard library:**

| Module | Use case |
|--------|----------|
| `pathlib` | File paths |
| `collections` | `defaultdict`, `Counter` |
| `itertools` | `chain`, `product`, `groupby` |
| `functools` | `lru_cache`, `partial` |
| `json`, `csv` | Data formats |
| `datetime` | Dates and times |
| `argparse` | Command-line interfaces |
| `logging` | Proper logging |
| `asyncio` | Async (3.11+ `TaskGroup`) |
| `contextlib` | `@contextmanager` |

**Third-party libraries:**

| Library | Use case |
|---------|----------|
| `rich` | Formatted terminal output |
| `typer` | Modern CLIs |
| `pydantic` | Data validation |
| `httpx` | HTTP client |
| `loguru` | Simple logging |
| `tqdm` | Progress bars |
| `pandas`, `numpy` | Data |
| `ruff`, `black` | Linting and formatting |

## Best Practices & Gotchas

**Best practices:**

- Use type hints.
- Prefer `pathlib` over `os.path`.
- Use f-strings (Python 3.6+).
- Use `enumerate()` instead of manual counters.
- Use `with` statements for files and other resources.
- Avoid `from module import *`.
- Use `ruff` instead of `flake8` + `isort`.
- Format with `black --line-length 100` (or `ruff format`).

**Common gotchas:**

- Mutable default arguments
- Late binding in closures
- `is` vs `==`
- Floating point precision
- List vs generator memory usage
