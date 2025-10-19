# Python Toolbox

## Introduction to Iterators

### Iterator Fundamentals
#### Key Concepts
- **Instructor:** Hugo Bowne-Anderson, Data Scientist at DataCamp
- **Course Focus:** Iterables, iterators, list comprehensions, generators, and case study application

---

### What Are Iterables and Iterators?

**Iterables:**
- Objects that have an associated `iter()` method
- When `iter()` is applied, an iterator object is created

**Common Iterables:**
- Lists
- Strings
- Range objects
- Dictionaries
- File connections

**Iterators:**
- Objects with an associated `next()` method
- Produces consecutive values sequentially
- Raises `StopIteration` error when exhausted

---

### Basic Iteration with For Loops

**Iterating over a list:**
```python
avengers = ['Iron Man', 'Thor', 'Hulk']
for hero in avengers:
    print(hero)
```

**Iterating over a string:**
```python
for char in "Python":
    print(char)
```

**Iterating over a range:**
```python
for num in range(5):
    print(num)  # Prints 0, 1, 2, 3, 4
```

**How For Loops Work (Under the Hood):**
1. Takes an iterable
2. Creates an iterator object using `iter()`
3. Calls `next()` repeatedly until `StopIteration` error is raised

---

### Working with Iterators Manually

**Creating and Using Iterators:**
```python
# Create an iterable (list)
avengers = ['Iron Man', 'Thor', 'Hulk']

# Create an iterator from the iterable
avengers_iter = iter(avengers)

# Get values one by one
print(next(avengers_iter))  # Output: Iron Man
print(next(avengers_iter))  # Output: Thor
print(next(avengers_iter))  # Output: Hulk
# next(avengers_iter)  # Would raise StopIteration error
```

**Unpacking with the Splat Operator (*):**
```python
# Create iterator
avengers_iter = iter(avengers)

# Print all values at once
print(*avengers_iter)  # Output: Iron Man Thor Hulk

# WARNING: Iterator is now exhausted!
# print(*avengers_iter)  # Would print nothing

# Need to recreate iterator to use again
avengers_iter = iter(avengers)
```

---

### Iterating Over Special Objects

**Dictionaries:**
```python
superhero_powers = {
    'Iron Man': 'Technology',
    'Thor': 'Lightning',
    'Hulk': 'Strength'
}

# Iterate over key-value pairs
for hero, power in superhero_powers.items():
    print(f"{hero}: {power}")
```

**File Connections:**
```python
# Open a file connection
with open('file.txt', 'r') as file:
    # Create iterator
    file_iter = iter(file)
    
    # Get lines one by one
    print(next(file_iter))  # First line
    print(next(file_iter))  # Second line
```

---

### Using enumerate()

**Purpose:**
- Adds a counter/index to any iterable
- Returns a special enumerate object consisting of pairs (index, element)

**Basic Usage:**
```python
avengers = ['Iron Man', 'Thor', 'Hulk']

# Create enumerate object
e = enumerate(avengers)

# Convert to list to see contents
print(list(e))
# Output: [(0, 'Iron Man'), (1, 'Thor'), (2, 'Hulk')]
```

**Iterating with enumerate:**
```python
# Unpack index and value in for loop
for index, value in enumerate(avengers):
    print(f"{index}: {value}")

# Output:
# 0: Iron Man
# 1: Thor
# 2: Hulk
```

**Custom Starting Index:**
```python
# Start counting from 1 instead of 0
for index, value in enumerate(avengers, start=1):
    print(f"{index}: {value}")

# Output:
# 1: Iron Man
# 2: Thor
# 3: Hulk
```

---

### Using zip()

**Purpose:**
- Accepts an arbitrary number of iterables
- Returns an iterator of tuples
- Combines elements from multiple iterables

**Basic Usage:**
```python
avengers = ['Iron Man', 'Thor', 'Hulk']
names = ['Tony Stark', 'Thor Odinson', 'Bruce Banner']

# Create zip object
z = zip(avengers, names)

# Convert to list
print(list(z))
# Output: [('Iron Man', 'Tony Stark'), ('Thor', 'Thor Odinson'), ('Hulk', 'Bruce Banner')]
```

