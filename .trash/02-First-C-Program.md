## Simple C Program: Printing a Line of Text
```c
// A first program in C 
#include 
// function main begins program execution  
int main(void) {  
	printf("Welcome to C!\n");  
	} 
// end function main
```
### Comments
- **Single-line comments**: Use `//` to describe purpose and improve readability.
  - Example: 
    ```c
    // A first program in C
    ```
- **Multi-line comments**: Use `/*...*/` for larger blocks.
  - Avoid errors like missing the closing `*/`.

### Preprocessor Directive
- **`#include`**: Includes header files, e.g., `<stdio.h>`, which provides standard library functions like `printf`.
- Preprocessor directives begin with `#` and are processed before compilation.

### White Space
- Blank lines, spaces, and tabs improve readability but are ignored by the compiler.

### The `main` Function
- Every C program starts with `int main(void)`.
- Purpose of `main`:
  - Entry point for execution.
  - Returns an integer (commonly `0` to indicate success).
- Structure:
  - Begins with `{` and ends with `}` forming a **block**.

#### Output Statement
- **`printf`**: Displays text on the screen.
  - Example:
    ```c
    printf("Welcome to C!\n");
    ```
  - **Statement**: Includes the function call and ends with a semicolon (`;`).

## Escape Sequences
- **`printf`** can use escape sequences for special actions:
  | Escape Sequence | Description                             |
  |-----------------|-----------------------------------------|
  | `\n`            | Moves cursor to the next line.          |
  | `\t`            | Moves cursor to the next horizontal tab.|
  | `\a`            | Produces an alert.                     |
  | `\\`            | Prints a backslash.                    |
  | `\"`            | Prints a double quote.                 |

## Linker and Executables
- **Compiler**: Allocates space for library function calls but doesn't link them.
- **Linker**:
  - Finds library functions (e.g., `printf`).
  - Produces an executable file.
  - Errors like misspelling `printf` are detected at the linking stage.

## Indentation Conventions
- Indent function bodies for readability (3 spaces recommended).
- Prefer spaces over tabs for consistent formatting across editors.

## Variations in Printing
1. **Using Multiple `printf`s**:
   - Example:
     ```c
     printf("Welcome ");
     printf("to C!\n");
     ```
2. **Printing Multiple Lines with One `printf`**:
   - Example:
     ```c
     printf("Welcome\nto\nC!\n");
     ```
   - Outputs:
     ```
     Welcome
     to
     C!
     ```
