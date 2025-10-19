# Data Types in Python

## Data Types and Container Sequences

### Introduction to Data Types

#### Importance of Data Types
- **Instructor:** Jason Myers, Author and Open Source Maintainer
- **Focus:** Understanding fundamental data types empowers data scientists
- Data type system sets the stage for language capabilities
- Foundation for data storage, manipulation, and processing

---

### Container Sequences

#### What Are Container Sequences?

**Definition:**
- Hold a sequence of elements of other data types
- Named for their ability to contain sequences

**Common Uses in Data Science:**
- Store data for aggregation
- Maintain order
- Enable sorting
- Facilitate data processing

**Types of Container Sequences:**
- Lists
- Sets
- Tuples

---

#### Key Properties

**Mutability:**
- Mutable: Can have elements added and removed
- Immutable: Cannot be altered after creation
- Protects reference data
- Allows replacing individual data points with calculations (sums, averages, derivations)

**Iteration (Looping):**
- Ability to loop over contained data
- Enables data grouping
- Facilitates aggregation
- Supports processing over time

---

### Lists

#### List Fundamentals

**Purpose:**
- Hold ordered collection of items
- Maintain specific sequence

**Key Features:**
- Mutable (can add or remove data)
- Indexable (access individual elements using index)
- Ordered
- Allow duplicate elements

---

#### Creating and Modifying Lists

**Creating a List:**
```python
# Create list of cookies
cookies = ['chocolate chip', 'oatmeal', 'sugar']
```

**Adding Elements:**
```python
# Append single item
cookies.append('peanut butter')
print(cookies)
# Output: ['chocolate chip', 'oatmeal', 'sugar', 'peanut butter']
```

---

#### Accessing List Elements

**Using Index:**
```python
# Access third cookie (index 2, since indexing starts at 0)
print(cookies[2])
# Output: 'sugar'
```

**Important:**
- Indexes start at 0
- First element is at index 0
- Third element is at index 2

---

#### Combining Lists

**Using the Plus Operator (+):**
```python
cookies = ['chocolate chip', 'oatmeal']
cakes = ['red velvet', 'chocolate']

# Add lists together - returns new list
desserts = cookies + cakes
# Output: ['chocolate chip', 'oatmeal', 'red velvet', 'chocolate']
```

**Using extend() Method:**
```python
# Extend list by appending all values from second list
cookies.extend(cakes)
# Modifies cookies list in place
```

---

#### Finding Elements

**Using index() Method:**
```python
# Find index of specific value
cookies = ['chocolate chip', 'sugar', 'oatmeal']
position = cookies.index('sugar')
print(position)
# Output: 1
```

---

#### Removing Elements

**Using pop() Method:**
```python
# Remove element at specific index
cookies = ['chocolate chip', 'sugar', 'oatmeal']

# Find index of sugar cookie
idx = cookies.index('sugar')

# Remove and return the element
removed_cookie = cookies.pop(idx)

print(removed_cookie)
# Output: 'sugar'

print(cookies)
# Output: ['chocolate chip', 'oatmeal']
```

---

#### Iterating Over Lists

**Using List Comprehension:**
```python
cookies = ['chocolate chip', 'sugar', 'oatmeal']

# Print each cookie in title case
for cookie in [cookie.title() for cookie in cookies]:
    print(cookie)

# Output:
# Chocolate Chip
# Sugar
# Oatmeal
```

---

#### Sorting Lists

**Using sorted() Function:**
```python
cookies = ['chocolate chip', 'sugar', 'oatmeal']

# Sort list alphabetically - returns new list
sorted_cookies = sorted(cookies)
print(sorted_cookies)
# Output: ['chocolate chip', 'oatmeal', 'sugar']
```

**Function Details:**
- Accepts any iterable (like a list)
- Returns new list with elements in proper order
- Does not modify original list

---

### Tuples

#### Introduction to Tuples

**What Are Tuples?**
- Container type similar to lists
- Widely used internally by systems like databases
- Hold data in order
- Access elements with index

**Key Differences from Lists:**
- More memory efficient
- Easier to process
- Immutable (cannot add or remove elements)
- Ensures data is not altered
- Created by pairing up elements

---

#### Tuple Characteristics

**Similarities to Lists:**
- Hold data in order
- Can access elements using index

**Unique Features:**
- Immutable (powerful for data protection)
- Support unpacking (expand into named variables)
- Use parentheses `()` as object representation
- More efficient than lists

---

#### Creating Tuples with zip()

**Using zip() Function:**
```python
# Lists of top cookies by country
us_cookies = ['chocolate chip', 'peanut butter', 'sugar']
in_cookies = ['coconut', 'butter', 'chocolate']

# Create pairs using zip
top_pairs = list(zip(us_cookies, in_cookies))
print(top_pairs)
# Output: [('chocolate chip', 'coconut'), ('peanut butter', 'butter'), ('sugar', 'chocolate')]
```

**How zip() Works:**
- Matches up elements from multiple lists into pairs
- Creates iterator of tuples
- Pairs elements by position (rank)

