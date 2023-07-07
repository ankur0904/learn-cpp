## Structure as Parameter.

- Call by value make the copy of the variable 

### Call by value

```C

struct Rectangle
{
    int length;
    int breadth; 
}

int area(struc Rectangle rec)
{
    return (rec.length*rec.breadth);
}


int main()
{
    struct Rectangle re = {10, 5};
    printf("%d", area(re));
}
```

### Call by reference

```C++

struct Rectangle
{
    int length;
    int breadth; 
}

int area(struc Rectangle &rec)
{
    return (rec.length*rec.breadth);
}


int main()
{
    struct Rectangle re = {10, 5};
    printf("%d", area(re));
}
```

### Call by address

```C

struct Rectangle
{
    int length;
    int breadth; 
}

void changeLength(struct Rectangle *p, int len)
{
    p -> length = len;
}


int main()
{
    struct Rectangle re = {105, 55};
    changeLength(&re, 54);
}
```

## !!! IMPORTANT

- YOU CAN PASS BY VALUE IN `STRUCTURE` EVEN IT HAVE _ARRAY INSIDE_


```C
struct Test
{
    int A[5];
    int n;
}

void func(struct Test te)
{
    te.A[0] = 10;   // do't reflect to original array in main
    te.A[1] = 20;   // do't reflect to original array in main
}

int main()
{
    struct Test test = {{1,2,3,4,5}, 5};
    func(test);
}
```