**Iterating with zip:**
```python
for hero, name in zip(avengers, names):
    print(f"{hero} is {name}")
```

**Using splat operator with zip:**
```python
z = zip(avengers, names)
print(*z)
# Output: ('Iron Man', 'Tony Stark') ('Thor', 'Thor Odinson') ('Hulk', 'Bruce Banner')
```

**Zipping multiple iterables:**
```python
powers = ['Technology', 'Lightning', 'Strength']
z = zip(avengers, names, powers)
print(list(z))
# Output: [('Iron Man', 'Tony Stark', 'Technology'), ...]
```

---

### Loading Large Files with Iterators

**The Challenge:**
- Dealing with datasets too large to fit in memory
- Need to process data without loading everything at once

**Solution - Loading Data in Chunks:**
1. Load data in chunks
2. Perform operations on each chunk
3. Store results
4. Discard the chunk
5. Load the next chunk

**Using pandas read_csv with chunksize:**

**Method 1 - Storing Results in a List:**
```python
import pandas as pd

# Initialize empty list for results
result = []

# Read CSV in chunks of 1000 rows
for chunk in pd.read_csv('large_file.csv', chunksize=1000):
    # Calculate sum of column 'x' for this chunk
    chunk_sum = chunk['x'].sum()
    
    # Append to results
    result.append(chunk_sum)

# Calculate total sum
total = sum(result)
print(f"Total sum: {total}")
```

**Method 2 - Running Total (More Memory Efficient):**
```python
import pandas as pd

# Initialize total to zero
total = 0

# Read CSV in chunks
for chunk in pd.read_csv('large_file.csv', chunksize=1000):
    # Add chunk sum to running total
    total += chunk['x'].sum()

print(f"Total sum: {total}")
```

**How It Works:**
- `pd.read_csv()` with `chunksize` parameter returns an iterable
- Each iteration yields a DataFrame containing the specified number of rows
- Only one chunk is held in memory at a time
- Ideal for processing files larger than available RAM
- Chunk size can be adjusted based on memory constraints

---

### 📖 Chapter 1 (Summary)

This chapter introduces the fundamentals of iterables and iterators in Python, essential tools in every Pythonista's toolbox.

**Core Concepts:**
Iterables are objects with an `iter()` method that creates iterators. Iterators are objects with a `next()` method that produces consecutive values. For loops work by automatically creating iterators from iterables and calling `next()` repeatedly until a `StopIteration` error occurs.

**Working with Iterators:**
You can manually create iterators using `iter()` and retrieve values using `next()`. The splat operator (*) unpacks all elements at once, but exhausts the iterator. Common iterables include lists, strings, range objects, dictionaries, and file connections. Dictionaries require the `items()` method to iterate over key-value pairs.

**Essential Functions:**
The `enumerate()` function adds a counter to any iterable, creating pairs of (index, element). It defaults to starting at 0 but can be customized with the `start` parameter. The `zip()` function combines multiple iterables into an iterator of tuples, allowing parallel iteration over multiple sequences.

**Practical Applications:**
Iterators excel at handling large datasets through chunked processing. Using pandas' `read_csv()` with the `chunksize` parameter allows processing files larger than available memory. Data is loaded in chunks, operations are performed on each chunk, results are stored, and chunks are discarded before loading the next one. This approach is memory-efficient and essential for big data workflows.

Understanding iterables and iterators enables you to write efficient, memory-conscious Python code and leverage Python's powerful iteration capabilities for data processing tasks of any scale.

## Generator Expressions and Comprehensions

### List Comprehensions

#### Basic List Comprehensions

**Problem:**
Creating a new list from an existing list with modifications

**Traditional Approach (For Loop):**
```python
# Initialize empty list
new_list = []

# Loop through old list
for num in nums:
    # Add 1 to each entry
    new_nums = num + 1
    # Append to new list
    new_list.append(new_nums)
```

