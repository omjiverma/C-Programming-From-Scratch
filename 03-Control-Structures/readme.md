## **Control Structures**

Control structures in C dictate the flow of program execution. They are essential for decision-making, looping, and handling specific program instructions.

### Conditional Statements

Conditional statements enable the program to make decisions based on conditions.

**1. if Statement** Executes a block of code if the condition evaluates to true (non-zero).

```
if (condition) {
    // Code to execute if condition is true
}
```

**Example:**

```
int a = 10;
if (a > 5) {
    printf("a is greater than 5\n");
}
```
**2. if-else Statement** Provides an alternative block of code if the condition is false.

```
if (condition) {
    // Code if condition is true
} else {
    // Code if condition is false
}
```

**Example:**

```
int a = 3;
if (a > 5) {
    printf("a is greater than 5\n");
} else {
    printf("a is less than or equal to 5\n");
}
```

**3. switch Statement** Used to select one block of code to execute from multiple options.

```
switch (expression) {
    case constant1:
        // Code for case 1
        break;
    case constant2:
        // Code for case 2
        break;
    default:
        // Code if no cases match
}
```

**Example:**

```
int choice = 2;
switch (choice) {
    case 1:
        printf("Option 1 selected\n");
        break;
    case 2:
        printf("Option 2 selected\n");
        break;
    default:
        printf("Invalid option\n");
}
```

**Key Notes:**

- Use `break` to exit a switch block after executing a case.
- The `default` case is optional but recommended.

### Loops

Loops allow repetitive execution of code blocks until a specified condition is met.

**1. for Loop** Used when the number of iterations is known.

```
for (initialization; condition; increment/decrement) {
    // Code to execute
}
```

**Example:**

```
for (int i = 1; i <= 5; i++) {
    printf("Iteration %d\n", i);
}
```

**2. while Loop** Repeats as long as the condition remains true.
```
while (condition) {
    // Code to execute
}
```

**Example:**

```
int i = 1;
while (i <= 5) {
    printf("Iteration %d\n", i);
    i++;
}
```

**3. do-while Loop** Executes the block at least once before checking the condition.

```
do {
    // Code to execute
} while (condition);
```

**Example:**

```
int i = 1;
do {
    printf("Iteration %d\n", i);
    i++;
} while (i <= 5);
```

### Other Control Keywords

Control keywords modify the behavior of loops and decision structures.

**1. break** Terminates the nearest enclosing loop or switch statement.

**Example:**

```
for (int i = 1; i <= 5; i++) {
    if (i == 3) break;
    printf("i = %d\n", i);
}
```

**2. continue** Skips the current iteration and continues with the next iteration of the loop.

**Example:**

```
for (int i = 1; i <= 5; i++) {
    if (i == 3) continue;
    printf("i = %d\n", i);
}
```


**3. goto** Transfers control to a labeled statement elsewhere in the code.

**Syntax:**

```
goto label;
// Other code
label:
// Code at label
```


**Example:**

```
int i = 1;
start:
if (i <= 5) {
    printf("Iteration %d\n", i);
    i++;
    goto start;
}
```

**Key Notes:**

- Use `goto` sparingly as it can make code harder to read and debug.