# 🔷 1. What is PHP?

👉 PHP is a server-side scripting language used to build websites and web applications.

✅ Key meaning:
- PHP = PHP:Hypertext Preprocessor
- Earlier: Personal Home Page

✅ Important concept:
- Runs on server, not browser
- Browser only sees HTML output

👉 Flow:
```diagram
User (Browser) → Request → Server (PHP runs) → HTML → Browser
```

## What is a Scripting Language?

👉 A scripting language executes code at runtime (no compilation needed)

💡 Example:
- PHP → Server-side scripting
- JavaScript → Client-side scripting

## Server-side vs Client-side
| Feature    | PHP              | JavaScript        |
| ---------- | ---------------- | ----------------- |
| Runs on    | Server           | Browser           |
| Visibility | Hidden from user | Visible           |
| Use        | Backend logic    | UI / Interactions |

## Why Use PHP?

✅ Advantages:
- Open source (free)
- Easy to learn
- Works with MySQL easily
- Supported by almost all hosting servers
- Cross-platform (Windows, Linux, Mac)
- Large community

👉 In simple words:

PHP is cheap + easy + powerful for backend

## PHP Syntax Basics

🧩 PHP code structure:

```php
<?php
   // your code here
?>
```

🔑 Rules:
- Starts with 
```PHP
<?php and ends with ?>
```
- Each statement ends with ;
- Case-sensitive variables

## PHP File

👉 PHP files always end with:
```
.php
```
👉 Example:
```
index.php
login.php
```

## Embedding PHP in HTML

👉 PHP can be written inside HTML:
```php
<html>
<body>

<?php
echo "Hello";
?>

</body>
</html>
```

✔ Server processes PHP → sends only HTML to browser

## Important Concepts (Hidden but VERY IMPORTANT)

✔ PHP is interpreted on server
- Browser never sees PHP code

✔ Output is always HTML
- PHP → converts → HTML → browser

✔ Can work with databases
- MySQL, PostgreSQL, etc.

## Programming vs Scripting

| Programming Language | Scripting Language |
| -------------------- | ------------------ |
| Needs compilation    | No compilation     |
| Full applications    | Small tasks        |
| Example: Java        | Example: PHP       |

👉 PHP is technically both, but mostly used as scripting language

## Real-world Usage

👉 PHP is used to build:

- Dynamic websites
- Login systems
- Admin panels
- APIs

# 🔷 2. PHP Data Types

Data type = type/category of data stored in a variable.

🔹 Main PHP Data Types

1. Integer
- Whole numbers
```php
$x = 10;
```
2. Float (Double)
- Decimal numbers
```php
$y = 3.14;
```
3. String
- Text data
```php
$name = "Meet";
```
4. Boolean
- True / False
```php
$isActive = true;
```

👉 PHP is loosely typed → You don’t need to define type manually.

🔥 Important (Interview Point)
- PHP automatically decides type → called Type Juggling
- Example:
```php
$x = "10" + 5; // Output = 15
```

## PHP Variables

👉 Definition:
A variable is a container to store data in memory.

🔹 Rules of Variables
```php
$name = "Meet";
$age = 21;
```
- Must start with $
- ✔ Must start with letter or _
- ✔ No spaces
- ✔ Case-sensitive ($name ≠ $Name)

🔹 Types of Variables (Scope)

1. Local Variable
- Declared inside function
- Only usable inside function
```php
function test() {
    $x = 10; // local
}
```
2. Global Variable
- Declared outside function
- Can be accessed globally
```php
$x = 10;

function test() {
    global $x;
}
```

## Use of Variables

👉 Variables are reusable containers.
```php
$price = 100;
$tax = 10;

$total = $price + $tax;
echo $total; // 110
```

👉 Think like:

Variable = Box storing value

## Type Casting (Important Concept)

👉 Converting one data type into another
```php
$x = "10";
$y = (int)$x; // convert string → int
```
Types:

- (int)
- (float)
- (string)
- (bool)

## PHP Constants

👉 Constant = value that cannot change
```php
define("PI", 3.14);
echo PI;
```
- ✔ No $ sign
- ✔ Value is fixed

## PHP Operators

👉 Operators are used to perform operations.

🔹 1. Arithmetic Operators
```
+  -  *  /  %
```
Example:
```php
echo 10 + 5; // 15
```

🔹 2. Assignment Operators
```
=   +=   -=   *=   /=
```
Example:
```php
$x = 5;
$x += 3; // 8
```

🔹 3. Comparison Operators
```
==   ===   !=   >   <   >=   <=
```
Example:
```php
$x = 10;
$y = "10";

var_dump($x == $y);  // true
var_dump($x === $y); // false
```
- 👉 == → value check
- 👉 === → value + type check

🔹 4. Logical Operators
```
&&   ||   !
```
Example:
```php
if ($age > 18 && $age < 60) {
    echo "Working age";
}
```

