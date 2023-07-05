## Pointers

store the address of the variables

why need? 
- coz program will not directly access the heap memory
- ... access external resources 
- parameter passing

```
main memory
____________________________
|                          |
|                          |
|  heap                    |
|                          |
____________________________
|                          |
|                          |
|  stack                   |
|                          |
|   __a__        __p__     |
|   |___|        |___|     |
____________________________
|                          |
|                          |
|                          |
|     code section         |
|                          |
|                          |
|                          |
____________________________
```

```C
int main(){
    int a = 5;
    int *p;     -> only two bytes, declaration
    p = &a;         -> initialization

    // accessing data via pointer
    printf("%d", *p);   -> dereferencing
}
```
C
```C
// how to create a memory in heap, a function called malloc
int main(){
    int *p;
    // malloc(10 * sizeof(int)) -> void pointer, we need to typecast it (in this case (int *))
    p = (int *) malloc(10 * sizeof(int));
}
```

In C++

```C++
int main(){
    int *p;
    p = new int[10]; // easy
}
```