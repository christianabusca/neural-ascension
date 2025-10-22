# Alteryx Designer: Data Cleaning and Preparation Notes

## Introduction to Data Cleaning

### Why is clean data important?

**GIGO Principle**:
- "Garbage In, Garbage Out"
- If your data has errors, your results may have errors too

**Benefits of clean data**:
- Avoid mistakes and help prevent errors
- Standardize datasets (formatting, naming conventions, guidelines)
- Increase productivity and speed to insight
- Streamline analytics and processes

### Cleaning your data is like...

**Car tune-up analogy**:
- Like tuning up your car
- Clean spark plugs and other parts make everything run smoother and faster
- Just like fixing "dirty data"

---

## Examples of Dirty Data

### Types of dirty data

**Missing or incomplete data**:
- Datasets may need cleaning before performing analyses

**Unstandardized or inconsistent data**:
- Formatting inconsistencies across dataset

**Data entry errors**:
- Errors that can be overlooked

**Leading and trailing whitespace**:
- Can cause issues with filtering and joining data

**Extra characters**:
- Currency signs on financial data
- Can prevent numeric formulas from being applied

---

## Clean Data Techniques

### Handling missing values

**Flagging missing data**:
- Impute blanks for null string data types
- Impute zeroes for null numeric data types
- Filter missing data

### Applying standards to dataset

**Formatting requirements**:
- Add dollar signs to currency fields
- Ensure IDs have leading zeros

**Naming conventions**:
- Append date to output filename
- Modify case type to Upper Case to enable case-sensitive joins

**Data types**:
- Play major role in analytics
- Convert string to numeric values easily in Alteryx

### Removing unneeded items

**Items to remove**:
- Leading and trailing whitespace
- Tabs and line breaks
- Entire rows and columns
- Punctuation and other characters

---

## Profile with Color-Coding

### Alteryx color coordination in Results window and Profile view

**Color meanings**:
- **Green**: "OK"
- **White**: Count of "Unique" records
- **Yellow**: "Null"
- **Red**: "Not OK"
- **Grey**: "Empty" values

---

## Data Types in Alteryx

### Five main categories of data types

**Boolean**:
- Binary format: zero or one, true or false
- Can be used to flag data

**Numeric**:
- **Integer**: Number without decimals
  - Integer 16, 32, and 64 (changes based on byte storage)
- **Fixed Decimal**: Numbers with specified precision
- **Double**: Double-precision floating point value
  - Good default for numeric data
  - Can hold various decimal positions

**String**:
- Ranges from String to V_W String types

**DateTime**:
- Dates, times, and combined datetime
- ISO standard format

**Spatial**:
- Spatial objects: points, lines, and polygons

---

## Dataset Details

### New York Property Sales dataset

**Dataset features**:
- Lists location, sale date, and sale amount
- Used in hands-on exercises throughout course

**Course goal**:
- Discover top 10 highest-selling properties

---

## Filtering Data

### What is filtering?

**Definition**:
- Process of reducing a dataset by removing some data
- Focus on subset of data based on specific criteria
- Example: "Sale Price is greater than or equal to $100,000"

### The concept of filtering is like...

**Sculpting analogy**:
- Like sculpting a statue
- Removing extraneous material to reveal the art underneath

---

## Filtering in Alteryx

### Filter tool location

**Tool availability**:
- Found in Favorites toolset
- Found in Preparation toolset

### Basic filters

**Basic filter characteristics**:
- Consist of one field with operator and/or specific criteria

**Examples**:
- Sales greater than or equals to 100000
- Employee ID is not null
- Product contains "Pizza"

### Custom filters

**Custom filter capabilities**:
- Utilize multiple criteria
- Write expressions to create subset of data

**Examples**:
- Sales >= 100000 AND Price > 0
- Name equals Jane OR Name equals John
- Range between dates: dates between January 1st, 2022 and January 1st, 2024

---

## Filter Tool Outputs

### Two output anchors

**True output**:
- Criteria in expression are met
- All records that meet requirements will be output

**False output**:
- Shows all records that do not meet specified criteria

---

## AND and OR

### Boolean logic terms in Custom filters

