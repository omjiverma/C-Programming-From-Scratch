## **Preprocessor and Macros**

The C Preprocessor is a tool that processes source code before compilation. It handles tasks like macro substitution, conditional compilation, and file inclusion.
### 1. Macros

**Defining and Using Macros**

A macro is a preprocessor directive that defines constants or expressions, which are substituted during preprocessing.

**Syntax:**

```c
#define MACRO_NAME value_or_expression
```

**Example:**

```c
#define PI 3.14159
printf("Value of PI: %f\n", PI);
```

**Parameter Macros:**

Macros can also take arguments.

**Example:**

```c
#define SQUARE(x) ((x) * (x))
printf("Square: %d\n", SQUARE(5));  // Outputs: 25
```

**Advantages:**

- Improves readability by using symbolic names for constants.
- Simplifies repetitive code with parameterized macros.

**Limitations:**

- No type checking.
- Can make debugging difficult if overused.

**Conditional Compilation**

Used to include or exclude parts of the code based on conditions.

|Directive|Purpose|
|---|---|
|`#if`|Evaluates a condition and includes code if true.|
|`#ifdef`|Includes code if a macro is defined.|
|`#ifndef`|Includes code if a macro is not defined.|
|`#else`|Provides alternative code if the condition is false.|
|`#elif`|Combines `else` and `if` for multiple conditions.|
|`#endif`|Ends the conditional compilation block.|


**Example:**

```c
#define DEBUG

#ifdef DEBUG
    printf("Debug mode is ON.\n");
#else
    printf("Debug mode is OFF.\n");
#endif
```

**Use Cases:**

- Debugging (`#ifdef DEBUG`)
- Platform-specific code (e.g., Windows vs. Linux)

### 2. Preprocessor Directives

- **`#include`**

- Includes the contents of another file (e.g., standard library headers or custom headers).
- **Syntax:**
- Standard Headers:

```c
#include <header_name>
```

- Custom Headers:
```c
#include "header_name.h"
```
- **`#pragma`**
 - Provides implementation-specific instructions to the compiler.
- **Common Examples:**
  - Suppressing Warnings:

  ```c
   #pragma warning(disable: 4996)
   ```

  - Once Directive:

```c
   #pragma once
```


**Example: Combining Preprocessor Features**

```c
#include <stdio.h>

// Macro Definitions
#define MAX 100
#define SQUARE(x) ((x) * (x))

// Conditional Compilation
#define DEBUG

int main() {
    #ifdef DEBUG
        printf("Debug Mode: SQUARE(5) = %d\n", SQUARE(5));
    #else
        printf("Release Mode\n");
    #endif

    printf("MAX value: %d\n", MAX);

    return 0;
}

```

**Key Points:**

- **Macros:** Define constants or reusable expressions.
- **Parameter Macros:** Create flexible and reusable code templates.
- **Conditional Compilation:** Include/exclude code based on conditions or configurations.
- **`#include`:** Incorporate external files or libraries.
- **`#pragma`:** Provide compiler-specific instructions.