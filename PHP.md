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
- Starts with <?php and ends with ?>
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