---

#### Unpacking Tuples

**Basic Tuple Unpacking:**
```python
# Tuple with top ranked cookies
top_pair = ('chocolate chip', 'coconut')

# Unpack into named variables
us_num_1, in_num_1 = top_pair

print(us_num_1)
# Output: 'chocolate chip'

print(in_num_1)
# Output: 'coconut'
```

**Benefits:**
- Also called tuple expansion
- Assigns tuple elements to named variables
- Creates more readable code
- Less error-prone
- Variables separated by comma in assignment

---

#### Unpacking in Loops

**Using Tuple Unpacking in For Loops:**
```python
top_pairs = [('chocolate chip', 'coconut'), ('peanut butter', 'butter')]

# Unpack tuples while iterating
for us_cookie, in_cookie in top_pairs:
    print(f"US: {us_cookie}, India: {in_cookie}")

# Output:
# US: chocolate chip, India: coconut
# US: peanut butter, India: butter
```

**How It Works:**
- Splits each tuple into its elements during iteration
- Elements assigned to separate variables
- Can use variables inside loop body

---

#### Enumerating with Tuples

**Using enumerate() Function:**
```python
cookies = ['chocolate chip', 'oatmeal', 'sugar']

# Enumerate creates tuples of (index, element)
for idx, cookie in enumerate(cookies):
    print(f"{idx}: {cookie}")

# Output:
# 0: chocolate chip
# 1: oatmeal
# 2: sugar
```

**Advanced Unpacking:**
```python
top_pairs = [('chocolate chip', 'coconut'), ('peanut butter', 'butter')]

# Unpack both enumerate tuple and item tuple
for idx, (us_cookie, in_cookie) in enumerate(top_pairs):
    print(f"Rank {idx}: US={us_cookie}, India={in_cookie}")
```

**Benefits:**
- Track rankings in data
- Skip elements not interested in
- Know index position while iterating
- First element is index, second is the element itself

---

#### Creating Tuples Safely

**Proper Ways to Create Tuples:**
```python
# Using zip
pairs = list(zip(list1, list2))

# Using enumerate
enumerated = list(enumerate(items))

# Using parentheses
my_tuple = ('item1', 'item2')
```

**Warning - Accidental Tuples:**
```python
# The comma creates the tuple, not parentheses!
accidental_tuple = 'item',  # This creates a tuple!

# Can cause undesirable side effects
# Be careful with trailing commas
```

**Important:**
- The comma is the real magic for creating tuples
- Parentheses are just for clarity
- Accidentally ending a line with comma creates tuple
- Can cause unexpected behavior later in code

---

### Strings

#### String Fundamentals

**String as Sequence Type:**
- Most common type encountered
- Can loop over like other sequence types
- Unique construction and manipulation methods

---

#### Formatted Strings (f-strings)

**Creating f-strings:**
```python
# Variables
cookie_name = 'Anzac'
cookie_price = '$1.99'

# f-string with expressions in curly braces
message = f"Each {cookie_name} cookie costs {cookie_price}"
print(message)
# Output: "Each Anzac cookie costs $1.99"
```

**Syntax:**
- Place `f` in front of opening quote
- Use Python expressions wrapped in `{}` inside string
- Short for "formatted string literals"
- Letter in front of quote indicates string type

---

#### Joining Strings

**Using join() Method:**
```python
child_ages = ['3', '4', '7', '8']

# Join with comma
ages_string = ', '.join(child_ages)
print(ages_string)
# Output: "3, 4, 7, 8"
```

**Combining join() with f-strings:**
```python
child_ages = ['3', '4', '7', '8']

# Advanced formatting
message = f"The children are ages {', '.join(child_ages[0:3])}, and {child_ages[-1]}"
print(message)
# Output: "The children are ages 3, 4, 7, and 8"
```

**How It Works:**
- Call join() method on the separator string
- Pass iterable (like list) as argument
- Combines elements with separator between them

---

#### Finding Patterns in Strings

**Using startswith() and endswith():**
```python
boy_names = ['Mohamed', 'Youssef', 'Ahmed']

# Find names starting with 'A'
a_names = [name for name in boy_names if name.startswith('A')]
print(a_names)
# Output: ['Ahmed']
```

**Important:**
- Methods are case-sensitive
- Must match exact case of first/last letters

---

#### Searching in Strings

**Using in Operator:**
```python
quote = "Life is a long lesson in humility."

# Search for substring (case-sensitive)
print("long" in quote)
# Output: True

print("life" in quote)
# Output: False (capital 'L' in original)
```

**Behavior:**
- Searches for value inside string
- Case-sensitive by default
- Returns True or False

---

#### Case-Insensitive Searching

**Using lower() Method:**
```python
quote = "Life is a long lesson in humility."

# Convert to lowercase before searching
print("life" in quote.lower())
# Output: True
```

**Common Pattern:**
- Use lower() method on string before searching
- Makes search case-insensitive
- Converts entire string to lowercase

---

