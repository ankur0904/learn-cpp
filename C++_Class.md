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
    Rectangle r(32,43);
    cout << "Area " << r.area() << endl;
    cout << "Perimeter " << r.perimeter() << endl;
}
```