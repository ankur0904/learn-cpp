# Structure And Function

### Code C

This is the best/highest level of programming which can be done with `C`

```C
struct Rectangle{
    int length;
    int breadth;
}

void initialize(struct Rectangle *r, int l, int b)
{
    r -> length = l;
    r -> breadth = b;
}

int area(struct Rectangle r)
{
    return (r.length*r.breadth)
}

void changeLength(struct Rectangle *r, int l)
{
    r -> length = l;
}

int main()
{
    struct Rectangle r;
    intialize(&r, 43,43);
    area(r);
    changleLength(&r, 432);
}

```

- Grouping data -> structure
- Grouping instruction -> function


### Code C++

#### Time to move to C++

```C++

class Rectangle
{
    private:
       int length;
       int breadth;
    public:
       void initialize(int l, int b)
       {
           length = l;
           breadth = b;
       }
       int area()
       {
           return length*breadth;
       }
       void changeLength(int l)
       {
           length = l;
       }
}

int main()
{
    Rectangle r;  // when you create the rectangle beside the length and breadth, it will also get function related to the class

    r.initialize(4324,5435);
    r.area();
    r.changeLength(54);
}

```

Till now this makes sense


### one improvement `Constructor`

```C++

class Rectangle
{
    private:
       int length;
       int breadth;
    public:
       Rectangle(int l, int b) // Constructor, automatically called when we are creating the object, does the job of initializing the object 
       {
           length = l;
           breadth = b;
       }
       int area()
       {
           return length*breadth;
       }
       void changeLength(int l)
       {
           length = l;
       }
}

int main()
{
    Rectangle r;  // when you create the rectangle beside the length and breadth, it will also get function related to the class

    r.initialize(4324,5435);
    r.area();
    r.changeLength(54);
}

```