**AND statement**:
- BOTH criteria must be met
- Example: Shape equals Triangle AND Letter equals B

**OR statement**:
- EITHER criteria must be met
- Example: Shape OR Letter criteria is met

**Comparison**:
- AND statement: Both shape equals triangle AND letter equals B
- OR statement: Either shape equals triangle OR letter equals B
- Result is very different than AND statement

---

## Expression Syntax

### Syntax based on data type

**String criteria**:
- Require quotes (single or double quotes can be utilized)
- Example: 'January' needs quotes in expression

**Numeric data types**:
- Do not use quotes
- Example: 100 in expression is not quoted

**Exclamation mark operator**:
- "!" before operator means "not"
- Example: Product field is not empty

**Data type verification**:
- Check data type even if field contains a number
- Example: Length field is a string, so zero requires quotes for expression to function properly

---

## Field Syntax in Custom Expressions

### Writing custom expressions

**Field inclusion rule**:
- Field must be included in each part of statement
- True even when writing expressions for same field

**Date ranges**:
- Important to remember to add field name to second date criterion
- Required when writing expressions to find records between specific date ranges

---

## Formulas in the Filter Tool

### Available formulas

**Accessing formulas**:
- Click Fx or Functions button at top left of expression builder
- View extensive list of categories

**Note**:
- Formulas will be explored further in next chapter with Formula tool

---

## Applying Formulas in Alteryx

### Various formulas are available

**Formula tool categories**:
- Conditional
- DateTime
- Finance
- String
- Much more

---

## Formula Expression Builder

### Expression Builder area

**Similarities**:
- Similar to Filter tool Expression Builder
- Allows you to write custom expressions or modify existing formulas

**Features**:
- Color-codes each part when formula syntax is written correctly
- Data preview shows formula result based on first record in dataset

---

## Data Types Are Important

### Role of data types in formulas

**Expression requirements**:
- String criteria require quotes
- Numeric criteria do not

**Formula category**:
- Essential that formula category uses correct data type

---

## String Formula Examples

### Common string formulas

**PadLeft**:
- Add character to left of existing field
- Useful when adding leading zeroes to Product SKU or ID

**Replace**:
- Replace characters with string text
- Example: Replacing "Co." with "Company"

---

## Flagging with the Contains Formula

### Contains string formula

**Function**:
- Useful for flagging data
- Outputs "0" or "-1" as result

**Flagging behavior**:
- "-1" acts as flag if string contains certain characters or text specified by user
- Example: Stage field contains word "Final"

---

## Length-Based vs Position-Based String Formulas

### Two types of string formulas

**Length-based formulas**:
- Begin counting characters with number 1

**Position-based formulas**:
- Also called "nth or 0-based" formulas
- Begin counting at zero

---

## Length-Based Formulas

### How length-based counting works

**Counting method**:
- Begin counting characters in string with number 1

**Left formula example**:
- Utilizes length count
- In "ALTERYX", three characters on left (1, 2, 3) are "ALT"

---

## Position-Based Formulas

### How position-based counting works

**Counting method**:
- Begin counting at zero

**GetWord formula example**:
- String formula that uses position-based count
- Count words starting with 0, 1, 2, 3
- Word "Preparation" is in position 1
- Formula would return "Preparation" as result

---

## Numeric Formula Examples

### Applications of numeric formulas

**Usage**:
- Applied to numeric data type fields
- Addition and subtraction
- Utilized in Finance and Math formula categories

**Common calculations**:
- Especially useful in calculating percentages
- Example: Percent of sales

---

## Fixed Decimals

### Fixed decimal option

**Availability**:
- Available when working with numeric data
- Provides value for Precision and Scale

**Precision**:
- Length of characters for entire number
- Includes all digits before decimal point
- Includes all digits after decimal point
- Space for decimal point
- Space for negative sign
- Example: Precision would be 10

**Scale**:
- Number of digits after decimal point
- Example: Scale is "2"

---

## Updating Fields and Creating New Ones

### Working with existing fields

**Applying formulas to existing fields**:
- Formulas can be applied to existing fields within dataset
- Note: Data type of existing field cannot be changed

