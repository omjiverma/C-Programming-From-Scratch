## **Variables, Data Types, and Operators**

### **1: Variables**

Variables act as named storage locations in memory used to hold data values during program execution.

**1. Declaration and Initialization**

* **Declaration:** Reserves memory and specifies the type of data the variable will store.
  * Syntax: `datatype variable_name;`
  * Example:
    ```c
    int age;  // Declares an integer variable named 'age'.
    ```

* **Initialization:** Assigns a value to the variable. Can be done during or after declaration.
  * Example:
    ```c
    int age = 25;  // Declaration with initialization.
    age = 30;      // Assigning a new value.
    ```

**2. Scope and Lifetime**

* **Scope:** Defines where a variable is accessible in the program.
  * **Global Scope:** Declared outside all functions; accessible throughout the program.
  * **Local Scope:** Declared within a function or block; accessible only in that function/block.
  * Example:
    ```c
    int globalVar = 10;  // Global scope

    void example() {
        int localVar = 5;  // Local scope
    }
    ```

* **Lifetime:**
  * **Static:** Retains value throughout program execution.
  * **Automatic (Default):** Created at block entry and destroyed at block exit.

### **2: Data Types**

Data types define the kind of data a variable can hold.

**1. Primitive Types**

* **int:** Integer values (e.g., 10, -5). Size: Typically 4 bytes (platform-dependent).
* **float:** Floating-point numbers (e.g., 3.14). Precision: Single precision (6-7 digits).
* **char:** Single character (e.g., 'A', '3'). Size: 1 byte.

**2. Derived Types**

* **Arrays:** Collection of elements of the same type.
  * Example:
    ```c
    int numbers[5] = {1, 2, 3, 4, 5};
    ```

* **Pointers:** Variables that store memory addresses.
  * Example:
    ```c
    int *ptr;
    int x = 10;
    ptr = &x;  // Pointer stores the address of 'x'.
    ```

* **Structures:** Aggregates related data of different types.
  * Example:
    ```c
    struct Point {
        int x;
        int y;
    };
    ```

**3. Size of Data Types**

In C, the size of data types depends on the system architecture (e.g., 32-bit or 64-bit). Use the `sizeof` operator to determine the size in bytes.

###### Primitive Data Types in C

|Data Type|Typical Size (in bytes)|Range|
|---|---|---|
|`char`|1|-128 to 127 (signed), 0 to 255 (unsigned)|
|`short`|2|-32,768 to 32,767|
|`int`|4|-2,147,483,648 to 2,147,483,647|
|`long`|4 or 8|-2,147,483,648 to 2,147,483,647 (32-bit), -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 (64-bit)|
|`float`|4|±3.4e-38 to ±3.4e38|
|`double`|8|±1.7e-308 to ±1.7e308|
|`long double`|10, 12, or 16|Implementation-defined|
|`void`|0|No value, no storage|

**Note:** The actual size of data types can vary across different compilers and systems. However, these are the common sizes used in most C implementations.

###### Derived Data Types

- **Arrays:** A collection of elements of the same data type.

    ```
    int numbers[10];  // Array of 10 integers
    ```
- **Structures:** A user-defined data type that groups variables of different data types.
    ```
    struct Point {
        int x;
        int y;
    };
    ```
- **Pointers:** A variable that stores the memory address of another variable.
    ```
    int *ptr;
    ```
###### The `sizeof` Operator

The `sizeof` operator is used to determine the size (in bytes) of data types or variables.

**Syntax:**

```
sizeof(datatype);
sizeof(variable);
```

**Example:**
```
int a;
printf("Size of a: %lu bytes\n", sizeof(a));
```

### **3: Operators**
Operators perform operations on variables and values.
#### **1. Arithmetic Operators**

Arithmetic operators are used for mathematical calculations.

|Operator|Description|Example|Result|
|---|---|---|---|
|`+`|Addition|`a + b`|Sum of `a` and `b`|
|`-`|Subtraction|`a - b`|Difference of `a` and `b`|
|`*`|Multiplication|`a * b`|Product of `a` and `b`|
|`/`|Division|`a / b`|Quotient of `a` divided by `b`|
|`%`|Modulus (Remainder)|`a % b`|Remainder when `a` is divided by `b`|

