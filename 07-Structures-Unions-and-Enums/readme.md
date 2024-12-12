## **7: Structures, Unions, and Enums**

C provides user-defined data types for organizing data and improving code readability. This unit covers Structures, Unions, and Enumerations (Enums).
### **1. Structures

**Definition and Initialization**

- A structure groups variables of different data types into a single unit.
- **Syntax:**
```c
struct StructureName {
  data_type member1;
  data_type member2;
};
```

- **Example:**
```c
struct Point {
  int x;
  int y;
};
```

**Structure Declaration and Initialization:**

- Declare variables after structure definition.
- **Example:**

```c
struct Point p1 = {10, 20}; // Initialize values
struct Point p2;            // Uninitialized
p2.x = 5;                   // Assign values manually
p2.y = 15;
```

**Accessing Members:**

- Use the dot operator (.) for direct access.
```c
struct Point p1 = {10, 20};
printf("x: %d, y: %d\n", p1.x, p1.y);
```

**Pointer to Structure:**

- Use the arrow operator (->) to access members via a pointer.
```c
struct Point p1 = {10, 20};
struct Point *ptr = &p1;
printf("x: %d, y: %d\n", ptr->x, ptr->y);
```

**Key Features:**

- Structures can contain other structures, arrays, or pointers as members.
- **Example (Nested Structure):**
```c
struct Rectangle {
  struct Point topLeft;
  struct Point bottomRight;
};
```

### **2. Unions**

**Memory Sharing**
- A union shares memory among all its members.
- Only one member can hold a value at any time.

**Definition:**
```c
union UnionName {
  data_type member1;
  data_type member2;
};
```

- **Example:**
```c
union Data {
  int i;
  float f;
  char str[20];
};
```

**Size of a Union:**

- Equal to the size of its largest member.

**Usage Example:**
```c
union Data d;
d.i = 10;
printf("i: %d\n", d.i);
d.f = 3.14;
printf("f: %.2f\n", d.f); // Overwrites `i`
```

**Applications:**

- Efficient memory usage (e.g., reading sensor data)
- Representing multiple data types in a single location

### 3. Enumerations (Enums)

**Defining and Using Enums**

- Define a set of named integral constants.

**Syntax:**

```c
enum EnumName {
  constant1,
  constant2,
};
```

- **Example:**
```c
enum Days {SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY};
```

**Assigning Values:**

- Constants start at 0 by default, but custom values can be assigned.
```c
enum Days {SUNDAY = 1, MONDAY, TUESDAY}; // MONDAY = 2, TUESDAY = 3
```

**Accessing Enum Values:**

- Enum variables hold integer values corresponding to named constants.

```c
enum Days today = MONDAY;
printf("Day: %d\n", today);  // Outputs: 1
```

**Applications:**

- Readable code: Replace magic numbers with meaningful names.
- State representation: (e.g., Traffic Lights)
```c
enum TrafficLight {RED, YELLOW, GREEN};
enum TrafficLight current = GREEN;
```

### Comparison: Structures vs. Unions

|Aspect|Structures|Unions|
|---|---|---|
|Memory|Each member has its own memory space.|All members share the same memory.|
|Size|Sum of the sizes of all members.|Size of the largest member.|
|Use Case|Group related variables.|Save memory when only one member is|
|||active at a time.|

## Key Takeaways

- Structures group related data of different types.
- Unions share memory for efficiency when only one member is active.
- Enums define named constants for clarity and readability.