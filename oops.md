It's a programming paradigm that is based on set of rules, concepts, idea, basically a standard in programming used to solve specific type of problems.

- represent real life entity with their attributes.

```C++
# include <iostream>
using std::string;

class Employee {
public:
    string name;
    string company;
    int age;

    void greet(){
        std:: cout << "Hi, my name is " + name << std::endl;
    }
};

int main()
{
    Employee employee1;
    employee1.name = "John";
    employee1.company = "Google";
    employee1.age = 25;
    employee1.greet();

    Employee employee2;
    employee2.name = "Jane";
    employee2.company = "Amazon";
    employee2.age = 35;
    employee2.greet();
}

```

Note:
    - Everything inside class in cpp is private by default.
    - in cpp we have 3 access modifier
        1. private - cann't access outside the class
        2. public
        3. protected - btw private and public


Constructor is special type of function that is invoked each time when object of the class is created.
Default constructor is  a constructor which actomatically generated by the compiler.
    - constructor have no return type.
    - have same name as class name
    - must be public (but can changes as needed)

    ```C++
# include <iostream>
using std::string;

class Employee {
public:
    string name;
    string company;
    int age;
    // Parameterized constructor
    Employee(string Name, string Company, int Age){
        name = Name;
        company = Company;
        age = Age;

    }
    // Deefault constructor when no parameters are passed
    Employee(){

    }
    void greet(){
        std:: cout << "Hi, my name is " + name << std::endl;
    }
};

int main()
{
    Employee employee1("John", "Google", 25);
    
    employee1.greet();

    Employee employee2("Jane", "Amazon", 35);
    employee2.greet();
}
    ```

    - Encapsulation: the idea of bundling, tying together data & methods that operate on that data
    - the purpose is to prevent anyone from outside from the class to directly access the data & modify it.
    - concept of setter, getter

    ```C++
        # include <iostream>
using std::string;

class Employee {
private:
    // encapsulated properties
    string name;
    string company;
    int age;

public:
    // setter name
    void setName(string Name){
        name = Name;
    }
    // getter name
    string getName(){
        return name;
    }
    // setter company
    void setCompany(string Company){
        company = Company;
    }
    // getter company
    string getCompany(){
        return company;
    }
    // setter age
    void setAge(int Age){
        if (Age >= 18){
            age = Age;
        }
    }
    // getter age
    int getAge(){
        return age;
    }
    // Parameterized constructor
    Employee(string Name, string Company, int Age){
        name = Name;
        company = Company;
        age = Age;

    }
    // Deefault constructor when no parameters are passed
    Employee(){

    }
    void greet(){
        std:: cout << "Hi, my name is " + name << std::endl;
    }
};

int main()
{
    Employee employee1("John", "Google", 25);
    employee1.setAge(43);
    std::cout << employee1.getAge() << std::endl;
    employee1.greet();

    Employee employee2("Jane", "Amazon", 35);
    employee2.greet();
}
    ```

    - Abstraction: hiding the complex things behind a procedure that makes those things look simple.
    e.g, clicking the photo on camera, we don't know how the camera is capturing the photo, we just click the button and photo is captured, complex things are hidden behind the button click.

    ```C++
# include <iostream>
using std::string;

// Abstraction class
class AbstractEmployee{
    // Pure virtual function - virtual class is a class that has one or more pure virtual functions & virtual 
    // function is a function that can be overridden in a derived class
    virtual void askForPromotion() = 0;
};

// employee class that inherits from AbstractEmployee, employee class provide implementation for the pure virtual function
class Employee:AbstractEmployee {
private:
    // encapsulated properties
    string name;
    string company;
    int age;

public:
    // setter name
    void setName(string Name){
        name = Name;
    }
    // getter name
    string getName(){
        return name;
    }
    // setter company
    void setCompany(string Company){
        company = Company;
    }
    // getter company
    string getCompany(){
        return company;
    }
    // setter age
    void setAge(int Age){
        if (Age >= 18){
            age = Age;
        }
    }
    // getter age
    int getAge(){
        return age;
    }
    // Parameterized constructor
    Employee(string Name, string Company, int Age){
        name = Name;
        company = Company;
        age = Age;

    }
    // Deefault constructor when no parameters are passed
    Employee(){

    }
    void greet(){
        std:: cout << "Hi, my name is " + name << std::endl;
    }

    
    void askForPromotion(){
        if (age > 30){
            std::cout << name << " got promoted!" << std::endl;
        } else {
            std::cout << name << " sorry, no promotion for you!" << std::endl;
        }
    }
};

int main()
{
    Employee employee1("John", "Google", 25);
    Employee employee2("Jane", "Amazon", 35);
    
    employee2.askForPromotion();
}
    ```

    - Inheritance: inheritance is a mechanism in which one object acquires all the properties and behaviors of parent object.
    e.g, car -> parent class, super class, base class
            - electric car -> child class, sub class, derived class
            - disel car -> child class, sub class, derived class

    ```C++
# include <iostream>
using std::string;

// Abstraction class
class AbstractEmployee{
    // Pure virtual function - virtual class is a class that has one or more pure virtual functions & virtual 
    // function is a function that can be overridden in a derived class
    virtual void askForPromotion() = 0;
};

// employee class that inherits from AbstractEmployee, employee class provide implementation for the pure virtual function
class Employee:AbstractEmployee {
private:
    // encapsulated properties
    string company;
    int age;
protected:
    string name;
public:
    // setter name
    void setName(string Name){
        name = Name;
    }
    // getter name
    string getName(){
        return name;
    }
    // setter company
    void setCompany(string Company){
        company = Company;
    }
    // getter company
    string getCompany(){
        return company;
    }
    // setter age
    void setAge(int Age){
        if (Age >= 18){
            age = Age;
        }
    }
    // getter age
    int getAge(){
        return age;
    }
    // Parameterized constructor
    Employee(string Name, string Company, int Age){
        name = Name;
        company = Company;
        age = Age;

    }
    // Deefault constructor when no parameters are passed
    Employee(){

    }
    void greet(){
        std:: cout << "Hi, my name is " + name << std::endl;
    }

    
    void askForPromotion(){
        if (age > 30){
            std::cout << name << " got promoted!" << std::endl;
        } else {
            std::cout << name << " sorry, no promotion for you!" << std::endl;
        }
    }
};

// default constructor of Developer class overwritten due to inheritance if paraent not have default constrcutor, 
// it also inherits constructor from Employee class
// Inheritance is private by default, so we need to make it public to access the properties of Employee class
class Develper: public Employee{
    public:
        string favProgrammingLanguage;
        Develper(string Name, string Company, int Age, string FavProgrammingLanguage):Employee(Name, Company, Age){
            favProgrammingLanguage = FavProgrammingLanguage;
        }
        void fixBug(){
            std::cout << name << " fixed bug using " << favProgrammingLanguage << std::endl;
        }
        // Note: private properties of Employee class are not accessible in Developer class, then *protected* come into picture
};

class Teacher: public Employee{
    public:
        string subject;
        void prepareLesson(){
            std::cout << name << " is preparing " << subject << " lesson" << std::endl;
        }
        Teacher(string Name, string Company, int Age, string Subject):Employee(Name, Company, Age){
            subject = Subject;
        }
};

int main()
{    
    Develper d = Develper("Jack", "Facebook", 30, "Python");
    Teacher t = Teacher("John", "School", 35, "History");
    t.askForPromotion();
}
    ```


    - Polymorphism: poly means many, morphism means forms, so polymorphism means many forms.
     In the parent class, we have a method, and in the child class, we have the same method with different implementation.
     the most common use of polymorphism is when a parent class reference is used to refer to a child class object.
     ```C++
# include <iostream>
using std::string;

// Abstraction class
class AbstractEmployee{
    // Pure virtual function - virtual class is a class that has one or more pure virtual functions & virtual 
    // function is a function that can be overridden in a derived class
    virtual void askForPromotion() = 0;
};

// employee class that inherits from AbstractEmployee, employee class provide implementation for the pure virtual function
class Employee:AbstractEmployee {
private:
    // encapsulated properties
    string company;
    int age;
protected:
    string name;
public:
    // setter name
    void setName(string Name){
        name = Name;
    }
    // getter name
    string getName(){
        return name;
    }
    // setter company
    void setCompany(string Company){
        company = Company;
    }
    // getter company
    string getCompany(){
        return company;
    }
    // setter age
    void setAge(int Age){
        if (Age >= 18){
            age = Age;
        }
    }
    // getter age
    int getAge(){
        return age;
    }
    // Parameterized constructor
    Employee(string Name, string Company, int Age){
        name = Name;
        company = Company;
        age = Age;

    }
    // Deefault constructor when no parameters are passed
    Employee(){

    }
    void greet(){
        std:: cout << "Hi, my name is " + name << std::endl;
    }

    
    void askForPromotion(){
        if (age > 30){
            std::cout << name << " got promoted!" << std::endl;
        } else {
            std::cout << name << " sorry, no promotion for you!" << std::endl;
        }
    }
    //  virtual function can be overridden in a derived class, it'll check if function is present in derived class or not
    virtual void Work(){
        std::cout << name << " is checking email" << std::endl;
    }
};

// default constructor of Developer class overwritten due to inheritance if paraent not have default constrcutor, 
// it also inherits constructor from Employee class
// Inheritance is private by default, so we need to make it public to access the properties of Employee class
class Develper: public Employee{
    public:
        string favProgrammingLanguage;
        Develper(string Name, string Company, int Age, string FavProgrammingLanguage):Employee(Name, Company, Age){
            favProgrammingLanguage = FavProgrammingLanguage;
        }
        void fixBug(){
            std::cout << name << " fixed bug using " << favProgrammingLanguage << std::endl;
        }
        // Note: private properties of Employee class are not accessible in Developer class, then *protected* come into picture
        void Work(){
            std::cout << name << " is writing " << favProgrammingLanguage << " code" << std::endl;
        }
};

class Teacher: public Employee{
    public:
        string subject;
        void prepareLesson(){
            std::cout << name << " is preparing " << subject << " lesson" << std::endl;
        }
        Teacher(string Name, string Company, int Age, string Subject):Employee(Name, Company, Age){
            subject = Subject;
        }
        void Work(){
            std::cout << name << " is teaching " << subject << std::endl;
        }
};

int main()
{    
    Develper d = Develper("Jack", "Facebook", 30, "Python");
    Teacher t = Teacher("John", "School", 35, "History");
    
    Develper* dPtr = &d;
    Teacher* tPtr = &t;

    dPtr->Work();
    tPtr->Work();  
}
     ```


     More about `this` keyword: https://www.geeksforgeeks.org/this-pointer-in-c/