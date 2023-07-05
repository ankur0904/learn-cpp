## Reference

only feature of C++
- alias to variable


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
|   _a,r_                  |
|   |___|                  |   <------- activation records
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


```Cpp
int main(){
    int a = 3;
    int &r = a;
    cout << a;
    r++;
    cout << a;
    cout << r;
}

```

why??

coz parameter passing