### 📖 Chapter 1 (Summary)

This chapter introduces Python's fundamental data types and container sequences essential for data science.

**Container Sequences:**
Container sequences hold ordered collections of elements from other data types. Python provides lists, sets, and tuples for storing data. Mutability determines whether elements can be added or removed, while immutability protects reference data. All container sequences support iteration, enabling data grouping, aggregation, and processing over time.

**Lists:**
Lists are mutable, ordered collections that allow duplicate elements. Create lists with square brackets, add elements with append(), and combine lists using the + operator or extend() method. Access elements using zero-based indexing. Find element positions with index(), remove elements with pop(), and sort with the sorted() function. List comprehensions provide efficient iteration for transforming list data.

**Tuples:**
Tuples are immutable, ordered containers more memory-efficient than lists. Create tuples using zip() to pair elements from multiple lists or enumerate() to add index numbers. Tuple unpacking assigns elements to named variables, improving code readability. The comma, not parentheses, creates tuples—watch for accidental trailing commas. Unpacking works in loops and with enumerate() for tracking positions while iterating.

**Strings:**
Strings are sequence types with unique features. F-strings (formatted string literals) embed Python expressions in curly braces by placing 'f' before the opening quote. The join() method combines iterable elements using the string as separator. Search for patterns with startswith() and endswith() methods or the in operator. All string searches are case-sensitive by default; use lower() method for case-insensitive searches.

Understanding these data types enables efficient data storage, manipulation, and processing in Python data science workflows.


## Dictionaries

### Introduction to Dictionaries

#### Why Dictionaries Matter

**Common Usage:**
- Most commonly used container type
- "Everything in Python is a dictionary" (popular joke with some truth)

**Primary Use Cases:**
- Storing key/value pairs
- Grouping data by time
- Structuring hierarchical data (like org charts)
- Quick lookups without scanning entire lists

---

### Creating and Using Dictionaries

#### Dictionary Fundamentals

**Key Features:**
- Hold data in key/value pairs
- Keys must be alphanumeric
- Values can be any data type
- Support nesting (dictionaries within dictionaries)
- Can iterate over keys, values, or items

---

#### Creating Dictionaries

**Two Methods:**

**Using dict() Method:**
```python
# Create empty dictionary
art_galleries = dict()
```

**Using Braces Shortcut:**
```python
# Create empty dictionary
art_galleries = {}
```

---

#### Building Dictionaries from Data

**Example with List of Tuples:**
```python
# List of (name, zip) tuples
galleries = [
    ('Gallery A', '10001'),
    ('Gallery B', '10002'),
    ('Gallery C', '10003')
]

# Create empty dictionary
art_galleries = {}

# Loop with tuple unpacking
for name, zipcode in galleries:
    # Set name as key, zipcode as value
    art_galleries[name] = zipcode
```

---

#### Iterating Over Dictionaries

**Default Iteration (Keys):**
```python
# By default, loops iterate over keys
for gallery in art_galleries:
    print(gallery)  # Prints gallery names
```

**Printing Last 5 Keys:**
```python
# sorted() on dictionary returns sorted keys
for gallery in sorted(art_galleries)[-5:]:
    print(gallery)
```

**Important:**
- Looping over dictionary loops over keys by default
- Using sorted() on dictionary sorts keys

---

### Accessing Dictionary Values

#### Unsafe Access (Using Key as Index)

**Direct Key Access:**
```python
# If key exists
zipcode = art_galleries['Gallery A']
# Returns: '10001'

# If key doesn't exist
zipcode = art_galleries['Louvre']
# Throws KeyError exception - stops code execution!
```

**Problem:**
- Throws ugly exception if key not present
- Stops program execution
- Not safe for uncertain keys

---

#### Safe Access (Using get() Method)

**Basic get() Method:**
```python
# Returns None if key not found
zipcode = art_galleries.get('Louvre')
print(zipcode)
# Output: None
```

**get() with Default Value:**
```python
# Returns custom value if key not found
zipcode = art_galleries.get('Louvre', 'Not Found')
print(zipcode)
# Output: 'Not Found'

# Valid key returns actual value
zipcode = art_galleries.get('Gallery A', 'Not Found')
print(zipcode)
# Output: '10001'
```

**Syntax:**
- First argument: key to search for
- Second argument (optional): value to return if key not found
- Returns None by default if key not found

---

### Altering Dictionaries

#### Adding Data to Dictionaries

**Adding Single Item:**
```python
# Use new key as index and assign value
art_galleries['Gallery D'] = '10004'
```

**Adding Nested Dictionary:**
```python
# Dictionary of galleries in zip code 10007
zip_10007 = {
    'Gallery E': '555-1234',
    'Gallery F': '555-5678'
}

# Add as nested dictionary
art_galleries['10007'] = zip_10007
```

---

#### Using update() Method

**What update() Accepts:**
- Another dictionary
- List of tuples
- Keyword arguments

