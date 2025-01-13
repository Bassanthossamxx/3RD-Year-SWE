## **Introduction to PHP**

---

### **1. What is PHP?**
- **Dynamic Output**: PHP generates server-side content that dynamically changes based on user requests.
- **Integration**: PHP works seamlessly with HTML, JavaScript, MySQL, and CSS to create dynamic, interactive web pages.

---

### **2. Tools for Development**
- **Integrated Development Environments (IDEs)**:
  - Provide error detection, debugging, and a streamlined learning process.
  - Enable running PHP code and viewing output directly.

---

### **3. Embedding PHP in HTML**
- **File Extensions**:
  - Use `.php` for files processed by the PHP processor.
  - `.html` or `.htm` can also process PHP, but this requires server configuration.
- **Simplest PHP Example**:
  ```php
  <?php
  echo "Hello, world!";
  ?>
  ```

---

### **4. Basic PHP Syntax**
- **PHP Tags**:
  - Opening: `<?php`
  - Closing: `?>` (optional if the file contains only PHP).
- **Programming Styles**:
  - Embed PHP inline within HTML for dynamic content.
  - Separate PHP and HTML to simplify code.

#### **Example**:
```php
<!DOCTYPE html>
<html>
<body>
  <h1>Welcome to PHP!</h1>
  <?php
  echo "This content is generated dynamically.";
  ?>
</body>
</html>
```

---

### **5. Comments in PHP**
- **Single-line Comments**: `//` or `#`
  ```php
  $x = 10; // Incrementing x by 10
  ```
- **Multi-line Comments**: `/* */`
  ```php
  /*
    This is a multi-line comment.
    It spans several lines.
  */
  ```
- **Avoid Pitfalls**:
  - Don't nest `/* */` comments.
  - Use an IDE for syntax highlighting to avoid errors.

---

### **6. Variables in PHP**
- **Syntax**:
  - All variables start with `$`.
  - Example:
    ```php
    $myVar = "Hello, PHP!";
    echo $myVar;
    ```
- **Variable Naming Rules**:
  1. Start with a letter or underscore (`_`) after `$`.
  2. Can include letters, numbers, and underscores.
  3. No spaces allowed (use underscores for readability).
  4. Variable names are case-sensitive.

---

### **7. PHP Arrays**
- **Single-dimensional Arrays**:
  ```php
  $team = array("Alice", "Bob", "Charlie");
  echo $team[1]; // Outputs: Bob
  ```
- **Two-dimensional Arrays**:
  - Used for structures like matrices.
  ```php
  $matrix = array(
      array('x', 'o', 'x'),
      array('o', 'x', 'o'),
      array('x', 'o', ' ')
  );
  echo $matrix[1][2]; // Outputs: o
  ```

---

### **8. Expressions and Operators**
- **Expressions**: Combine variables, values, and operators to produce a result.
  ```php
  $result = 3 * (2 + 4);
  echo $result; // Outputs: 18
  ```

- **Boolean Values**:
  - `TRUE` evaluates to `1`.
  - `FALSE` evaluates to an empty value.
  ```php
  echo (20 > 10) ? "TRUE" : "FALSE"; // Outputs: TRUE
  ```

---

### **9. PHP Operators**
#### **Arithmetic Operators**:
- Perform mathematical operations:
  - `+` (Addition), `-` (Subtraction), `*` (Multiplication), `/` (Division), `%` (Modulus), `**` (Exponentiation).

#### **Assignment Operators**:
- Combine assignment with operations:
  ```php
  $x = 5;
  $x += 3; // Equivalent to $x = $x + 3
  ```

#### **Comparison Operators**:
- Compare values:
  - `==` (Equal), `!=` (Not Equal), `===` (Identical), `>` (Greater than).

#### **Logical Operators**:
- Combine boolean expressions:
  ```php
  if ($hour > 9 && $hour < 17) {
      echo "Working hours";
  }
  ```
Here's an organized breakdown of the "Strings in PHP" section, with examples for each concept:

---

### **1. String Concatenation**
- **Combine Strings**: Use the dot (`.`) operator to concatenate strings.
  ```php
  $msgs = 5;
  echo "You have " . $msgs . " messages."; // Outputs: You have 5 messages.
  ```
