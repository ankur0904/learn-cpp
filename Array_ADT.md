# Array ADT

```
  ptr
 _A__        ___________________________________________________________
|___| --->  |____||____||____||____||____||____||____||____||____||____|

```

Data
- Array Space
- Size
- Length(no. of elements)

size
- 1. `int A[10]` -> stack
- 2. **good** for creating array for required size
```C++
int *A;
A = new int[size];  // heap - dynamic
```