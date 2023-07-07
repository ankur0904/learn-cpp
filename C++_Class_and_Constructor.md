## C++ Class and Constructor

```C++
# include <iostream>
using namespace std;

class Rectangle
{
    private:
        int length;
        int breadth;
    public:
        Rectangle(){length = breadth = 1};   // default constructor
        Rectangle(int l, int b);   // parameterized constructor, constructor overloading
        int area();  // facilitators, perform operation on the data members of the object
        int perimeter();  // facilitators, perform operation on the data members of the object
        int getLength(){return length}; // accessor, getter
        void setLength(int l ){ length = l}; // mutator, setter
        ~Rectangle();  // destructor
}
// class name,scope resolution, constructor name
Rectangle::Rectangle(int l, int b)
{
    length = l;
    breadth = b;
}

// return type, class name,scope resolution, function name 
int Rectangle:: area() 
{
    return length * breadth;
}

int Rectangle::Perimeter()
{
    return 2*(length+breadth);
}

Rectangle::~Rectangle()
{

}

int main()
{
    Rectangle r(34,43);
    cout << r.area();
    cout << r.Perimeter();
    r.setLength(45);
}

```
- When the main function will be end , this destructor will be automatically called coz the object is going outside the scope