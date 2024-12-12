## **4: Functions**

Functions in C are reusable blocks of code designed to perform a specific task. They help modularize programs, making them easier to read, debug, and maintain.

### Basics of Functions

**What is a Function?**

A function is a self-contained block of code that performs a specific operation.

**Benefits:**

- Improves code modularity.
- Avoids code duplication.
- Facilitates debugging.

**Structure of a Function**

- **Prototype:** Declares the function's name, return type, and parameters.
- **Definition:** Implements the actual logic of the function.
- **Call:** Executes the function in the main program.

**Example:**

```
#include <stdio.h>

// Prototype
int add(int a, int b);

// Definition
int add(int a, int b) {
    return a + b;
}

int main() {
    int result = add(5, 3);  // Call
    printf("Result: %d\n", result);
    return 0;
}
```


### Function Prototypes

A prototype specifies the function's return type, name, and parameter types to ensure the compiler knows how to call it.

**Syntax:**

```
return_type function_name(parameter_list);
```


**Example:**

```
int multiply(int, int);
```


**Purpose:**

- Enforces type-checking at compile time.
- Required for functions defined after their first use in the program.

### Parameter Passing

C supports two ways of passing parameters to functions:

**1. By Value:**

- A copy of the argument's value is passed to the function.
- Modifications inside the function do not affect the original variable.

**Example:**

```
void increment(int x) {
    x++;
}

int main() {
    int a = 5;
    increment(a);
    printf("%d\n", a);  // Outputs: 5
    return 0;
}
```


**2. By Reference:**

- The function receives the memory address of the variable.
- Modifications inside the function affect the original variable.
- Achieved using pointers.

**Example:**

```
void increment(int *x) {
    (*x)++;
}

int main() {
    int a = 5;
    increment(&a);
    printf("%d\n", a);  // Outputs: 6
    return 0;
}
```

### Recursion

Recursion is when a function calls itself either directly or indirectly to solve a problem.

**Structure of a Recursive Function:**

- **Base Case:** A condition to stop recursion.
- **Recursive Step:** A call to the function itself with a modified argument.

**Example:**

```
int factorial(int n) {
    if (n == 0)  // Base case
        return 1;
    return n * factorial(n - 1);  // Recursive step
}

int main() {
    printf("Factorial of 5: %d\n", factorial(5));  // Outputs: 120
    return 0;
}
```


**Common Uses of Recursion:**

- Mathematical problems (factorial, Fibonacci, etc.)
- Searching and sorting (binary search, quicksort)
- Tree traversals

### Recursion vs Iteration

| Aspect      | Recursion                                                    | Iteration                              |
| ----------- | ------------------------------------------------------------ | -------------------------------------- |
| Definition  | Function calls itself repeatedly.                            | Looping constructs (for, while).       |
| Termination | Requires a base case to end recursion.                       | Loop condition determines termination. |
| Performance | May use more memory due to function calls.                   | More memory-efficient.                 |
| Complexity  | Elegant for problems with a natural hierarchy (e.g., trees). | Straightforward for repetitive tasks.  |
| Example     | Factorial using recursion:                                   | Factorial using iteration:             |
|             |                                                              |                                        |
|             | int factorial(int n) {                                       | int factorial(int n) {                 |
|             | if (n == 0) return 1;                                        | int result = 1;                        |
|             | return n * factorial(n - 1);                                 | for (int i = 1; i <= n; i++)           |
|             | }                                                            | result *= i;                           |
|             | }                                                            | return result;                         |
|             | }                                                            | }                                      |
