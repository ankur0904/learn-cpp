## Structure

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
|                          |
|                          |
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


Definition -> don't consume any memory
```C
struct rectangle{
    int length;
    int breadth;
}
```

Declaration
```C
int main(){
    struct rectangle r = {1, 58}; // -> takes memory 
    r.length = 56;
}
```

- In C++ `struct` keyword is not compulsory, only necessary for the creation of `structure`

only here
```C++
struct rectangle{
    int length;
    int breadth;
}
```
not in here

```C++
int main(){
    rectangle r = {1, 58}; // -> struct not necessary 
    r.length = 56;
}
```