**List Comprehension Approach:**
```python
# One line solution
new_nums = [num + 1 for num in nums]
```

**Syntax:**
- Use square brackets `[]`
- Output expression: `num + 1`
- For clause: `for num in nums`
- Format: `[output_expression for iterator_variable in iterable]`

---

#### For Loop vs List Comprehension

**For Loop Syntax:**
```python
for num in nums:
    new_nums.append(num + 1)
```

**List Comprehension Syntax:**
```python
new_nums = [num + 1 for num in nums]
```

**Advantages:**
- More efficient computationally
- Saves coding time and space
- Single line of code
- Works with any iterable, not just lists

---

#### List Comprehension with range()

**Example:**
```python
# Create list using range object
result = [num for num in range(11)]
# Output: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

---

#### Required Components

**List comprehensions require three components:**
1. An iterable
2. An iterator variable (represents members of the iterable)
3. An output expression

---

### Nested Loops in List Comprehensions

#### Nested For Loops (Traditional)

**Problem:**
Create list of all pairs where first integer is 0-1 and second is 6-7

**For Loop Approach:**
```python
pairs = []
for num1 in range(2):
    for num2 in range(6, 8):
        pairs.append((num1, num2))
# Output: [(0, 6), (0, 7), (1, 6), (1, 7)]
```

---

#### Nested List Comprehension

**List Comprehension Approach:**
```python
pairs = [(num1, num2) for num1 in range(2) for num2 in range(6, 8)]
# Output: [(0, 6), (0, 7), (1, 6), (1, 7)]
```

**Syntax:**
- Output expression followed by both for clauses
- Format: `[output for iterator1 in iterable1 for iterator2 in iterable2]`

**Tradeoff:**
- Single line of code
- May sacrifice readability
- Consider audience when using nested comprehensions
- Readability improves with practice

---

### Advanced Comprehensions

#### Conditionals in Comprehensions

**Filtering with Conditionals on Iterable:**
```python
# Square even numbers only
result = [num ** 2 for num in range(10) if num % 2 == 0]
# Output: [0, 4, 16, 36, 64]
```

**The Modulo Operator (%):**
- Produces remainder from division
- `num % 2 == 0` checks if number is even
- Returns True if integer is divisible by 2

---

#### Conditionals on Output Expression

**Using if-else in Output:**
```python
# Square if even, 0 if odd
result = [num ** 2 if num % 2 == 0 else 0 for num in range(10)]
# Output: [0, 0, 4, 0, 16, 0, 36, 0, 64, 0]
```

**Syntax:**
- Condition on iterable: `[output for item in iterable if condition]`
- Condition on output: `[output if condition else alternative for item in iterable]`

---

### Dictionary Comprehensions

#### Creating Dictionaries from Iterables

**Syntax:**
```python
# Basic dictionary comprehension
new_dict = {key_expression: value_expression for iterator in iterable}
```

**Example:**
```python
# Create dictionary with positive keys and negative values
pos_neg = {num: -num for num in range(10)}
# Output: {0: 0, 1: -1, 2: -2, 3: -3, ..., 9: -9}
```

**Key Differences from List Comprehensions:**
1. Use curly braces `{}` instead of square brackets `[]`
2. Key and value separated by colon `:` in output expression

---

### Generator Expressions

#### Introduction to Generators

**List Comprehension:**
```python
# Creates a list in memory
nums = [num * 2 for num in range(10)]
```

**Generator Expression:**
```python
# Creates a generator object
nums_gen = (num * 2 for num in range(10))
# Output: <generator object>
```

**Key Difference:**
- Replace square brackets `[]` with parentheses `()`
- Creates a generator object instead of a list

---

#### What is a Generator?

**Definition:**
- Like a list comprehension but doesn't store the list in memory
- Does not construct the list immediately
- An object you can iterate over to produce elements as required
- Uses lazy evaluation (evaluation delayed until value is needed)

**Benefits:**
- Memory efficient for large sequences
- Generates elements on-the-fly
- Doesn't store entire list in memory

---

#### Using Generators

**Iterating with For Loop:**
```python
nums_gen = (num * 2 for num in range(10))