- **Append to Existing Variable**: Use `.=` to append a string to an existing variable.
  ```php
  $bulletin = "News: ";
  $newsflash = "PHP is fun!";
  $bulletin .= $newsflash; 
  echo $bulletin; // Outputs: News: PHP is fun!
  ```

---

## **2. String Types**
- **Single-Quoted Strings**:
  - Treated as literal strings.
  - Special characters like `\n` are **not** evaluated.
  - **Example**:
    ```php
    $info = 'Preface variables with a $ like this: $variable';
    echo $info; // Outputs: Preface variables with a $ like this: $variable
    ```

- **Double-Quoted Strings**:
  - Support variable substitution (variables are evaluated inside the string).
  - **Example**:
    ```php
    $count = 10;
    echo "This week $count people viewed your profile."; 
    // Outputs: This week 10 people viewed your profile.
    ```

---

### **3. Escaping Characters**
- Use backslashes (`\`) to escape special characters within strings.
  - **Single Quotes**:
    ```php
    $text = 'My spelling\'s atroshus';
    echo $text; // Outputs: My spelling's atroshus
    ```
  - **Double Quotes**:
    ```php
    $text = "She wrote, \"Return to sender\".";
    echo $text; // Outputs: She wrote, "Return to sender".
    ```

- **Special Characters**:
  - `\t`: Tab
  - `\n`: Newline
  - `\r`: Carriage return
  - **Example**:
    ```php
    echo "Hello\nWorld!"; 
    // Outputs: 
    // Hello
    // World!
    ```

---

### **4. Multiline Strings**
- **Using Double or Single Quotes**:
  - Place text over multiple lines.
  - Variables are evaluated in double quotes.
  - **Example**:
    ```php
    $author = "Steve Ballmer";
    echo "Developers, developers, developers!
    - $author.";
    // Outputs:
    // Developers, developers, developers!
    // - Steve Ballmer.
    ```
  - Assigning to a Variable:
    ```php
    $author = "Bill Gates";
    $text = "Measuring programming progress by lines of code
    is like measuring aircraft building progress by weight.
    - $author.";
    echo $text;
    ```

---

### **5. Heredoc Syntax**
- **Purpose**: Create multiline strings while preserving whitespace and avoiding escaped quotes.
- **Syntax**:
  - Use `<<<` followed by an identifier (e.g., `_END`).
  - End with the identifier on a new line.
  - **Example**:
    ```php
    $author = "Brian W. Kernighan";
    echo <<<_END
    Debugging is twice as hard as writing the code in the first place.
    Therefore, if you write the code as cleverly as possible, you are,
    by definition, not smart enough to debug it.
    - $author.
    _END;
    ```
- **Rules**:
  - Closing identifier (e.g., `_END`) must be on its own line without spaces.
  - Avoid semicolons after the opening tag.

- Assigning to a Variable:
  ```php
  $author = "Scott Adams";
  $quote = <<<_END
  Normal people believe that if it ain't broke, don't fix it.
  Engineers believe that if it ain't broke, it doesn't have enough features yet.
  - $author.
  _END;
  echo $quote;
  ```

---

### **6. Newlines and HTML Formatting**
- **Line Breaks in PHP**:
  - Line breaks are preserved in PHP strings but may not appear in HTML unless explicitly added.
  - **Example**:
    ```php
    echo "Line 1\nLine 2"; 
    // Outputs:
    // Line 1
    // Line 2 (in plain text, not HTML).
    ```
  - Use `<br>` for visible HTML line breaks:
    ```php
    echo "Line 1<br>Line 2"; 
    // Outputs in HTML:
    // Line 1
    // Line 2
    ```

- **View Source**: Use the browser's "View Source" feature to verify preserved line breaks.

---

### **7. Variable Typing**
- PHP is **loosely typed**, dynamically determining variable types.
- **Example: Automatic Conversion**:
  ```php
  $number = 12345 * 67890;
  echo substr($number, 3, 1); // Outputs: 1
  ```

- **String to Number**:
  ```php
  $pi = "3.1415927";
  $radius = 5;
  echo $pi * ($radius * $radius); // Outputs: 78.5398175
  ```

---

### **8. Constants**
- **Definition**: Store unchangeable values during script execution.
- **Syntax**:
  ```php
  define("ROOT_LOCATION", "/usr/local/www/");
  echo ROOT_LOCATION; // Outputs: /usr/local/www/
  ```
- **Rules**:
  - Use `define()`.
  - Cannot start with `$`.
  - Uppercase names are recommended.

---

### **9. Magic Constants**
- Predefined constants for debugging and file information.
  - Examples:
    - `__LINE__`: Current line number.
    - `__FILE__`: Full path of the current file.
    - `__DIR__`: Directory of the file.
    - `__FUNCTION__`: Function name.
  - **Example**:
    ```php
    echo "This is line " . __LINE__ . " of file " . __FILE__;
    ```

---

### **10. echo vs. print**
- **echo**:
  - Faster, does not return a value.
  - Preferred for output.
- **print**:
  - Returns `1`, can be used in expressions.
  - **Example**:
    ```php
    $b = true;
    $b ? print "TRUE" : print "FALSE"; // Outputs: TRUE
    ```

--- 
## 3. **Conditionals in PHP**

---

### **1. The `if` Statement**
- **Purpose**: Executes a block of code if a condition evaluates to `TRUE`.
- **Syntax**:
  ```php
  if (condition) {
      // Actions if the condition is TRUE
  }
  ```
- **Example**:
  ```php
  $bank_balance = 50;
  if ($bank_balance < 100) {
      $money = 1000;
      $bank_balance += $money;
  }
  echo $bank_balance; // Outputs: 1050
  ```
- **Best Practice**:
  - Always use curly braces `{}` for readability, even if there’s only one line of code in the block.
  - Avoid omitting braces to prevent logic errors.

---

### **2. The `else` Statement**
- **Purpose**: Specifies a block of code to execute if the `if` condition is `FALSE`.
- **Syntax**:
  ```php
  if (condition) {
      // Actions if the condition is TRUE
  } else {
      // Actions if the condition is FALSE
  }
  ```
- **Example**:
  ```php
  $bank_balance = 150;
  if ($bank_balance < 100) {
      $money = 1000;
      $bank_balance += $money;
  } else {
      $savings = 50;
      $bank_balance -= 50;
  }
  echo $bank_balance; // Outputs: 100
  ```

---

### **3. The `elseif` Statement**
- **Purpose**: Adds additional checks between the `if` and `else` blocks.
- **Syntax**:
  ```php
  if (condition1) {
      // Actions if condition1 is TRUE
  } elseif (condition2) {
      // Actions if condition2 is TRUE
  } else {
      // Actions if all conditions are FALSE
  }
  ```
- **Example**:
  ```php
  $bank_balance = 250;

  if ($bank_balance < 100) {
      $money = 1000;
      $bank_balance += $money;
  } elseif ($bank_balance > 200) {
      $savings = 100;
      $bank_balance -= 100;
  } else {
      $savings = 50;
      $bank_balance -= 50;
  }

  echo $bank_balance; // Outputs: 150
  ```

---

### **4. The `switch` Statement**
- **Purpose**: Evaluates a variable or expression and executes the block of code that matches the `case` value.
- **Syntax**:
  ```php
  switch (variable) {
      case value1:
          // Actions for value1
          break;
      case value2:
          // Actions for value2
          break;
      default:
          // Actions for unmatched cases
          break;
  }
  ```
- **Example**:
  ```php
  $page = "Home";

  switch ($page) {
      case "Home":
          echo "You selected Home";
          break;
      case "About":
          echo "You selected About";
          break;
      default:
          echo "Unrecognized selection";
          break;
  }
  // Outputs: You selected Home
  ```
- **Notes**:
  - Always use a `break` statement to prevent unintended execution of subsequent `case` blocks.
  - Include a `default` case to handle unmatched values.

---

### **5. The Ternary (`?`) Operator**
- **Purpose**: A shorthand for simple `if-else` statements.
- **Syntax**:
  ```php
  result = condition ? value_if_true : value_if_false;
  ```
- **Example**:
  ```php
  $fuel = 0.5;
  echo $fuel <= 1 ? "Fill tank now" : "There's enough fuel"; 
  // Outputs: Fill tank now
  ```
- **Assigning Result**:
  ```php
  $enough = $fuel <= 1 ? FALSE : TRUE;
  var_dump($enough); // Outputs: bool(false)
  ```

---
##  4. **PHP Loops: An Overview**

---

### **1. `while` Loops**
- **Purpose**: Executes a block of code repeatedly **as long as a condition evaluates to `TRUE`**.
- **Syntax**:
  ```php
  while (condition) {
      // Code to execute
  }
  ```
- **Example 1: Monitoring Fuel Level**
  ```php
  $fuel = 10;
  while ($fuel > 1) {
      echo "There's enough fuel<br>";
      $fuel--; // Decrement fuel to avoid an infinite loop
  }
  // Outputs: "There's enough fuel" 9 times
  ```
- **Example 2: 12 Times Table**
  ```php
  $count = 1;
  while ($count <= 12) {
      echo "$count times 12 is " . $count * 12 . "<br>";
      ++$count; // Increment $count
  }
  // Outputs 12 lines, e.g., "1 times 12 is 12" to "12 times 12 is 144"
  ```
- **Shortened Version**:
  ```php
  $count = 0;
  while (++$count <= 12) 
      echo "$count times 12 is " . $count * 12 . "<br>";
  ```

- **Key Notes**:
  - Ensure the condition eventually becomes `FALSE`, or the loop will run indefinitely.
  - Commonly used when the number of iterations is not predefined.

---

### **2. `do...while` Loops**
- **Purpose**: Guarantees the block of code is executed at least **once**, regardless of the condition.
- **Syntax**:
  ```php
  do {
      // Code to execute
  } while (condition);
  ```
- **Example: 12 Times Table**
  ```php
  $count = 1;
  do {
      echo "$count times 12 is " . $count * 12 . "<br>";
  } while (++$count <= 12);
  ```
- **With Curly Braces**:
  ```php
  $count = 1;
  do {
      echo "$count times 12 is " . $count * 12;
      echo "<br>";
  } while (++$count <= 12);
  ```

---

### **3. `for` Loops**
- **Purpose**: Combines initialization, condition-checking, and modification in a single line.
- **Syntax**:
  ```php
  for (initialization; condition; modification) {
      // Code to execute
  }
  ```
- **Example: 12 Times Table**
  ```php
  for ($count = 1; $count <= 12; ++$count) {
      echo "$count times 12 is " . $count * 12 . "<br>";
  }
  ```
- **Advanced Example: Multiple Variables**
  ```php
  for ($i = 1, $j = 1; $i + $j < 10; $i++, $j++) {
      echo "i = $i, j = $j<br>";
  }
  ```

---

### **4. Breaking Out of Loops**
- **`break`**: Terminates the loop prematurely when a condition is met.
- **Example**:
  ```php
  $fp = fopen("text.txt", 'wb');
  for ($j = 0; $j < 100; ++$j) {
      if (!fwrite($fp, "data")) break; // Exit loop on error
  }
  fclose($fp);
  ```
- **Breaking Multiple Levels**:
  ```php
  break 2; // Exits two levels of nested loops
  ```

---

### **5. Skipping Iterations**
- **`continue`**: Skips the current iteration and moves to the next.
- **Example**: Avoid division by zero
  ```php
  $j = 10;
  while ($j > -10) {
      $j--;
      if ($j == 0) continue; // Skip iteration when $j is 0
      echo (10 / $j) . "<br>";
  }
  ```

---

### **6. Implicit and Explicit Casting**
#### **Implicit Casting**
- PHP automatically converts variable types based on context.
- **Example**:
  ```php
  $a = 56;
  $b = 12;
  $c = $a / $b;
  echo $c; // Outputs: 4.6666666667 (converted to float automatically)
  ```

#### **Explicit Casting**
- Forcefully convert variable types using type casting.
- **Example**:
  ```php
  $a = 56;
  $b = 12;
  $c = (int) ($a / $b); // Explicitly cast to integer
  echo $c; // Outputs: 4
  ```
- **Alternative**: Use built-in functions like `intval()`:
  ```php
  $c = intval($a / $b);
  ```

---

## 5. **PHP Dynamic Linking**

---

### **1. Overview**
- **Dynamic Websites**: PHP enables the creation of dynamic, interactive websites that can respond to user actions using sessions, cookies, or input data.
- **Single PHP Page**: Entire websites can operate using a single PHP page by dynamically linking and handling logic.

---

### **2. Challenges of a Single PHP Page**
1. **Complexity**: Managing large amounts of code becomes difficult as the project grows.
2. **Debugging and Maintenance**: Hard to identify issues or update specific sections in unstructured code.
3. **Solution**: Divide the website into **modules** for better organization and maintainability.

---

### **3. Modular Approach in PHP**
- **Definition**: Breaking down the website into smaller, reusable parts (modules), each responsible for specific functionality.

#### **Examples of Modules**
1. **Sign-up Module**:
   - Handles user registration.
   - Validates emails and checks username availability.
   ```php
   // sign_up.php
   function registerUser($username, $email) {
       // Logic to register user
       echo "User $username registered with email $email.";
   }
   ```

2. **Login Module**:
   - Manages user authentication.
   ```php
   // login.php
   function loginUser($username, $password) {
       if ($username == "admin" && $password == "12345") {
           echo "Login successful!";
       } else {
           echo "Invalid credentials.";
       }
   }
   ```

3. **Messaging Module**:
   - Enables sending and receiving messages.
   ```php
   // messaging.php
   function sendMessage($from, $to, $message) {
       echo "$from sent '$message' to $to.";
   }
   ```

---

### **4. Benefits of Modular Design**
1. **Organized Code**:
   - Easier to understand and maintain.
2. **Team Collaboration**:
   - Teams can work on separate modules simultaneously without interference.
3. **Debugging**:
   - Errors are easier to isolate and fix in specific modules.
4. **Scalability**:
   - Adding features becomes simpler since each module is independent.

---

### **5. Dynamic Linking in Action: WordPress**
- WordPress is an example of a modular PHP application:
  - **Dashboard**: Manages site overview.
  - **Posts**: Handles content creation.
  - **Comments**: Moderates user feedback.
- **Features**:
  - Uses **sessions** for seamless transitions between sections.
  - Dynamically loads only the necessary PHP files.
  - Developers can easily locate and modify specific modules.

---

### **6. Advantages of Dynamic Linking**
1. **Selective Code Loading**:
   - Only the required code is executed, improving performance.
2. **Improved Maintainability**:
   - Changes to one module don’t affect others.
3. **Collaboration-Friendly**:
   - Developers can work on individual modules without conflicts.

---

### **7. Example of Dynamic Linking**
```php
// index.php
$page = $_GET['page'] ?? 'home';

switch ($page) {
    case 'signup':
        include 'sign_up.php';
        registerUser('JohnDoe', 'john@example.com');
        break;

    case 'login':
        include 'login.php';
        loginUser('admin', '12345');
        break;

    case 'message':
        include 'messaging.php';
        sendMessage('Alice', 'Bob', 'Hello!');
        break;

    default:
        echo "Welcome to the homepage.";
}
```
- **Explanation**:
  - Dynamically includes the necessary module based on the user's input (`$_GET['page']`).

---
## 5. **PHP Functions and Objects**

---

### **1. Functions in PHP**
Functions are blocks of reusable code that perform specific tasks. They improve:
- **Code Reusability**: Write once, reuse multiple times.
- **Readability**: Encapsulate logic into named sections.
- **Flexibility**: Accept parameters and return values for dynamic operations.

#### **Benefits of Functions**
1. **Reduce Redundancy**: Centralize code, reducing duplication.
2. **Simplify Maintenance**: Updates to the function reflect everywhere it is used.
3. **Enhance Flexibility**: Parameters and return values allow versatile behavior.

---

### **2. Creating a Function**
- **Syntax**:
  ```php
  function functionName(parameters) {
      // Code to execute
      return value; // Optional
  }
  ```

#### **Example: Simple Function**
```php
function longdate($timestamp) {
    return date("l F jS Y", $timestamp);
}

echo longdate(time()); // Outputs today's date
echo longdate(time() - 17 * 24 * 60 * 60); // Outputs the date 17 days ago
```

---

### **3. Example: Cleaning a Name**
- Functions can process multiple inputs and return formatted outputs.
```php
function fix_names($n1, $n2, $n3) {
    $n1 = ucfirst(strtolower($n1));
    $n2 = ucfirst(strtolower($n2));
    $n3 = ucfirst(strtolower($n3));
    return "$n1 $n2 $n3";
}

echo fix_names("WILLIAM", "henry", "gatES"); 
// Output: William Henry Gates
```

---

### **4. Built-In Functions**
PHP includes many built-in functions for common tasks.

#### **String Functions**
1. `strrev()`: Reverses a string.
   ```php
   echo strrev("Hello"); // Outputs: olleH
   ```
2. `str_repeat()`: Repeats a string.
   ```php
   echo str_repeat("Hip ", 2); // Outputs: Hip Hip
   ```
3. `strtoupper()`: Converts a string to uppercase.
   ```php
   echo strtoupper("hooray!"); // Outputs: HOORAY!
   ```

#### **System Functions**
- `phpinfo()`: Displays PHP configuration.
   ```php
   phpinfo(); // Avoid using in production environments.
   ```

---

### **5. Returning Values**
Functions can return values for further use.

#### **Single Value**
```php
function capitalize($name) {
    return ucfirst(strtolower($name));
}

echo capitalize("wIllIAM"); // Outputs: William
```

#### **Multiple Values**
Return multiple values using an array.
```php
function fix_names($n1, $n2, $n3) {
    return [
        ucfirst(strtolower($n1)),
        ucfirst(strtolower($n2)),
        ucfirst(strtolower($n3))
    ];
}

$names = fix_names("WILLIAM", "henry", "gatES");
echo $names[0] . " " . $names[1] . " " . $names[2]; 
// Outputs: William Henry Gates
```

---

### **6. Variable Scope in PHP**
#### **1. Local Variables**
- Defined inside a function and accessible only within that function.
- Deleted after the function executes.
```php
function example() {
    $temp = "Hello, World!";
    return $temp;
}

// echo $temp; // Error: Undefined variable $temp
```

#### **2. Global Variables**
- Defined outside of functions and accessible globally using the `global` keyword.
```php
$is_logged_in = false;

function login() {
    global $is_logged_in;
    $is_logged_in = true;
}
```

#### **3. Static Variables**
- Retain their value between function calls.
- Useful for counters or state tracking.
```php
function counter() {
    static $count = 0;
    echo $count;
    $count++;
}

counter(); // Outputs: 0
counter(); // Outputs: 1
counter(); // Outputs: 2
```

---

### **7. Superglobal Variables**
- Predefined variables accessible anywhere in a script.
- Examples: `$_GET`, `$_POST`, `$_SERVER`.
```php
$came_from = htmlentities($_SERVER['HTTP_REFERER']); 
echo "You came from $came_from.";
```

#### **Best Practices**:
- Sanitize superglobals before use (e.g., with `htmlentities()`).

---

### **8. Passing Arguments**
#### **Pass by Value**:
- Default behavior: the value is copied to the function.
```php
function add_one($num) {
    $num++;
    return $num;
}

$value = 5;
add_one($value);
echo $value; // Outputs: 5
```

#### **Pass by Reference**:
- Modifies the original variable using `&`.
```php
function fix_names(&$n1, &$n2, &$n3) {
    $n1 = ucfirst(strtolower($n1));
    $n2 = ucfirst(strtolower($n2));
    $n3 = ucfirst(strtolower($n3));
}

$a1 = "WILLIAM"; $a2 = "henry"; $a3 = "gatES";
fix_names($a1, $a2, $a3);
echo "$a1 $a2 $a3"; // Outputs: William Henry Gates
```

---
## 6. **Objects in PHP**

---

### **1. What Are Objects?**
- **Definition**: Objects extend the functionality of functions by combining data (**properties**) and operations (**methods**) into a single structure called a **class**.
- **Key Concepts**:
  - **Classes**: Blueprints for creating objects.
  - **Objects**: Instances of classes.
  - **Methods**: Functions defined within a class.
  - **Properties**: Variables associated with an object.

---

### **2. Variable Scope Recap**
- **Local Variables**:
  - Defined inside a function or block.
  - Accessible only within that scope.
  - Lost when the function exits.
- **Global Variables**:
  - Defined outside any function or class.
  - Accessible throughout the program using the `global` keyword.
- **Static Variables**:
  - Retain their value across multiple function calls but are accessible only within the function.

---

### **3. Including and Requiring Files**
- **`include`**:
  - Fetches a file and inserts its contents into the current script.
  - Generates a warning if the file is not found but continues execution.
  - **Best Practice**: Use `include_once` to avoid multiple inclusions.
  - **Example**:
    ```php
    include "library.php";
    echo "Code after inclusion.";
    ```
- **`require`**:
  - Similar to `include` but throws a fatal error and halts execution if the file is missing.
  - **Example**:
    ```php
    require "library.php";
    echo "Code after requirement.";
    ```

---

### **4. PHP Classes and Objects**
#### **Key Terminology**:
1. **Class**: Blueprint for creating objects.
2. **Object**: An instance of a class.
3. **Properties**: Variables in a class.
4. **Methods**: Functions in a class.
5. **Encapsulation**: Restricting direct access to properties, allowing controlled interaction through methods.

#### **Creating and Using Classes**
- **Example**:
  ```php
  class User {
      public $name, $password;

      function save_user() {
          echo "Save User code goes here";
      }
  }

  $object = new User();
  $object->name = "Joe";
  $object->password = "mypassword";
  $object->save_user(); // Outputs: Save User code goes here
  ```

---

### **5. Object Cloning**
- **By Default**: Assigning one object to another passes a reference.
  - **Without Cloning**:
    ```php
    $object1 = new User();
    $object1->name = "Alice";
    $object2 = $object1;
    $object2->name = "Amy";
    echo $object1->name; // Outputs: Amy
    ```

- **With Cloning**:
  ```php
  $object1 = new User();
  $object1->name = "Alice";
  $object2 = clone $object1;
  $object2->name = "Amy";
  echo $object1->name; // Outputs: Alice
  echo $object2->name; // Outputs: Amy
  ```

---

### **6. Constructors and Destructors**
- **Constructors**:
  - A special method (`__construct`) invoked when an object is created.
  - **Example**:
    ```php
    class User {
        public $username;

        function __construct($username) {
            $this->username = $username;
        }
    }

    $user = new User("Guest");
    echo $user->username; // Outputs: Guest
    ```

- **Destructors**:
  - A special method (`__destruct`) called when an object is no longer in use.
  - **Example**:
    ```php
    class User {
        function __destruct() {
            echo "Cleaning up resources...";
        }
    }
    ```

---

### **7. Methods and Properties**
- **Using Methods**:
  ```php
  class User {
      public $password;

      function get_password() {
          return $this->password;
      }
  }

  $user = new User();
  $user->password = "mypassword";
  echo $user->get_password(); // Outputs: mypassword
  ```

- **Declaring Properties**:
  - Explicit Declaration (recommended):
    ```php
    class User {
        public $name = "John Doe";
        public $age = 25;
    }
    ```

  - Implicit Declaration (not recommended):
    ```php
    $user = new User();
    $user->name = "Alice"; // Creates a new property dynamically
    ```

---

### **8. Constants in Classes**
- Defined using the `const` keyword.
- Accessed with the `::` operator.
- **Example**:
  ```php
  class Translate {
      const ENGLISH = 0;
      const SPANISH = 1;

      static function lookup() {
          echo self::SPANISH;
      }
  }

  Translate::lookup(); // Outputs: 1
  ```

---

### **9. Visibility (Access Modifiers)**
- **Public**: Accessible anywhere.
- **Protected**: Accessible only within the class and subclasses.
- **Private**: Accessible only within the class.
- **Example**:
  ```php
  class Example {
      public $name = "Michael"; // Public
      protected $usercount;    // Protected
      private function admin() { // Private
          echo "Admin logic";
      }
  }
  ```

---

### **10. Static Methods and Properties**
- **Static Methods**:
  - Belong to the class rather than an instance.
  - Cannot use `$this`.
  - **Example**:
    ```php
    class User {
        static function pwd_string() {
            echo "Please enter your password";
        }
    }

    User::pwd_string(); // Outputs: Please enter your password
    ```

- **Static Properties**:
  - Shared across all instances.
  - Accessed with `self::` or `ClassName::`.
  - **Example**:
    ```php
    class Test {
        static $static_property = "I'm static";

        function get_sp() {
            return self::$static_property;
        }
    }

    echo Test::$static_property; // Outputs: I'm static
    ```

---

### **11. Inheritance**
- **Allows reusing and extending code.**
- **Basic Inheritance**:
  ```php
  class User {
      public $name, $password;

      function save_user() {
          echo "Save User code goes here";
      }
  }

  class Subscriber extends User {
      public $phone, $email;

      function display() {
          echo "Name: $this->name<br>";
          echo "Phone: $this->phone<br>";
          echo "Email: $this->email";
      }
  }

  $subscriber = new Subscriber();
  $subscriber->name = "Fred";
  $subscriber->phone = "0123456789";
  $subscriber->email = "fred@example.com";
  $subscriber->display();
  ```
  **Output**:
  ```
  Name: Fred
  Phone: 0123456789
  Email: fred@example.com
  ```

- **Overriding Methods**:
  - Subclasses can redefine methods from the parent class.
  - **Use `parent::` to call the parent method**.
  ```php
  class Dad {
      function test() {
          echo "I am your father<br>";
      }
  }

  class Son extends Dad {
      function test() {
          echo "I am Luke<br>";
      }

      function test2() {
          parent::test();
      }
  }

  $son = new Son();
  $son->test();   // Outputs: I am Luke
  $son->test2();  // Outputs: I am your father
  ```
  ## 7. **Calling Parent Constructors**

---

### **1. Parent Constructor in Subclasses**
- **Default Behavior**: 
  - If a subclass defines its own constructor, the parent class's constructor is **not automatically called**.
- **Solution**:
  - Use `parent::__construct()` within the subclass's constructor to explicitly invoke the parent class's constructor.

---

### **2. Example: Subclass Constructor**

```php
<?php 
class Wildcat {
    public $fur;

    function __construct() {
        $this->fur = "TRUE"; // Initialize the 'fur' property
    }
}

class Tiger extends Wildcat {
    public $stripes;

    function __construct() {
        parent::__construct(); // Explicitly call the parent constructor
        $this->stripes = "TRUE"; // Initialize the 'stripes' property
    }
}

$object = new Tiger();
echo "Tigers have...<br>";
echo "Fur: " . $object->fur . "<br>"; // Outputs: TRUE
echo "Stripes: " . $object->stripes;  // Outputs: TRUE
?>
```

#### **Output**:
```
Tigers have...
Fur: TRUE
Stripes: TRUE
```

#### **Explanation**:
1. The `Wildcat` class defines a constructor that initializes the `fur` property.
2. The `Tiger` class overrides the constructor but explicitly calls `parent::__construct()` to initialize the `fur` property from the parent class.
3. Without `parent::__construct()`, the `fur` property would not be initialized.

---

### **3. Final Methods**
- **Purpose**:
  - The `final` keyword is used to **prevent a subclass from overriding a method**.
- **Syntax**:
  ```php
  final function methodName() {
      // Logic
  }
  ```
- **Example: Final Method**
  ```php
  <?php 
  class User {
      final function copyright() {
          echo "This class was written by Joe Smith";
      }
  }

  class Admin extends User {
      // Trying to override the 'copyright' method here will cause an error.
      // function copyright() {
      //     echo "This is the admin's copyright.";
      // }
  }
  ?>
  ```

#### **Explanation**:
1. The `copyright` method in the `User` class is marked as `final`.
2. Any attempt to override this method in the `Admin` class will result in a **fatal error**.

---



