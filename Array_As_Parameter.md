## Array as Parameter

- Array can't be passed by value nor reference it can only be passed by `address` only in C as well as C++

```C
void func(int A[], int n){  // A -> address, n -> copy the value
    // do operation
}

int main(){
    int A[5] = {4,5,2,3,6};
    func(A, 8);
}
```

or

```C
void func(int *A, int n){
    cout << sizeof(A)/sizeof(int) << endl;  // -> return the size of pointer
    // do operation
}

int main(){
    int A[5] = {4,5,2,3,6};
    func(A, 8);
    cout << sizeof(A)/sizeof(int) << endl; // -> return the size of array
}
```

Note: 
- `int A[]` points to array only and `int *A` can points to any address.
- Changes in array in function will reflect to the main array.


### **Return array from the function**

```C
int * func(int n){
    int *p;
    p = (int *)malloc(n*sizeof(int));   // C
    return (p);
}

int main(){
    int *A;
    A = func(45);
}
```

- We can't use foreach loop in the pointer
```C++
for(int a: A)
```


C++ code

```C++
int * fun(int size){
    int *p;
    p = new int[size];

    for(int i = 0; i < size; i++){
        p[i] = i+1;
    }

    return p;
}

int main(){
    int *ptr, n = 5;

    ptr = fun(n);

    for(int i = 0; i < n; i++){
        cout << ptr[i] << endl;
    }

    return 0;
}

```