🔹 5. String Operator
```
.   // concatenation
```
```php
echo "Hello " . "Meet";
```

# 🔷 3. Why Comments Are Used

Comments are lines in code that are ignored by PHP and only help humans understand the code.

🔹 Types of Comments

1. Single-line comment
```
// This is a comment
# This is also a comment
```
2. Multi-line comment
```
/*
This is a 
multi-line comment
*/'
```

💡 Why Important?
- Makes code readable
- Helps in debugging
- Used in teamwork

👉 Think like:
- Comments = Notes for developers 🧠

# 🔷 4. PHP Include & Include_once

👉 Used to insert one file into another file

🔹 Syntax
```php
include 'file.php';
include_once 'file.php';
```
🔹 Real Example

📁 header.php
```php
<a href="index.php">Home</a>
<a href="about.php">About</a>
```
📁 index.php
```php
include 'header.php';
```
👉 Output → Header gets added automatically

🔹 What is include_once?

👉 It ensures file is included only once
```php
include_once 'config.php';
```
- ✔ Prevents duplicate loading
- ✔ Avoids errors like redeclaration

💡 Real Use Cases
- Navbar
- Footer
- Common functions
- Layout reuse

👉 This improves code reuse and maintainability

# 🔷 5. PHP Require & Require_once

👉 Same as include, but more strict

🔹 Syntax
```php
require 'file.php';
require_once 'file.php';
```

🔹 Example
```php
require 'config.php';
```
👉 Used when file is critical (like DB connection)

🔹 require_once

👉 Includes file only once (same as include_once behavior)

## Difference: include vs require (VERY IMPORTANT)
| Feature          | include        | require         |
| ---------------- | -------------- | --------------- |
| Error Type       | Warning        | Fatal Error     |
| Script Execution | Continues      | Stops           |
| Usage            | Optional files | Mandatory files |

👉 If file missing:
```php
include 'file.php'; // warning, continues
require 'file.php'; // fatal error, stops
```
- ✔ include → safe
- ✔ require → strict

📌 Confirmed:

- include → warning + continues
- require → fatal error + stops execution

## include_once vs require_once

👉 Both prevent multiple inclusions
| Statement    | Behavior          |
| ------------ | ----------------- |
| include_once | include only once |
| require_once | require only once |

✔ Avoids:

- Function redeclaration error
- Class duplication

## When to Use What

✅ Use include
- Header / Footer
- UI components
- Optional files

✅ Use require
- Database config
- Core logic files
- Authentication system

👉 Rule:

- If app can run without file → include
- If app cannot run → require

## Big Picture (Very Important Concept)

👉 These functions help in:

- ✔ Code reusability
- ✔ Modular programming
- ✔ Clean architecture

Example:
```
config.php → DB connection
header.php → UI
functions.php → common logic
```

Then:
```
require 'config.php';
include 'header.php';
```

# 🔷 6. Array in PHP?

An array is a variable that can store multiple values in a single variable.

💡 Simple Understanding
```php
$name1 = "Meet";
$name2 = "Raj";
$name3 = "Amit";
```
❌ Bad (too many variables)
```php
$names = ["Meet", "Raj", "Amit"];
```
✅ Good (single variable)

👉 Think like:
- Array = One box 📦 containing many items

## Why Arrays Are Used

- Store multiple values
- Easy to manage data
- Useful for loops, DB results, APIs

👉 Arrays make data handling easier and faster

## Types of Arrays in PHP

### 1. Numeric (Indexed) Array

👉 Uses numbers (0,1,2...) as index

🔹 Example
```php
$movies[0] = "Shaolin Monk";
$movies[1] = "Drunken Master";
$movies[2] = "American Ninja";
```
👉 Access:
```php
echo $movies[1]; // Drunken Master
```
🔹 Alternative Syntax
```php
$movies = array(
  0 => "Shaolin Monk",
  1 => "Drunken Master"
);
```
💡 Important Points
- Index starts from 0
- Order matters
- Used for lists

### 2. Associative Array

👉 Uses key => value pair (like object/map)

🔹 Example
```php
$persons = array(
  "Meet" => "Male",
  "Riya" => "Female"
);
```
👉 Access:
```php
echo $persons["Meet"]; // Male
```
💡 Important Points
- Keys are custom names
- Easy to understand data
- Used in database results

👉 Example (real project):
```php
$user = [
  "name" => "Meet",
  "email" => "meet@gmail.com"
];
```

### 3. Multidimensional Array

👉 Array inside array

🔹 Example
```php
$movies = array(
  "comedy" => ["M1" => "Movie1", "M2" => "Movie2"],
  "action" => ["Movie3", "Movie4"]
);
```

👉 Access:
```php
echo $movies["comedy"]["M2"];
```

