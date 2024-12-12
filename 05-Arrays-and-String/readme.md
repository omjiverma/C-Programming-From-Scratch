## **5: Arrays and Strings**

Arrays and strings are fundamental data structures in C. Arrays store collections of elements of the same type, while strings are character arrays used to represent text.

### 1. One-Dimensional Arrays

**Declaration and Initialization**

- **Declaration:**
```c
data_type array_name[size];
```

- Example:
```c
int numbers[5];  // Declares an array of 5 integers
```

- **Initialization:**

    ```c
    int numbers[5] = {1, 2, 3, 4, 5};  // Initializes all elements
    int numbers[5] = {1, 2};           // Initializes first 2, others are 0
    int numbers[] = {1, 2, 3};         // Compiler determines size
    ```

**Accessing Elements:**

```c
numbers[0] = 10;  // Assigns 10 to the first element
printf("%d", numbers[2]);  // Accesses the third element
```

**Common Operations**
- **Sorting:**
 - Example: Bubble Sort

```c
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}
```

- **Searching:**
- Linear Search:

```c
        int linearSearch(int arr[], int n, int key) {
            for (int i = 0; i < n; i++) {
                if (arr[i] == key) return i;
            }
            return -1;  // Not found
        }
```
 - Binary Search (Array must be sorted):

```c
        int binarySearch(int arr[], int n, int key) {
            int low = 0, high = n - 1;
            while (low <= high) {
                int mid = (low + high) / 2;
                if (arr[mid] == key) return mid;
                else if (arr[mid] < key) low = mid + 1;
                else high = mid - 1;
            }
            return -1;  // Not found
        }
```  

### 2. Multidimensional Arrays

**Definition and Applications**

Multidimensional arrays are arrays of arrays, commonly used for matrices or tabular data.

**Declaration:**

```
data_type array_name[rows][columns];
```

**Example:**

```
int matrix[3][3];  // 3x3 integer matrix
```

**Initialization:**

```
int matrix[2][2] = {{1, 2}, {3, 4}};  // Initializes all elements
int matrix[2][2] = {1, 2, 3, 4};      // Flattened initialization
```

**Accessing Elements:**

```
matrix[0][1] = 10;  // Assigns 10 to the second element of the first row
printf("%d", matrix[1][1]);  // Accesses element at (1, 1)
```

**Applications:**

- Representing matrices
- Storing tabular data (e.g., student grades, chessboard)
- Graphs in adjacency matrices

### 3. Strings

Strings in C are arrays of characters terminated by a null character (`\0`).

**Character Arrays**

- **Declaration and Initialization:**
   - Explicit:

```c
char str[6] = {'H', 'e', 'l', 'l', 'o', '\0'};
```

   - Implicit (Recommended):

```c
 char str[] = "Hello";  // Compiler adds '\0' automatically
```
 **Accessing Characters:**

```c
printf("%c", str[1]);  // Outputs 'e'
```
**String Manipulation Functions**

The `<string.h>` library provides functions for manipulating strings.

|Function|Description|Example|
|---|---|---|
|`strlen`|Returns the length of the string (excluding `\0`)|`strlen("Hello")` returns 5.|
|`strcpy`|Copies one string into another|`strcpy(dest, src);`|
|`strcat`|Concatenates two strings|`strcat(dest, src);`|
|`strcmp`|Compares two strings (0 if equal)|`strcmp("A", "B")` returns < 0.|
|`strchr`|Finds the first occurrence of a character in a string|`strchr("Hello", 'e')` returns pointer to e.|
|`strstr`|Finds the first occurrence of a substring|`strstr("Hello", "lo")` returns pointer to lo.|


**Examples:**

- **String Copy:**
    ```c
    char src[] = "Hello";
    char dest[10];
    strcpy(dest, src);
    printf("%s", dest);  // Outputs: Hello
    ```

- **String Length:**
    ```c
    char str[] = "World";
    printf("Length: %lu", strlen(str));  // Outputs: Length: 5
    ```
- **String Concatenation:**
```c
    char str1[20] = "Hello ";
    char str2[] = "World";
    strcat(str1, str2);
    printf("%s", str1);  // Outputs: Hello World
```