**Example with List of Tuples:**
```python
# Create list of tuples
new_galleries = [
    ('Gallery G', '555-9999'),
    ('Gallery H', '555-8888')
]

# Update nested dictionary at specific zip code
art_galleries['10007'].update(new_galleries)

# Print to verify
print(art_galleries['10007'])
# Shows nested dictionary with new entries
```

---

#### Removing Data from Dictionaries

**Using del Instruction:**
```python
# Remove key from dictionary
del art_galleries['11234']

# WARNING: Throws KeyError if key doesn't exist!
```

**Using pop() Method (Safe):**
```python
# Safely remove and return value
# If key doesn't exist, returns None (or provided default)
popped_value = art_galleries.pop('10310', None)

print(popped_value)
# Returns value if key exists, None otherwise
```

**Comparison:**
- `del`: Throws KeyError if key missing
- `pop()`: Safe, returns default value if key missing

---

### Pythonic Dictionary Usage

#### Iterating Over Items

**Non-Pythonic Way:**
```python
# Loop through keys, then access values
for gallery in art_galleries:
    zipcode = art_galleries[gallery]
    print(gallery, zipcode)
```

**Pythonic Way with items():**
```python
# items() returns dict_items object
# Can iterate as list of key/value tuples
for name, phone in art_galleries.items():
    print(name, phone)
```

**How items() Works:**
- Returns dict_items object
- Iterate as list of (key, value) tuples
- Use tuple unpacking to separate key and value

---

#### Checking for Keys

**Using get() Method:**
```python
# Check if key exists by testing for None
result = art_galleries.get('11234')
if result is not None:
    print("Found!")
```

**Pythonic Way with in Operator:**
```python
# Check if key exists - returns boolean
if '11234' in art_galleries:
    print("Found!")
else:
    print("Not found!")

# Output: Not found! (if key was deleted earlier)
```

**Using in Conditionals:**
```python
# Common pattern in if/else statements
if '10010' in art_galleries:
    value = art_galleries['10010']
    print(f"Found: {value}")
```

**Benefits:**
- Returns True or False (boolean)
- More readable
- Commonly used in conditional statements
- More efficient than get() for existence checks

---

### Working with Nested Dictionaries

#### Creating Nested Structure

**Hierarchical Organization:**
```python
# Dictionary organized by zip code, then gallery name
art_galleries = {
    '10001': {
        'Gallery A': '555-1111',
        'Gallery B': '555-2222'
    },
    '10002': {
        'Gallery C': '555-3333',
        'Gallery D': '555-4444'
    }
}
```

**Purpose:**
- Group data (by zip code, time period, etc.)
- Establish hierarchy (org charts, reporting structures)
- Handle repeating data structures

---

#### Accessing Nested Data

**View Top-Level Keys:**
```python
# Get list of zip code keys
zipcodes = art_galleries.keys()
print(zipcodes)
```

**Access Nested Dictionary:**
```python
# Print entire nested dictionary
print(art_galleries['10001'])
# Output: {'Gallery A': '555-1111', 'Gallery B': '555-2222'}
```

**Access Nested Value:**
```python
# Use multiple indices to access nested value
phone = art_galleries['10001']['Gallery A']
print(phone)
# Output: '555-1111'
```

**Using get() with Nested Dictionaries:**
```python
# Safe access to nested data
zip_dict = art_galleries.get('10001', {})
phone = zip_dict.get('Gallery A', 'Not Found')
```

**Common Use Cases:**
- Yearly data organization
- Grouped data structures
- Hierarchical relationships
- Organization reporting structures

---

### 📖 Chapter 2 (Summary)

This chapter covers dictionaries, Python's most commonly used container type for storing and organizing data.

**Dictionary Fundamentals:**
Dictionaries store data in key/value pairs where keys must be alphanumeric but values can be any data type. Create dictionaries using dict() method or braces {}. Dictionaries support nesting for hierarchical data and grouping. By default, iterating over a dictionary loops over its keys. The items() method returns key/value tuples for more efficient iteration using tuple unpacking.

**Accessing and Safety:**
Direct key access using brackets throws KeyError exceptions if keys don't exist, stopping program execution. The get() method provides safe access, returning None by default or a custom value if the key is missing. The in operator offers the most Pythonic way to check key existence, returning a boolean value commonly used in conditional statements.

**Modifying Dictionaries:**
Add data by assigning values to new keys or using the update() method with dictionaries, lists of tuples, or keyword arguments. Remove data using del (throws KeyError if key missing) or pop() method (safe, returns default value). Dictionaries are mutable, allowing constant addition and removal of data during processing.

**Nested Dictionaries:**
Nesting dictionaries enables working with grouped or hierarchical data like yearly information or org charts. Access nested values using multiple indices (dict[key1][key2]) or chaining get() methods for safe access. The keys() method shows top-level keys, while nested structures organize repeating data patterns efficiently.

Understanding dictionaries is critical for data science tasks involving quick lookups, data grouping, and hierarchical organization without scanning entire datasets.


## Numeric Data Types and Advanced Data Structures

### Numeric Data Types