💡 Important Points
- Used for complex data
- Represents tables / JSON / DB data

👉 Example (VERY IMPORTANT for you):
```php
$users = [
  ["name" => "Meet", "age" => 21],
  ["name" => "Raj", "age" => 22]
];
```

## Accessing Array Elements

👉 Using index or key
```php
echo $array[index];
echo $array["key"];
```

- ✔ Index → numeric array
- ✔ Key → associative array

### Updating Array Values

```php
$movies[1] = "New Movie";
```

👉 Arrays are mutable (changeable)

### Array Keys

👉 Each value has a key/index

- Numeric → 0,1,2
- Associative → name, email

👉 Keys are used to access memory location

## Array Operators

👉 Used to compare arrays
| Operator | Meaning      |
| -------- | ------------ |
| +        | Union        |
| ==       | Equal        |
| ===      | Equal + type |
| !=       | Not equal    |

🔹 Example
```php
$a = ["a" => 1];
$b = ["b" => 2];

$c = $a + $b;
```

## Array Functions

### count()

Counts number of elements
```php
$arr = ["A", "B", "C"];
echo count($arr); // 3
```
- ✔ Used in loops
- ✔ Used in validations

📌 Very commonly used in real projects

### print_r() / var_dump()

👉 Used to display arrays (debugging)
```php
print_r($arr);
```
```php
var_dump($arr);
```
- ✔ Debugging tool
- ✔ Shows structure of array

### array_push() → Add Element

👉 Adds element at the end
```php
$arr = ["A", "B"];
array_push($arr, "C");
```
✔ Output: ["A", "B", "C"]

### array_pop() → Remove Last Element
```php
array_pop($arr);
```
- ✔ Removes last element
- ✔ Useful in stack operations

### array_shift() → Remove First Element
```php
array_shift($arr);
```
- ✔ Removes first element
- ✔ Re-indexes array

### array_unshift() → Add at Beginning
```php
array_unshift($arr, "Z");
```
✔ Adds element at start

### array_merge() → Combine Arrays
```php
$a = ["A", "B"];
$b = ["C", "D"];

$c = array_merge($a, $b);
```
✔ Output: ["A","B","C","D"]

### in_array() → Search Value
```php
$arr = ["A", "B", "C"];

if (in_array("B", $arr)) {
    echo "Found";
}
```
✔ Returns true/false

### array_keys() → Get Keys
```php
$arr = ["name" => "Meet", "age" => 21];

print_r(array_keys($arr));
```
✔ Output: ["name", "age"]

### array_values() → Get Values
```php
print_r(array_values($arr));
```
✔ Output: ["Meet", 21]

### sort() → Sort Array (Ascending)
```php
$arr = [3, 1, 2];
sort($arr);
```
✔ Output: [1,2,3]

### rsort() → Descending Sort
```php
rsort($arr);
```
✔ Output: [3,2,1]

### asort() → Sort Associative (by Value)
```php
$arr = ["a"=>3, "b"=>1, "c"=>2];
asort($arr);
```
✔ Maintains keys

### ksort() → Sort by Keys
```php
ksort($arr);
```
✔ Sorts based on keys

### explode() → String → Array
```php
$str = "A,B,C";
$arr = explode(",", $str);
```
✔ Output: ["A","B","C"]

### implode() → Array → String
```php
$arr = ["A","B","C"];
$str = implode(",", $arr);
```
✔ Output: "A,B,C"

### is_array() → Check Type
```php
is_array($arr); // true or false
```
✔ Used in validation

# Variable Variable in PHP

A variable variable means:

👉 The name of a variable is stored inside another variable

So PHP uses the value of one variable as the name of another variable.

🧠 Basic Syntax
```php
$var = "name";
$$var = "Meet";
```
👉 This means:
```php
$name = "Meet";
```
- ✔️ $var holds "name"
- ✔️ $$var becomes $name

# Copy On Write

Instead of copying data immediately when you assign a variable to another, PHP shares the same memory.

👉 It only creates a real copy when one of the variables is modified.

🔹 Example 1: Without Modification
```php
$a = [1, 2, 3];
$b = $a;  // No actual copy yet

// Both $a and $b point to same memory internally
```

✔️ At this point:
- No new memory is allocated
- PHP just increases a reference count

🔹 Example 2: When Modification Happens
```php
$a = [1, 2, 3];
$b = $a;

$b[0] = 100;  // Modification triggers copy
```

✔️ Now:
- PHP creates a separate copy for $b
- $a remains unchanged

👉 Final values:
```php
$a = [1, 2, 3];
$b = [100, 2, 3];
```

🔍 What’s Happening Internally?
- $a is created → memory allocated
- $b = $a → both point to same memory (refcount = 2)
- $b[0] = 100 → PHP detects change
- COW triggers → data is copied
- $b gets its own memory

⚡ Why PHP Uses Copy-On-Write

