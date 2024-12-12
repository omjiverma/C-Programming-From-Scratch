## **6: Pointers**

Pointers are variables that store the memory address of another variable. They are a powerful feature of C that provides flexibility and control over memory management.
#### **1. Pointer Basics**

##### **Declaration and Dereferencing**

- **Declaration**:
- A pointer is declared by specifying the data type it points to and using the `*` symbol.
- **Syntax**:

```c
data_type *pointer_name;
```

- **Example**:
```c
int *ptr;  // Declares a pointer to an integer
```

- **Initialization**:

- A pointer is assigned the address of a variable using the address-of operator (`&`).

```c
int x = 10; int *ptr = &x;  // Pointer points to the address of x`
```

- **Dereferencing**:

- Access or modify the value stored at the memory address using the dereference operator (`*`).
```c
int x = 10; 
int *ptr = &x; 
printf("%d\n", *ptr);  
// Outputs: 10 
*ptr = 20;     // Modifies x through the pointer         
printf("%d\n", x);     // Outputs: 20
```


##### **Pointer Arithmetic**

- Pointer arithmetic allows manipulation of addresses.
- Operations:
- **Increment (`ptr++`)**: Moves to the next element.
- **Decrement (`ptr--`)**: Moves to the previous element.
- **Addition/Subtraction (`ptr + n`, `ptr - n`)**: Moves `n` positions forward or backward.
- **Example**:

```c
   int arr[3] = {10, 20, 30}; 
   int *ptr = arr; printf("%d\n", *ptr);      
   // Outputs: 10 
   ptr++; 
   printf("%d\n", *ptr);      
   // Outputs: 20`
```

**Key Notes**:

- Pointer arithmetic depends on the size of the data type.
- For an integer pointer, `ptr++` increments the address by 4 bytes (on a 32-bit system).
#### **2. Pointers and Arrays**

##### **Relationship between Arrays and Pointers**

- An array name acts as a pointer to the first element.
- **Example**:  
```c
// Array name is the address of arr[0] 
int arr[3] = {10, 20, 30}; 
int *ptr = arr;  
printf("%d\n", *(ptr + 1));  // Outputs: 20

```

- **Key Equivalence**:
```c
arr[i] == *(arr + i)  // Accessing elements via pointers`
```
##### **Passing Arrays to Functions**

- Arrays are always passed by reference to functions.
- **Example**:
```c
void printArray(int *arr, int size){     
    for (int i = 0; i < size; i++){
        printf("%d ", arr[i]);     
    } 
}  
int main(){
    int arr[3] = {10, 20, 30};     
    printArray(arr, 3);  // Passes the base address of arr     
    return 0; 
}
```

#### **3. Advanced Pointer Concepts**

##### **Pointers to Pointers**

- A pointer to a pointer stores the address of another pointer.
- Useful in dynamic memory allocation and multi-level indirection.
- **Syntax**:
```c
data_type **pointer_to_pointer;
```
- **Example**:
```c
int x = 10; 
int *ptr = &x; 
int **pptr = &ptr; 
printf("%d\n", **pptr);  
// Outputs: 10`
```

##### **Function Pointers**

- Function pointers store the address of a function and allow dynamic function calls.
- **Syntax**:
```c
return_type (*pointer_name)(parameter_list);
```

- **Example**:
```c
void greet() {
	printf("Hello, World!\n"); 
}  

int main(){ 
    void (*funcPtr)() = greet;  // Assigns address of greet to funcPtr
    funcPtr(); 
    // Calls greet via pointer     
    return 0; 
}
```

- **Applications**:
- Callback mechanisms.
- Dynamic function dispatch.
- Building menu-driven programs.



### **Summary**

|**Concept**|**Key Takeaways**|
|---|---|
|Declaration|Use `*` to declare a pointer to a data type.|
|Dereferencing|Access or modify the value at the pointed address.|
|Arithmetic|Perform address calculations using `++`, `--`.|
|Arrays and Pointers|Arrays act as pointers; use arithmetic for access.|
|Passing Arrays|Pass base address to functions.|
|Pointers to Pointers|Store address of another pointer for multi-level indirection.|
|Function Pointers|Point to functions for dynamic calls.|