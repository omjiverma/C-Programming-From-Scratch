## **08: File Handling**

File handling in C enables programs to store and retrieve data from files. C provides a set of library functions for interacting with files through file streams.

### **1. File Streams**

**FILE Pointer Basics**

- C uses the `FILE` data type to represent file streams.
- A `FILE` pointer is used to refer to an open file.

**Declaration:**

```
FILE *filePtr;
```

**Key Notes:**

- Always check if the file is successfully opened before performing operations.
- Use `fopen` to open files and `fclose` to close them.

**File Modes**

- File modes determine the purpose of opening a file (e.g., reading, writing).

|Mode|Description|
|---|---|
|`r`|Open file for reading. File must exist.|
|`w`|Open file for writing. Overwrites existing content.|
|`a`|Open file for appending. Writes to the end of the file.|
|`r+`|Open file for reading and writing. File must exist.|
|`w+`|Open file for reading and writing. Overwrites file.|
|`a+`|Open file for reading and appending.|


**Example:**

```c
FILE *filePtr = fopen("example.txt", "r");
if (filePtr == NULL) {
    printf("Error opening file!\n");
}
fclose(filePtr);
```

### 2. Reading and Writing Files

**Functions for File I/O**

- **`fopen`:** Opens a file.
```c
   FILE *fopen(const char *filename, const char *mode);
```

Returns a `FILE` pointer or `NULL` if the operation fails.

- **`fclose`:** Closes an open file.
```c    int fclose(FILE *stream);    
```

Always close a file after operations to avoid data corruption.

- **`fprintf`:** Writes formatted data to a file.

  ```c
   int fprintf(FILE *stream, const char *format, ...);
    ```

**Example:**

```c
FILE *file = fopen("data.txt", "w");
 fprintf(file, "Name: %s, Age: %d\n", "Alice", 25);
fclose(file);
```

- **`fscanf`:** Reads formatted data from a file.

    ```
   int fscanf(FILE *stream, const char *format, ...);
    ```

**Example:**

```c
FILE *file = fopen("data.txt", "r");
char name[50];
int age;
fscanf(file, "Name: %s, Age: %d", name, &age);    printf("Name: %s, Age: %d\n", name, age);
fclose(file);
```
### 3. Random Access

Random access allows reading and writing at arbitrary positions in a file.

**Functions for Random Access**

- **`fseek`:** Moves the file position pointer to a specific location.

    ```
   int fseek(FILE *stream, long offset, int whence);
    ```

- `offset`: Number of bytes to move.
- `whence`:
- `SEEK_SET`: Beginning of file.
- `SEEK_CUR`: Current position.
- `SEEK_END`: End of file.
- **`ftell`:** Returns the current position of the file pointer.

  ```c       
   long ftell(FILE *stream);
  ```
**Example:**
```c
FILE *file = fopen("data.txt", "r");
fseek(file, 10, SEEK_SET);  // Moves to the 10th byte
fclose(file);
```

**Example: Reading and Writing to a File**

```c
#include <stdio.h>

int main() {
    FILE *file;

    // Writing to the file
    file = fopen("example.txt", "w");
    if (file == NULL) {
        printf("Error opening file!\n");
        return 1;
    }
    fprintf(file, "Hello, File Handling in C!\n");
    fclose(file);

    // Reading from the file
    file = fopen("example.txt", "r");
    if (file == NULL) {
        printf("Error opening file!\n");
        return 1;
    }
    char buffer[100];
    fgets(buffer, 100, file);
    printf("Content: %s", buffer);
    fclose(file);

    return 0;
}
```

**Key Points:**

- Always check if the file opens successfully using `NULL`.
- Close the file using `fclose` after completing operations.
- Use `fseek` and `ftell` for advanced file manipulation.