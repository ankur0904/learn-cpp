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