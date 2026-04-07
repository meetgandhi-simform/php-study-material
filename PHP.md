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