---

#### **2. Relational Operators**

Relational operators compare two values and return `true` (1) or `false` (0).

|Operator|Description|Example|Result|
|---|---|---|---|
|`==`|Equal to|`a == b`|`1` if `a` is equal to `b`, else `0`|
|`!=`|Not equal to|`a != b`|`1` if `a` is not equal to `b`, else `0`|
|`<`|Less than|`a < b`|`1` if `a` is less than `b`, else `0`|
|`>`|Greater than|`a > b`|`1` if `a` is greater than `b`, else `0`|
|`<=`|Less than or equal to|`a <= b`|`1` if `a` is less than or equal to `b`, else `0`|
|`>=`|Greater than or equal to|`a >= b`|`1` if `a` is greater than or equal to `b`, else `0`|

---

#### **3. Logical Operators**

Logical operators are used to combine multiple conditions.

|Operator|Description|Example|Result|
|---|---|---|---|
|`&&`|Logical AND|`a > 0 && b > 0`|`1` if both `a` and `b` are true|
|`||`|Logical OR|
|`!`|Logical NOT|`!(a > 0)`|`1` if `a > 0` is false|

---

#### **4. Bitwise Operators**

Bitwise operators perform operations on the binary representation of integers.

|Operator|Description|Example|Binary Result|
|---|---|---|---|
|`&`|Bitwise AND|`a & b`|Bits set in both `a` and `b`|
|`|`|Bitwise OR|`a|
|`^`|Bitwise XOR|`a ^ b`|Bits set in `a` or `b`, but not both|
|`~`|Bitwise NOT (complement)|`~a`|Inverts all bits of `a`|
|`<<`|Left shift|`a << 2`|Shifts bits of `a` left by 2 places|
|`>>`|Right shift|`a >> 2`|Shifts bits of `a` right by 2 places|

---

### **Operator Precedence and Associativity**

**Precedence** determines the order in which operators are evaluated.  
**Associativity** resolves the order for operators with the same precedence.

|Precedence|Operators|Description|Associativity|
|---|---|---|---|
|1|`()`|Parentheses|Left-to-right|
|2|`*`, `/`, `%`|Multiplication, Division, Modulus|Left-to-right|
|3|`+`, `-`|Addition, Subtraction|Left-to-right|
|4|`<`, `<=`, `>`, `>=`|Relational operators|Left-to-right|
|5|`==`, `!=`|Equality operators|Left-to-right|
|6|`&&`|Logical AND|Left-to-right|
|7|`||`|
|8|`=`, `+=`, `-=`|Assignment operators|Right-to-left|
**Examples**:

1. **Precedence**:
```c
int result = 5 + 2 * 3;  // Output: 11 (Multiplication first)

```
1. **Associativity**:
```c
int a = b = c = 10;      // Right-to-left: c = 10, b = c, a = b

```
**Best Practices**:

- Use parentheses to override precedence and ensure clarity.
- Avoid overly complex expressions for better readability.

#### **5. Increment and Decrement Operators**

The increment (`++`) and decrement (`--`) operators are unary operators used to modify a variable's value by 1.

#### Types of Increment/Decrement

1. **Post-Increment (x++) / Post-Decrement (x--)**
   - Increments or decrements the value **after** using it in an expression.


```c
 int x = 5;
  printf("%d\n", x++);  // Outputs 5, then x becomes 6.
```

2. **Pre-Increment (++x) / Pre-Decrement (--x)**
- Increments or decrements the value **before** using it in an expression.

  ```c
   int x = 5;
   printf("%d\n", ++x);  // x becomes 6, then outputs 6.
   ```


#### Examples of Usage

**Basic Increment/Decrement:**

```c
int a = 10;
a++;  // a becomes 11
--a;  // a becomes 10
```


**In Loops:**

Increment and decrement are often used as counter updates in loops.
```c
for (int i = 0; i < 5; i++) {
   printf("%d\n", i);  // Outputs: 0 1 2 3 4
}
```


**Expression Evaluation:**

Combined with other operations, increment/decrement affects the sequence of evaluation.

```c
int x = 5, y;
y = x++ + 10;  // y = 15, x = 6
```