✅ Benefits
- Saves memory
- Faster assignments
- Efficient for large arrays/strings

🔸 Important Note: Reference vs COW
```php
$a = [1, 2, 3];
$b = &$a;  // reference (NOT copy-on-write)

$b[0] = 100;
```

✔️ Now:
```php  
$a = [100, 2, 3];
$b = [100, 2, 3];
```

👉 Because:
- & creates a true reference
- No COW happens

🆚 COW vs Reference (Quick Table)
| Feature       | Copy-On-Write        | Reference (`&`) |
| ------------- | -------------------- | --------------- |
| Copy created? | Only on modification | Never           |
| Memory usage  | Optimized            | Shared          |
| Independence  | Yes after change     | No              |
| Performance   | Fast                 | Fast but risky  |

# PHP Control Structure

A control structure in PHP is used to control the flow of execution of your program.

👉 It decides:
- Which code runs
- When it runs
- How many times it runs

### 🔹 Types of Control Structures in PHP

There are mainly 3 categories:

### 1️⃣ Conditional Statements (Decision Making)

👉 Used to execute code based on conditions

✅ if Statement
```php
$age = 18;

if ($age >= 18) {
    echo "Adult";
}
```

✅ if...else
```php
$age = 16;

if ($age >= 18) {
    echo "Adult";
} else {
    echo "Minor";
}
```

✅ if...elseif...else
```php
$marks = 75;

if ($marks >= 90) {
    echo "A";
} elseif ($marks >= 70) {
    echo "B";
} else {
    echo "C";
}
```

✅ switch Statement
```php
$day = "Monday";

switch ($day) {
    case "Monday":
        echo "Start of week";
        break;
    case "Friday":
        echo "Weekend coming";
        break;
    default:
        echo "Normal day";
}
```
✔️ Used when multiple conditions depend on same variable

### 2️⃣ Loops (Iteration)

👉 Used to execute code multiple times

🔁 for Loop
```php
for ($i = 0; $i < 5; $i++) {
    echo $i;
}
```

🔁 while Loop
```php
$i = 0;

while ($i < 5) {
    echo $i;
    $i++;
}
```

🔁 do...while Loop
```php
$i = 0;

do {
    echo $i;
    $i++;
} while ($i < 5);
```

🔁 foreach Loop (Very Important 🔥)
```php
$arr = [10, 20, 30];

foreach ($arr as $value) {
    echo $value;
}
```
✔️ Mostly used with arrays

### 3️⃣ Control Flow Statements (Jump Statements)

👉 Used to alter normal flow

⏭️ break
```php
for ($i = 0; $i < 5; $i++) {
    if ($i == 3) break;
    echo $i;
}
```
✔️ Stops loop immediately


⏭️ continue
```php
for ($i = 0; $i < 5; $i++) {
    if ($i == 2) continue;
    echo $i;
}
```
✔️ Skips current iteration

🔙 return
```php
function test() {
    return "Hello";
}
```
✔️ Exits function

🛑 exit / die
```php
echo "Start";
exit();
echo "End"; // won't run
```

# PHP Loops

Loops in PHP are used to execute a block of code repeatedly until a condition is met.

👉 Instead of writing the same code multiple times, you use loops to automate repetition.

🧠 Simple Definition (Interview Ready)

A loop in PHP is a control structure that allows repeated execution of a block of code based on a condition.

## 🔹 Types of Loops in PHP

There are 4 main loops:

### 1️⃣ for Loop

👉 Used when you know how many times you want to run the loop

✅ Syntax
```php
for (initialization; condition; increment/decrement) {
    // code
}
```

🔹 Example
```php
for ($i = 1; $i <= 5; $i++) {
    echo $i . " ";
}
```
✔️ Output:
```bash
1 2 3 4 5
```

🧠 Use Case
- Fixed iterations
- Counting loops

### 2️⃣ while Loop

👉 Used when the number of iterations is not fixed

✅ Syntax
```php
while (condition) {
    // code
}
```

🔹 Example
```php
$i = 1;

while ($i <= 5) {
    echo $i . " ";
    $i++;
}
```

⚠️ Important

👉 If condition never becomes false → infinite loop

### 3️⃣ do...while Loop

👉 Executes at least once, even if condition is false

✅ Syntax
```php
do {
    // code
} while (condition);
```

🔹 Example
```php
$i = 10;

do {
    echo $i;
} while ($i < 5);
```
✔️ Output:
```
10
```
👉 Runs once even though condition is false

### 4️⃣ foreach Loop (Most Important 🔥)

👉 Used for arrays and collections

✅ Syntax
```php
foreach ($array as $value) {
    // code
}
```

🔹 Example
```php
$users = ["Meet", "Rohan", "Amit"];

foreach ($users as $user) {
    echo $user . " ";
}
```
✔️ Output:
```

```