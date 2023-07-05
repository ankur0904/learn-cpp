##### Pass by value

```C
void swap(int x, int y){
    int tmp = x;
    x = y;
    y = tmp;
}

int main(){
    int a, b;
    a = 53;
    b = 23;
    swap(a, b);
    printf("%d %d", a, b);
}
```

##### Call by address

```C
void swap(int *x, int *y){
    int tmp = *x;
    *x = *y;
    *y = tmp;
}

int main(){
    int a, b;
    a = 53;
    b = 23;
    swap(&a, &b);
    printf("%d %d", a, b);
}
```

##### Call by references(only in C++)

references don't take any memory

- one function cann't access the variable of another function directly, it can access indirectly
- in the memory `swap` became the part of the main function, like this(depends on compiler)
- ```
  main
  ...
  ...
  ...
  .swap
   ...
   ...
  ...
  ...
  ```
 ``` 
 a/x     b/y
 |__|    |__|     
 ```



```C++
void swap(int &x, int &y){
    int tmp = x;
    x = y;
    y = tmp;
}

int main(){
    int a, b;
    a = 53;
    b = 23;
    swap(a, b);
    printf("%d %d", a, b);
}
``` 

- NOTE: *Machine code is monolithic but the source code is procedure
- must be used carefully, not always nor on big function.