#### Built-in Numeric Types

**Integers (int):**
- Whole numbers
- Great for substantial values
- No decimal points

**Floats:**
- Hold fractional amounts
- Approximations acceptable
- Support scientific notation

---

#### Decimals

**Purpose:**
- Exacting precision required
- Currency operations
- Avoid floating-point errors

**Using Decimals:**
```python
# Import from decimal module
from decimal import Decimal

# Create Decimal
amount = Decimal('0.00001')
print(amount)
# Output: 0.00001 (not scientific notation)
```

**Important:**
- Must import from decimal module
- Doesn't convert to scientific notation
- More precise than floats

---

#### Printing Floats

**Scientific Notation Problem:**
```python
# Small float prints as scientific notation
print(0.00001)
# Output: 1e-05
```

**Using f-strings with Format Specifiers:**
```python
# Basic float format specifier (f)
print(f"{0.00001:f}")
# Output: 0.000010
```

**Precision Control:**
```python
# Default stops at 6 decimal places
print(f"{0.0000001:f}")
# Output: 0.000000 (unexpected!)

# Specify precision with .Xf where X is number of decimals
print(f"{0.0000001:.7f}")
# Output: 0.0000001
```

**Syntax:**
- Follow variable with colon and format specifier
- `f` for float format
- `.Xf` for X decimal places precision

---

#### Python Division Types

**Float Division (Single Slash):**
```python
# Returns float result
result = 4 / 2
print(result)
# Output: 2.0

result = 7 / 3
print(result)
# Output: 2.333...
```

**Floor Division (Double Slash):**
```python
# Floors the result (rounds down)
result = 4 // 2
print(result)
# Output: 2 (integer)

result = 7 // 3
print(result)
# Output: 2 (floors 2.333... to 2)
```

**Difference:**
- `/` : Returns float result
- `//` : Floors result to integer

---

### Booleans

#### Booleans as Data Type

**Two Values:**
- `True`
- `False`

**Characteristics:**
- Work like on-off switch
- Complete opposites
- **IMPORTANT:** Capitalized in Python (unlike some languages)

**Basic Usage:**
```python
# Set boolean value
need_cookies = True

# Use in conditional
if need_cookies:
    print("Going to get more cookies!")
```

---

#### Truthy and Falsey Values

**Definition:**
- **Truthy:** Values that evaluate to True in boolean context
- **Falsey:** Values that evaluate to False in boolean context

**Boolean Context Examples:**
- If statements
- While loops
- Logical operations

**Examples:**
```python
# Integer 2 is truthy
apples = 2
if apples:
    print("Have apples!")  # This prints

# Integer 0 is falsey
apples = 0
if apples:
    print("Have apples!")  # This doesn't print
```

---

#### Truthy and Falsey Rules

**Numeric Types:**
```python
# Any non-zero number is truthy
if 2: print("Truthy")
if -1: print("Truthy")
if 3.14: print("Truthy")

# Zero is falsey
if 0: print("Won't print")
if 0.0: print("Won't print")
```

**Strings:**
```python
# Non-empty strings are truthy
if "hello": print("Truthy")
if "x": print("Truthy")

# Empty string is falsey
if "": print("Won't print")
```

**Lists and Dictionaries:**
```python
# Non-empty is truthy
if [1, 2, 3]: print("Truthy")
if {'a': 1}: print("Truthy")

# Empty is falsey
if []: print("Won't print")
if {}: print("Won't print")
```

**None:**
```python
# None is always falsey
if None: print("Won't print")
```

**General Rule:**
- Something is truthy if it's not empty of value
- Empty or zero values are falsey

---

#### Boolean Operators

**Comparison Operators:**
```python
cookie_qty = 3

# Equality
cookie_qty == 3  # True
cookie_qty == 5  # False

# Not equal
cookie_qty != 5  # True

# Less than
cookie_qty < 5   # True

# Less than or equal
cookie_qty <= 3  # True

# Greater than
cookie_qty > 2   # True

# Greater than or equal
cookie_qty >= 3  # True
```

**Available Operators:**
- `==` : Equal to
- `!=` : Not equal to
- `<`  : Less than
- `<=` : Less than or equal to
- `>`  : Greater than
- `>=` : Greater than or equal to

---

#### Float Comparison Issues

**The Problem:**
```python
# Expected: True
result = (0.1 + 1.1) == 1.2
print(result)
# Output: False

# Why?
print(0.1 + 1.1)
# Output: 1.2000000000000002
```

**Explanation:**
- Floats stored internally with less precision
- Approximations cause unexpected results
- Equality comparisons can fail
- Solutions involve rounding and absolute values

**Remember:**
- Floats are suitable for approximations
- Be careful with equality comparisons
- Use Decimal for precise calculations

---

### Sets

#### Introduction to Sets

**Purpose:**
- Find unique values in data columns
- Store unique elements from lists
- Find unique rows from files
- Optimized for logic operations

**Key Characteristics:**
- Store unique data elements only
- Unordered (no specific sequence)
- Mutable (can add/remove elements)
- Based on set theory from mathematics