# Loop produces elements
for num in nums_gen:
    print(num)
```

**Converting to List:**
```python
nums_gen = (num * 2 for num in range(10))
nums_list = list(nums_gen)
```

**Using next():**
```python
nums_gen = (num * 2 for num in range(10))

print(next(nums_gen))  # First value
print(next(nums_gen))  # Second value
print(next(nums_gen))  # Third value
```

---

#### Generators vs List Comprehensions

**Problem with Large Lists:**
```python
# DON'T DO THIS - Will crash!
# Trying to create massive list in memory
huge_list = [num for num in range(10**1000000)]
# Result: Memory error, server disconnection
```

**Solution with Generators:**
```python
# This works fine - no memory issue
huge_gen = (num for num in range(10**1000000))
# Result: Generator object created successfully
```

**Why Generators Work:**
- Doesn't create entire list in memory
- Only generates values when needed
- Perfect for very large sequences

---

#### Conditionals in Generator Expressions

**Filtering with Generators:**
```python
# Generator with conditional
even_gen = (num for num in range(20) if num % 2 == 0)

# Use in for loop
for num in even_gen:
    print(num)
```

**Capabilities:**
- All list comprehension features work in generators
- Filtering with conditionals
- Nested loops
- Output expression conditionals

---

### Generator Functions

#### Creating Generator Functions

**Definition:**
- Functions that produce generator objects when called
- Use `yield` keyword instead of `return`
- Yield sequences of values

**Basic Syntax:**
```python
def generator_function(n):
    # Function body using yield
    yield value
```

---

#### Building a Generator Function

**Example:**
```python
def num_sequence(n):
    """Generate values from 0 through n"""
    i = 0
    while i <= n:
        yield i
        i += 1
```

**How It Works:**
1. Initialize `i` to 0
2. First call yields `i = 0`
3. Adds 1 to `i`
4. Yields 1 on next iteration
5. Continues until `i == n`
6. Generator stops yielding values

---

#### Using Generator Functions

**Calling the Generator Function:**
```python
# Call function with argument
result = num_sequence(5)
print(result)
# Output: <generator object>
```

**Iterating Over Generator:**
```python
# Use in for loop
for num in num_sequence(5):
    print(num)
# Output: 0, 1, 2, 3, 4, 5
```

**Benefits:**
- Powerful and customizable way to create generators
- Can include complex logic
- Memory efficient
- Flexible control over value generation

---

### 📖 Chapter 2 (Summary)

This chapter covers list comprehensions, advanced comprehensions, and generator expressions in Python.

**List Comprehensions:**
List comprehensions collapse for loops into a single line of code for building lists. They require three components: an iterable, an iterator variable, and an output expression. The syntax uses square brackets with the format `[output for iterator in iterable]`. List comprehensions work with any iterable, not just lists, and can replace nested for loops, though this may sacrifice readability.

**Advanced Comprehensions:**
Conditionals can filter comprehensions on the iterable (`if num % 2 == 0`) or modify the output expression (`num ** 2 if condition else 0`). Dictionary comprehensions use curly braces and separate keys from values with colons: `{key: value for iterator in iterable}`. The modulo operator (%) helps filter even/odd numbers by checking if remainders equal zero.

**Generator Expressions:**
Generators are created by replacing square brackets with parentheses. Unlike list comprehensions that store entire lists in memory, generators use lazy evaluation to produce elements only when needed. They're essential for large sequences that can't fit in memory. Generators can be iterated with for loops, converted to lists with `list()`, or accessed with `next()`.

**Generator Functions:**
Generator functions use the `yield` keyword instead of `return` to produce sequences of values. When called, they return generator objects that can be iterated over. Generator functions provide a powerful, customizable, and memory-efficient way to create generators with complex logic. They're ideal for processing large datasets or infinite sequences without consuming memory.
