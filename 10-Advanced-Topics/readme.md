## Dynamic Memory Allocation

Dynamic memory allocation in C allows programs to request memory at runtime, providing flexibility to handle varying memory needs.

### 1. Functions for Dynamic Memory Allocation

C provides the following functions from `<stdlib.h>` for managing dynamic memory:

|Function|Purpose|
|---|---|
|`malloc`|Allocates a block of memory and returns a pointer to the first byte.|
|`calloc`|Allocates memory for an array and initializes all bytes to zero.|
|`realloc`|Resizes a previously allocated memory block.|
|`free`|Releases allocated memory back to the system.|


**1.1 `malloc`**

Allocates a specified number of bytes. Does not initialize memory.

**Syntax:**

```c
void* malloc(size_t size);
```

**Example:**

```c
int *ptr = (int *)malloc(5 * sizeof(int));  // Allocates memory for 5 integers
if (ptr == NULL) {
    printf("Memory allocation failed\n");
    exit(1);
}
```

**1.2 `calloc`**

Allocates memory for an array and initializes all elements to 0.

**Syntax:**

```c
void* calloc(size_t num_elements, size_t element_size);
```

**Example:**

```c
int *ptr = (int *)calloc(5, sizeof(int));  // Allocates and zero-initializes memory for 5 integers
if (ptr == NULL) {
    printf("Memory allocation failed\n");
    exit(1);
}
```

**1.3 `realloc`**

Resizes a previously allocated memory block.

**Syntax:**

```c
void* realloc(void *ptr, size_t new_size);
```

**Example:**

```c
int *ptr = (int *)malloc(3 * sizeof(int));  // Initially allocate memory
ptr = (int *)realloc(ptr, 5 * sizeof(int));  // Resize to hold 5 integers
```

**1.4 `free`**

Releases memory previously allocated by `malloc`, `calloc`, or `realloc`.

**Syntax:**

```c
void free(void *ptr);
```

**Example:**

```c
free(ptr);  // Frees the allocated memory
ptr = NULL;  // Best practice to avoid dangling pointers
```

### 2. Handling Memory Leaks

A memory leak occurs when dynamically allocated memory is not released, leading to wasted resources and eventual program failure.

**2.1 Identifying Memory Leaks**

- Use tools like `valgrind` (Linux) to detect memory leaks.

**2.2 Best Practices for Avoiding Memory Leaks**

- **Always Free Allocated Memory:**
  - Every `malloc` or `calloc` should have a corresponding `free`.
- **Use NULL After Freeing:**
  - Avoid dangling pointers by resetting to NULL.

```c
   free(ptr);
   ptr = NULL;
```
   
- **Track Allocations:**
  - Use comments or maintain logs to track memory usage.
- **Check Return Values:**
 - Ensure memory allocation functions succeed before using the pointer.
```c
   if (ptr == NULL) {
   printf("Memory allocation failed\n");
   }
```
   

### Examples

**Dynamic Memory Allocation Example:**

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    // Dynamic allocation using malloc
    int *arr = (int *)malloc(n * sizeof(int));
    if (arr == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }

    // Reading values
    printf("Enter %d elements:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    // Displaying values
    printf("You entered:\n");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }

    // Free memory
    free(arr);

    return 0;
}
```

**Using `calloc`:**

```c
int *array = (int *)calloc(5, sizeof(int));
if (array == NULL) {
    printf("Memory allocation failed\n");
    exit(1);
}
```

**Handling Memory Leaks:**


```c
#include <stdio.h>
#include <stdlib.h>

void createLeak() {
    int *leak = (int *)malloc(5 * sizeof(int));
    // No call to free; causes memory leak
}

int main() {
    createLeak();
    return 0;
}
```

**Key Points:**

- Use `malloc` for uninitialized memory.
- Use `calloc` for zero-initialized memory.
- Use `realloc` to resize allocated memory.
- Use `free` to release allocated memory.
- Use tools like `valgrind` to detect memory leaks.
- Always call `free` for allocated memory.