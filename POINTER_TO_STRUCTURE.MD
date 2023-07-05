## Pointer to Structure

`C`
```C
struct Rectangle{
    int length;
    int breadth;
}

int main(){
    struct Rectangle r = {3, 5};
    struct Rectangle *p = &r;  //-> takes only 2 bytes
    r.length = 18;
    (*p).length = 56; //-> () coz precedence
    p->length = 32;
}

```

heap -> dynamic object
stack -> static object

`C`
```C
struct Rectangle{
    int length;
    int breadth;
}

int main(){
    struct Rectangle *p;
    p = (struct Rectangle *)malloc(sizeof(struct Rectangle));  // in heap
    p -> length = 43;
    p -> breadth = 42;
}
```

`C++`
```C++
struct Rectangle{
    int length;
    int breadth;
}

int main(){
    struct Rectangle *p;
    p = new Rectangle;  // in heap
    p -> length = 43;
    p -> breadth = 42;
}
```