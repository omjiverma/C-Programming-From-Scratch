### **1: Introduction to C

**Creator:** Dennis Ritchie, AT&T Bell Labs, 1972

**Design Philosophy:**

* Efficiency and performance
* Minimalistic syntax with essential features for low-level access
* Extensive use in systems programming (e.g., OS, embedded systems)

**Key Characteristics:**

* Small set of keywords
* Rich library support
* Compiled to native machine code for high performance

**Key Features of C:**

* **Structures and Unions:** Compound data types for organizing complex data
* **Pointers:** Enable memory and array manipulation
* **Standard Library:** Includes I/O operations and other essential functionalities
* **Macro Preprocessor:** Simplifies repetitive code with macros

**Evolution of C:**

* 1978: "The C Programming Language" published (K&R C)
* 1989/1990: ANSI C standardization (C89/C90)
* 1999: Introduction of C99 standards (backward compatible but not universally supported)

**Applications of C:**

* **System-Level Programming:**
    * Operating systems (e.g., Linux)
    * Embedded systems in automobiles and consumer electronics
* **Other Uses:**
    * Influences derived languages like C++, Java, and Python

**C Compared to Other Languages:**

* **Advantages:** Faster code execution compared to higher-level languages
* **Limitations:**
    * No built-in exception handling or garbage collection
    * Absence of features like object-oriented programming and polymorphism

### **2: C Program Structure**

**C Program Structure**

**Basic Program Anatomy**

A C program consists of various components arranged in a specific structure to ensure proper functionality. The essential elements of a C program include:

- **Comments:** Descriptive text ignored by the compiler, meant for documentation.
- **Preprocessor Directives:** Instructions processed before compilation (e.g., `#include`).
- **The main() Function:** The entry point where the program begins execution.
- **Code Statements:** Instructions that perform operations, enclosed within functions.

**Comments and Formatting**

**Purpose of Comments:**

- Improve code readability and maintainability.
- Explain complex logic or provide metadata about the program (e.g., author, date, purpose).

**Types of Comments:**

- **Single-Line Comments:**
```c
// This is a single-line comment
```
- **Multi-Line Comments:**
```c
/* 
This is a multi-line comment.
Used for detailed explanations.
*/
```

**Best Practices:**

- Place comments near the code they explain.
- Avoid excessive commenting for self-explanatory code.
- Maintain consistency in comment style.

**#include and Header Files**

Header files are essential for defining and including functionality in a C program. They declare constants, macros, and functions for reuse.

**Common Header Files:**

- `<stdio.h>`: Provides standard input/output functions like `printf`, `scanf`.
- `<stdlib.h>`: Provides memory allocation functions like `malloc`, `free`.
- `<string.h>`: Includes string manipulation functions like `strcpy`, `strlen`.

**Syntax:**
```c
#include <header_name.h>  // For standard headers
#include "custom_header.h"  // For custom headers in the current directory
```
**Notes:**

- The `#include` directive is a preprocessor command.
- Angle brackets `< >` indicate system header files, while quotes `" "` are for user-defined headers.

**main() Function Structure**

The `main()` function is the entry point of every C program and is where execution begins.

**Basic Syntax:**
```c
int main(void) {
    // Program statements
    return 0; // Indicates successful execution
}
```
**Key Elements:**

- **Return Type:** Usually `int` (standard practice) to return an exit status to the operating system.
- **Arguments:** Optional parameters: `int argc, char *argv[]`.
    - `argc`: Argument count.
    - `argv[]`: Array of command-line arguments.
```c
    int main(int argc, char *argv[]) {
    printf("Argument count: %d\n", argc);
    return 0;
}
```
**Return Statement:**

- `return 0`: Signals successful completion.
- Non-zero values indicate errors.

**Sample Program: "Hello, World!"**

A "Hello, World!" program demonstrates the basic structure and execution of a C program.

```c
#include <stdio.h>  // Include standard I/O library

int main(void) {
    printf("Hello, World!\n");  // Output text to the console
    return 0;  // Exit successfully
}
```

