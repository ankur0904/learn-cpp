# Template Classes

- C++ supporst generic classes and generic function
- `this` is the pointer to the current/same object.
-  `Generic Classes` 

Code

```C++
class Arithmetic
{
private:
    int a;
    int b;
public:
    Arithmetic(int a, int b);
    int add();
    int sub();
};

Arithmetic::Arithmetic(int a, int b)
{
    // a = a;  // compiler will this `first` a is parameter and `second` a is also parameter
    this -> a = a;
    this -> b = b;
}

int Arithmetic::add()
{
    int c; 
    c = a + b;
    return c;
}

int Arithmetic::sub()
{
    int c; 
    c = a - b;
    return c;
}
```
- This class is for the `int` type suppose you want to support the `float`, `double` etc.
- C++ , you can use the same class for multiple data type but at a time you can use only one data type.
- For any type of data it is called `generic class` and defined as templates

### Templates

```C++
template <class T>
class Arithmetic
{
private:
    T a;
    T b;
public:
    Arithmetic(T a, T b);
    T add();
    T sub();
}; // <------ the effect of template ends here

// whenever you use the class name you should pass template parameter

template <class T>
Arithmetic<T>::Arithmetic(T a, T b)
{
    this -> a = a;
    this -> b = b;
}// <------ the effect of template ends here

template <class T>
T Arithmetic<T>::add()
{
    T c; 
    c = a + b;
    return c;
}

template <class T>
T Arithmetic<T>::sub()
{
    T c; 
    c = a - b;
    return c;
}

int main()
{
    Arithmetic <int> a(10, 453); // integer
    cout << a.add();

    Arithmetic <float> b(43.34,423.3); // float
    cout << b.add(); 
}
```

- `Observation :` wherever `int` is present we change to `T` in this case but it is **not** true for all the case, you have to check based on the condition _for example_ `c = a + b` if `a` & `b` is `T` then `c` must be `T`

