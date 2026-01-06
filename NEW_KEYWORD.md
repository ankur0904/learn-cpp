# The `new` Keyword in C++

## Introduction

The `new` keyword in C++ is used for dynamic memory allocation. It allocates memory on the heap at runtime and returns a pointer to the allocated memory.

## Why Use `new`?

- **Dynamic Memory Allocation**: Allocate memory at runtime when the size is not known at compile time
- **Heap Memory Access**: Access heap memory which has a larger capacity than stack
- **Object Lifetime Control**: Objects created with `new` persist until explicitly deleted
- **Flexible Memory Management**: Create arrays and objects of variable size

## Basic Syntax

### Allocating a Single Variable

```C++
int main(){
    int *p;
    p = new int;        // allocates memory for a single integer
    *p = 10;            // assign value
    
    delete p;           // deallocate memory (important!)
}
```

### Allocating an Array

```C++
int main(){
    int *p;
    p = new int[10];    // allocates memory for 10 integers
    
    delete[] p;         // deallocate array memory
}
```

### Allocating with Initialization

```C++
int main(){
    int *p = new int(5);        // allocates and initializes to 5
    int *arr = new int[5]{1,2,3,4,5};  // allocates and initializes array
    
    delete p;
    delete[] arr;
}
```

## Comparison with C's `malloc`

### C (using malloc)
```C
int main(){
    int *p;
    p = (int *)malloc(10 * sizeof(int));  // typecasting required
    free(p);                              // deallocate
}
```

### C++ (using new)
```C++
int main(){
    int *p;
    p = new int[10];    // no typecasting needed, cleaner syntax
    delete[] p;         // deallocate
}
```

### Key Differences:
- `new` doesn't require typecasting
- `new` is type-safe
- `new` automatically calculates size
- `new` calls constructors for objects
- `malloc` only allocates raw memory

## Using `new` with Structures

### C (malloc)
```C
struct Rectangle{
    int length;
    int breadth;
}

int main(){
    struct Rectangle *p;
    p = (struct Rectangle *)malloc(sizeof(struct Rectangle));
    p -> length = 43;
    p -> breadth = 42;
    free(p);
}
```

### C++ (new)
```C++
struct Rectangle{
    int length;
    int breadth;
}

int main(){
    Rectangle *p;
    p = new Rectangle;  // simpler, no typecasting
    p -> length = 43;
    p -> breadth = 42;
    delete p;
}
```

## Dynamic Array Creation

```C++
int * createArray(int size){
    int *p;
    p = new int[size];  // heap - dynamic allocation
    
    for(int i = 0; i < size; i++){
        p[i] = i+1;
    }
    
    return p;
}

int main(){
    int *arr, n = 5;
    arr = createArray(n);
    
    for(int i = 0; i < n; i++){
        cout << arr[i] << endl;
    }
    
    delete[] arr;  // clean up
    return 0;
}
```

## Memory Management Rules

### Always Remember:
1. **`delete` for single allocation**: `delete ptr;`
2. **`delete[]` for array allocation**: `delete[] arr;`
3. **Avoid memory leaks**: Always deallocate what you allocate
4. **Don't double delete**: Only delete once
5. **Set to nullptr after delete**: `ptr = nullptr;` (good practice)

### Example with Proper Cleanup

```C++
int main(){
    // Single object
    int *p = new int(42);
    delete p;
    p = nullptr;
    
    // Array
    int *arr = new int[10];
    delete[] arr;
    arr = nullptr;
    
    // Structure
    Rectangle *rect = new Rectangle;
    rect -> length = 10;
    rect -> breadth = 5;
    delete rect;
    rect = nullptr;
    
    return 0;
}
```

## Common Use Cases

### 1. Variable-Sized Arrays
```C++
int size;
cout << "Enter size: ";
cin >> size;
int *A = new int[size];  // size determined at runtime
// ... use array ...
delete[] A;
```

### 2. Returning Dynamic Arrays from Functions
```C++
int* func(){
    int *p = new Rectangle;
    p -> length = 443;
    p -> breadth = 34;
    return p;  // object persists after function returns
}
```

### 3. Large Data Structures
```C++
// Allocate large structures on heap instead of stack
LargeStructure *ls = new LargeStructure;
// ... use structure ...
delete ls;
```

## Important Notes

- **Stack vs Heap**: Objects created with `new` are on the heap, regular variables are on the stack
- **Manual Management**: Unlike stack variables, heap memory must be manually freed
- **Exceptions**: `new` throws `std::bad_alloc` exception if allocation fails
- **Modern C++**: Consider using smart pointers (`unique_ptr`, `shared_ptr`) for automatic memory management

## Summary

The `new` keyword is essential for dynamic memory allocation in C++. It provides:
- Type-safe memory allocation
- Cleaner syntax than C's malloc
- Automatic size calculation
- Constructor calling for objects
- Runtime memory allocation flexibility

Remember: **Every `new` should have a corresponding `delete`** to prevent memory leaks!