---

#### Creating Sets

**From Lists:**
```python
# List with duplicates
cookies_today = [
    'chocolate chip',
    'oatmeal',
    'chocolate chip',
    'sugar',
    'chocolate chip'
]

# Create set (removes duplicates)
unique_cookies = set(cookies_today)
print(unique_cookies)
# Output: {'chocolate chip', 'oatmeal', 'sugar'}
```

**Important:**
- Sets only store unique items
- Duplicates automatically removed
- Created from lists using set() constructor

---

#### Modifying Sets

**Adding Single Element:**
```python
# Add new element
unique_cookies.add('biscotti')
unique_cookies.add('chocolate chip')  # Already exists, no change

print(unique_cookies)
# Output: {'chocolate chip', 'oatmeal', 'sugar', 'biscotti'}
```

**Behavior:**
- Only adds if element is unique
- Ignores if element already exists
- No error thrown for duplicates

---

#### Updating Sets

**Adding Multiple Items:**
```python
# Hugo's cookies
hugo_cookies = ['snickerdoodle', 'ginger snap']

# Add multiple items at once
unique_cookies.update(hugo_cookies)

print(unique_cookies)
# Includes both original and Hugo's cookies
```

**How update() Works:**
- Takes list of items
- Adds each unique item to set
- Skips items already present

---

#### Removing Elements from Sets

**Using discard() Method (Safe):**
```python
# Remove element by value - no error if not found
unique_cookies.discard('biscotti')
print(unique_cookies)
# biscotti removed from set
```

**Using pop() Method:**
```python
# Remove and return arbitrary element
cookie1 = unique_cookies.pop()
cookie2 = unique_cookies.pop()

print(cookie1, cookie2)
# Two random cookies removed and returned
```

**Comparison:**
- `discard()`: Safe, no error if element missing
- `pop()`: Removes arbitrary (random) element

---

### Set Operations

#### Finding Similarities

**Union Method:**
```python
# Create two sets
my_cookies = {'chocolate chip', 'oatmeal', 'sugar'}
hugo_cookies = {'snickerdoodle', 'oatmeal', 'ginger snap'}

# Get all unique elements from both sets
all_cookies = my_cookies.union(hugo_cookies)
print(all_cookies)
# Output: {'chocolate chip', 'oatmeal', 'sugar', 'snickerdoodle', 'ginger snap'}
```

**Intersection Method:**
```python
# Find overlapping elements in both sets
common_cookies = my_cookies.intersection(hugo_cookies)
print(common_cookies)
# Output: {'oatmeal'}
```

**Use Cases:**
- Union: Combine all unique items
- Intersection: Find commonalities (e.g., year-over-year comparisons)

---

#### Finding Differences

**Difference Method:**
```python
my_cookies = {'chocolate chip', 'oatmeal', 'sugar'}
hugo_cookies = {'snickerdoodle', 'oatmeal', 'ginger snap'}

# Find cookies I ate that Hugo didn't
my_unique = my_cookies.difference(hugo_cookies)
print(my_unique)
# Output: {'chocolate chip', 'sugar'}

# Find cookies Hugo ate that I didn't
hugo_unique = hugo_cookies.difference(my_cookies)
print(hugo_unique)
# Output: {'snickerdoodle', 'ginger snap'}
```

**Important:**
- Target set matters (basis for differences)
- Returns elements in first set not in second set
- Order of operation changes result

---

### 📖 Chapter 3 (Summary)

This chapter covers numeric data types, booleans, and sets for efficient data manipulation.

**Numeric Types:**
Python provides integers for whole numbers, floats for fractional amounts with approximations, and Decimals for exact precision in currency operations. Import Decimals from the decimal module to avoid scientific notation. Use f-string format specifiers to control float output—bare `f` shows 6 decimal places, while `.Xf` specifies X decimals. Python supports two division types: single slash `/` for float division and double slash `//` for floor division that rounds down.

**Booleans and Truth Values:**
Booleans have two capitalized values: True and False. All Python values are truthy or falsey in boolean contexts like if statements. Non-zero numbers, non-empty strings, non-empty lists/dictionaries are truthy. Zero, empty strings, empty containers, and None are falsey. Comparison operators (==, !=, <, <=, >, >=) return boolean values. Float equality comparisons can fail due to internal storage imprecision—floats approximate values.

**Sets:**
Sets store unique, unordered elements and are mutable. Create sets from lists using set() constructor, which automatically removes duplicates. Add single elements with add() method, multiple elements with update() method. Remove elements safely with discard() (no error if missing) or pop() (removes arbitrary element). Sets excel at comparison operations.

**Set Operations:**
Union method returns all unique elements from both sets. Intersection finds overlapping elements present in both sets. Difference method finds elements in one set not in another—the target set matters. These operations align with mathematical set theory and enable efficient data comparisons, making sets ideal for finding unique values and analyzing differences between datasets.


## Advanced Data Containers

### The Collections Module

