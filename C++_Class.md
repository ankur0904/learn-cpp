# C++ Class

```C++
class Rectangle
{
private:
    int length;
    int breadth;
public:
    Rectangle()
    {
        length = 0;
        breadth = 0;
    }

    Rectangle(int l, int b)
    {
        length = l;
        breadth = b;
    }

    int area()
    {
        return length*breadth;
    }

    int perimeter()
    {
        return 2*(length+breadth);
    }

    // Setter, mutator
    void setLength(int l)
    {
        length = l;
    }

    // Getter, accessor 
    int getLength()
    {
        return length;
    }

    ~Rectangle()
    {
        cout << "Destructor";
    }
};

int main()
{
    Rectangle r(32,43); // Stack, Destructor called automatically 
    cout << "Area " << r.area() << endl;
    cout << "Perimeter " << r.perimeter() << endl;

    Rectangle* r = new Rectangle(32, 43); // heap, Must call delete r; manually
    cout << "Area " << r->area() << endl;
    cout << "Perimeter " << r->perimeter() << endl;
    
    // Must delete to free memory and call destructor
    delete r;
}
```