### Creating new fields

**New field creation**:
- Create new fields and apply formulas simultaneously
- Use "Add Column" option under "Select Column"
- Type new field name
- When creating new fields, data type can be manually set

---

## Stacking Formulas in the Formula Tool

### Multiple formulas in one tool

**Stacking capability**:
- Click plus sign to add new formula
- Allows multiple formulas within one tool

**Using new fields**:
- All new fields created can be used in subsequent formulas within same tool
- Located in "New Fields" area of Columns and Constants field list

---

## Sampling Data

### Sampling data is like...

**Chemistry lab analogy**:
- Like sampling fluids in chemistry lab
- Can take top layer of fluid (when oil floats on water)
- Can take top percent of fluid
- Can take random sample

---

## Sample Tool Options

### Available sampling methods

**Options in Sample tool**:
- First or Last N rows
- Skip the first N rows
- 1 of every N rows
- 1 in N chance
- First N% of rows

---

## Top N and Bottom N Records

### Combining Sort and Sample tools

**Method**:
- Sort tool before Sample tool is efficient way to sample Top N records

**Example**:
- Sort total sales in descending order
- Apply Sample tool where N equals 10
- Returns top 10 sales

---

## Skip 1st N Rows

### Functionality

**What it does**:
- Provides all rows after first number of rows specified is skipped

**Use case**:
- Method of skipping rows that contain extraneous information before rows containing data
- Example: Company description and logo in spreadsheet

---

## 1 of Every N Rows

### How this option works

**Functionality**:
- Returns first row of every N rows in dataset

**Example**:
- 1 of every 10 rows returns first record in each group of 10 records, in order
- 100 initial records would return 10 records

**Use case**:
- View patterns in running total

**Important note**:
- This is NOT a random sample process

---

## 1 in N Chance to Include Each Row

### Random sampling method

**Functionality**:
- Random dataset sample
- 1 in N probability of being included in output

**Example**:
- 1 in 25 chance out of 1000 records
- Creates random sample of entire dataset

**Important notes**:
- This option will produce new randomly sampled dataset with each workflow run
- If dataset has unique identifiers, you will see different IDs with each run

---

## First N% of Rows

### Percentage-based sampling

**Functionality**:
- Obtain first percentage specified of rows
- In order from first to last

**Example**:
- "Top 25% of sales"
- In dataset of 1000 records, first 25% of rows would return rows 1 to 250

---

## Grouping with Samples

### Sample tool grouping capability

**Functionality**:
- Sample tool allows grouping by column
- One or more fields can be selected in grouping option

**Example**:
- Top 10 sales by region

---

## Using the Summarize Tool

### Summarize tool features

**Location**:
- In Transform toolset

**Capabilities**:
- Provides many features for grouping and summarizing data

**How it works**:
- All actions depend on data type of each field (string and numeric functions)
- Only fields with actions applied are output
- Multiple actions can be applied to same field

**Example**:
- Min and Max Sales Revenue

---

## Summarizing String Data

### String data actions

**Available options**:
- Group By (example: Group By State)
- Count
- Count Non Null
- Min
- Max (example: Max Date)
- Mode
- First
- Last
- Concatenate

---

## Summarizing Numeric Data

### Numeric field actions

**Available options**:
- Group By
- Previous string data type actions
- Sum (example: Total Sales)
- Average
- Median and Mode (example: Median income)
- Percentile
- Standard Deviation
- Many Finance formulas (IRR and NPV)

---

## Order Does Matter

### Hierarchical application in Summarize tool

**How actions are applied**:
- Summarize tool actions are applied hierarchically
- Example with Group By function

**Grouping example**:
- First by Region
- Then by Sales Team
- Then by Salesperson
- Data will be grouped in that order
- Output with columns listed left to right

---

## Alteryx File Types

### Three main file types

**Alteryx database (.yxdb)**:
- Data can be output in this native format
- Can be input into workflows

**Alteryx Designer workflow (.yxmd)**:
- Standard format

**Alteryx packaged workflow (.yxzp)**:
- Can zip input and output datasets within package
- Ease in sharing