#### Introduction

**Purpose:**
- Part of Python standard library
- Provides advanced data containers
- Solves common data science problems

**Common Use Cases:**
- Counting items
- Creating dictionaries with unknown keys
- Structuring complex types
- Handling data before knowing structure

---

### Counter

#### What is Counter?

**Definition:**
- Powerful object based on dictionary
- Accepts a list
- Counts occurrences of each value
- Supports all normal dictionary features

---

#### Creating and Using Counter

**Basic Usage:**
```python
from collections import Counter

# List of eatery types from NYC parks data
nyc_eatery_types = [
    'Restaurant',
    'Snack Bar',
    'Restaurant',
    'Cafe',
    'Restaurant',
    'Snack Bar'
]

# Create Counter
type_counts = Counter(nyc_eatery_types)
print(type_counts)
# Output: Counter({'Restaurant': 3, 'Snack Bar': 2, 'Cafe': 1})
```

**Accessing Counts:**
```python
# Use key as index (like dictionary)
restaurant_count = type_counts['Restaurant']
print(restaurant_count)
# Output: 3
```

---

#### Finding Most Common Items

**Using most_common() Method:**
```python
# Get top 3 most frequent items
top_3 = type_counts.most_common(3)
print(top_3)
# Output: [('Restaurant', 3), ('Snack Bar', 2), ('Cafe', 1)]
```

**How It Works:**
- Returns list of tuples
- Format: (item, count)
- Sorted in descending order by count
- Pass number of items to return

**Use Cases:**
- Frequency analytics
- Finding how often something occurs
- Common data science problem

---

### defaultdict

#### The Problem

**Traditional Dictionary Approach:**
```python
# Want to store list of eateries by park
eateries_by_park = {}

# Loop through data
for park_id, name in park_eateries:
    # Must check if key exists
    if park_id not in eateries_by_park:
        # Initialize empty list
        eateries_by_park[park_id] = []
    
    # Append to list
    eateries_by_park[park_id].append(name)
```

**Issues:**
- Must check if key exists
- Must initialize empty structure
- Repetitive code
- Error-prone

---

#### Using defaultdict

**What is defaultdict?**
- Accepts a type as default value
- Auto-creates default value if key not present
- Can override by setting key manually
- Simplifies code significantly

**Example with Lists:**
```python
from collections import defaultdict

# Create defaultdict that defaults to list
eateries_by_park = defaultdict(list)

# List of (park_id, eatery_name) tuples
park_eateries = [
    ('M010', 'Cafe A'),
    ('M010', 'Restaurant B'),
    ('M011', 'Snack Bar C')
]

# No need to check if key exists!
for park_id, name in park_eateries:
    eateries_by_park[park_id].append(name)

# Print eateries in Central Park (M010)
print(eateries_by_park['M010'])
# Output: ['Cafe A', 'Restaurant B']
```

---

#### defaultdict as Counter

**Using int as Default Type:**
```python
from collections import defaultdict

# Create defaultdict that defaults to int (0)
contact_counts = defaultdict(int)

# Count eateries with phone numbers and websites
for eatery in nyc_eateries:
    # Add 1 if phone exists (not None)
    if eatery['phone'] is not None:
        contact_counts['phones'] += 1
    
    # Add 1 if website exists
    if eatery['website'] is not None:
        contact_counts['websites'] += 1

print(contact_counts)
# Output: defaultdict(<class 'int'>, {'phones': 150, 'websites': 75})
```

**Use Cases:**
- Counting multiple keys from dictionaries
- Tracking different categories
- Accumulating counts without initialization

---

### namedtuple

#### Introduction to namedtuple

**What is namedtuple?**
- Tuple with names for each position
- Makes code more readable
- Easier to access data by name
- Alternative to dictionaries

**When to Use:**
- Don't need nested structure of dictionary
- Want items to look identical
- Don't want overhead of Pandas DataFrame
- Need named access to tuple elements

---

#### Creating namedtuple

**Basic Setup:**
```python
from collections import namedtuple

# Define namedtuple (use PascalCase convention)
Eatery = namedtuple('Eatery', ['name', 'park_id', 'location', 'phone'])
```

**Syntax:**
- First argument: name for tuple type
- Second argument: list of field names
- Convention: Use PascalCase (capitalize each word)

---

#### Creating Instances

**Building List of namedtuples:**
```python
# Create empty list
eateries_list = []

# Iterate over data
for eatery in nyc_eateries:
    # Create instance by passing data as arguments
    eatery_tuple = Eatery(
        name=eatery['name'],
        park_id=eatery['park_id'],
        location=eatery['location'],
        phone=eatery['phone']
    )
    eateries_list.append(eatery_tuple)

# Print first element
print(eateries_list[0])
# Output: Eatery(name='Cafe A', park_id='M010', location='Central Park', phone='555-1234')
```

---

#### Using namedtuples

**Accessing Fields as Attributes:**
```python
# Loop through first 3 eateries
for eatery in eateries_list[:3]:
    print(f"{eatery.name} in park {eatery.park_id} at {eatery.location}")
```

**Benefits:**
- Fields available as attributes
- Makes code clearer
- Safe access without get() method
- Every instance has all fields (may be None)
- More readable than numeric indices

**Attribute Definition:**
- Named field or data storage location
- Access using dot notation

---

### Dataclasses

#### Introduction to Dataclasses

**What are Dataclasses?**
- More powerful version of namedtuple
- Complex data representation
- Additional features beyond namedtuple

---

#### Benefits of Dataclasses

**Key Features:**
1. Set default values for fields
2. Nice default representation for print/log
3. Convert to dictionary or tuple easily
4. Create custom properties
5. Make frozen (immutable) instances
6. Preset fields on creation

**Note:** Python documentation provides even more benefits

---

#### Creating a Dataclass

**Basic Structure:**
```python
from dataclasses import dataclass

# Use @dataclass decorator
@dataclass
class Cookie:
    name: str
    quantity: int = 0  # Default value
```

**Syntax:**
- Import dataclass from dataclasses module
- Use `@` symbol with dataclass as decorator
- Decorator adds extra behaviors to class
- Define field names with types
- Optional: Set default values

---

#### Converting Dataclasses

**To Dictionary and Tuple:**
```python
from dataclasses import dataclass, asdict, astuple

@dataclass
class Cookie:
    name: str
    quantity: int = 0

# Create instance
ginger_molasses = Cookie(name='Ginger Molasses', quantity=12)

# Convert to dictionary
cookie_dict = asdict(ginger_molasses)
print(cookie_dict)
# Output: {'name': 'Ginger Molasses', 'quantity': 12}

# Convert to tuple
cookie_tuple = astuple(ginger_molasses)
print(cookie_tuple)
# Output: ('Ginger Molasses', 12)
```

**Functions Available:**
- `asdict()`: Converts to dictionary
- `astuple()`: Converts to tuple
- Import from dataclasses module

---

#### Custom Properties

**Creating Custom Properties:**
```python
from dataclasses import dataclass
from decimal import Decimal

@dataclass
class Cookie:
    name: str
    quantity: int = 0
    cost: Decimal = Decimal('0.00')
    
    # Custom property using @property decorator
    @property
    def value_of_goods(self):
        return self.cost * self.quantity
```

**How Custom Properties Work:**
- Use `@property` decorator (built-in Python)
- Method always receives `self` as argument
- Can perform operations on property values
- Returns result of operation

---

#### Using Custom Properties

**Accessing Custom Properties:**
```python
# Create instance
peanut_cookie = Cookie(
    name='Peanut Butter',
    quantity=10,
    cost=Decimal('2.50')
)

# Access custom property (no parentheses needed!)
total_value = peanut_cookie.value_of_goods
print(total_value)
# Output: 25.00
```

**Important:**
- Methods with `@property` decorator don't need parentheses
- Used like any other property
- Acts as calculated field

---

#### Frozen Instances

**Creating Frozen Dataclass:**
```python
from dataclasses import dataclass

# Pass frozen=True to decorator
@dataclass(frozen=True)
class Cookie:
    name: str
    quantity: int = 0

# Create instance
c = Cookie(name='Chocolate Chip', quantity=10)

# Try to modify (will raise error!)
c.quantity = 15
# Error: FrozenInstanceError: cannot assign to field 'quantity'
```

**Characteristics:**
- Cannot be edited after creation
- Pass `frozen=True` to dataclass decorator
- Attempting to modify raises error
- Ensures data immutability

---

### 📖 Chapter 4 (Summary)

This chapter covers advanced data containers from Python's collections module and dataclasses for efficient data handling.

**Counter and defaultdict:**
Counter, based on dictionaries, counts occurrences of values in lists and supports all dictionary features. The most_common() method returns tuples of items and counts in descending order, perfect for frequency analytics. The defaultdict accepts a default type, automatically creating default values for missing keys. Use list type for grouping items or int type for counting, eliminating manual key existence checks and initialization.

**namedtuple:**
Namedtuples are tuples with named positions, making code more readable than numeric indices. Create them by passing a tuple name and field list, using PascalCase convention. Access fields as attributes using dot notation. Every instance has all fields (possibly None), providing safe access without get() methods. Use namedtuples when you don't need nested dictionary structures or Pandas DataFrame overhead but want named data access.

**Dataclasses:**
Dataclasses are powerful namedtuple alternatives. Import and use the @dataclass decorator on class definitions. Set default values for fields and specify types. Convert instances to dictionaries with asdict() or tuples with astuple(). Create custom properties using @property decorator—these calculated fields don't need parentheses when accessed. Make frozen instances by passing frozen=True to the decorator, preventing any modifications after creation.

**Practical Applications:**
These containers solve common data science problems: Counter for frequency analysis, defaultdict for unknown dictionary structures, namedtuple for readable structured data, and dataclasses for complex data with validation and computed fields. Each offers specific advantages for different data organization and manipulation scenarios.
