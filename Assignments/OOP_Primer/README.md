####Ethan Krchnak; OOP_PRIMER

1. Abstract Classes and Interfaces
Abstract Classes: A class that cannot be instantiated and may contain abstract methods (methods without implementation).
Example:
cpp
Copy code
class Animal {
public:
    virtual void makeSound() = 0; // Abstract method
};
class Dog : public Animal {
public:
    void makeSound() override {
        cout << "Woof!" << endl;
    }
};
Interfaces: A contract that defines methods that must be implemented by any class that "implements" it.
Example:
cpp
Copy code
class Shape {
public:
    virtual void draw() = 0;
};
class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing Circle" << endl;
    }
};
2. Abstraction
Hiding complex implementation details and showing only the essential functionality.
Example:
cpp
Copy code
class Car {
public:
    void start() {
        turnKey();
        engineStart();
    }
private:
    void turnKey() { cout << "Turning key." << endl; }
    void engineStart() { cout << "Starting engine." << endl; }
};
3. Access Modifiers (Public, Private, Protected)
Control the visibility of class members (variables/methods).
public: Accessible anywhere.
private: Accessible only within the class.
protected: Accessible within the class and derived classes.
Example:
cpp
Copy code
class MyClass {
private:
    int x;
public:
    void setX(int val) { x = val; }
    int getX() { return x; }
};
4. Attributes / Properties
Attributes are data members of a class. Properties often have getters and setters for accessing attributes.
Example:
cpp
Copy code
class Person {
private:
    string name;
public:
    string getName() { return name; }
    void setName(string n) { name = n; }
};
5. Class Variable
A variable that is shared by all instances of a class, declared with static.
Example:
cpp
Copy code
class Counter {
public:
    static int count; // Class variable
    void increment() { count++; }
};
int Counter::count = 0; // Initialization
6. Classes and Objects
Class: Blueprint for creating objects.
Object: An instance of a class.
Example:
cpp
Copy code
class Dog {
public:
    void bark() { cout << "Woof!" << endl; }
};
Dog d;
d.bark();  // Object d calls the method
7. Collections and Iterators
Collections are data structures (e.g., lists, arrays).
Iterators are objects that allow you to iterate over a collection.
Example:
cpp
Copy code
vector<int> nums = {1, 2, 3};
for (auto it = nums.begin(); it != nums.end(); ++it) {
    cout << *it << " "; // Iterating through vector
}
8. Composition
A type of association where one class contains objects of other classes.
Example:
cpp
Copy code
class Engine {
public:
    void start() { cout << "Engine starting..." << endl; }
};
class Car {
private:
    Engine engine; // Composition
public:
    void startCar() { engine.start(); }
};
9. Constructors and Destructors
Constructor: A special method used to initialize objects.
Destructor: A special method used to clean up when an object is destroyed.
Example:
cpp
Copy code
class Car {
public:
    Car() { cout << "Car created!" << endl; } // Constructor
    ~Car() { cout << "Car destroyed!" << endl; } // Destructor
};
10. Design Patterns (e.g., Singleton, Factory, Observer)
Singleton: A design pattern ensuring a class has only one instance.
Example:
cpp
Copy code
class Singleton {
private:
    static Singleton* instance;
    Singleton() {}
public:
    static Singleton* getInstance() {
        if (!instance) instance = new Singleton();
        return instance;
    }
};
11. Encapsulation
The concept of bundling data and methods that operate on the data within a class and restricting access to some of the object's components.
Example:
cpp
Copy code
class BankAccount {
private:
    double balance;
public:
    void deposit(double amount) { balance += amount; }
    double getBalance() { return balance; }
};
12. Exception Handling
The mechanism to handle runtime errors, usually using try, catch, and throw.
Example:
cpp
Copy code
try {
    int x = 10 / 0;  // Throws exception
} catch (const std::exception& e) {
    cout << "Error: " << e.what() << endl;
}
13. File I/O in OOP
Reading from and writing to files.
Example:
cpp
Copy code
#include <fstream>
ofstream file("example.txt");
file << "Hello, world!" << endl;
file.close();
14. Friends
Friend classes/functions can access private and protected members of a class.
Example:
cpp
Copy code
class Box {
private:
    double width;
public:
    Box() { width = 5; }
    friend void printWidth(Box b); // Friend function
};
void printWidth(Box b) {
    cout << "Width: " << b.width << endl;
}
15. Generics and Templates
Generics (in languages like Java) and Templates (in C++) allow writing code that works with any data type.
Example:
cpp
Copy code
template <typename T>
T add(T a, T b) { return a + b; }
16. Inheritance
A mechanism where a new class inherits properties and behaviors from an existing class.
Example:
cpp
Copy code
class Animal {
public:
    void speak() { cout << "Animal speaks!" << endl; }
};
class Dog : public Animal {
public:
    void speak() { cout << "Woof!" << endl; }
};
17. Instance Variable / Member Variable
Variables that belong to an instance (object) of a class.
Example:
cpp
Copy code
class Person {
public:
    string name; // Member variable
};
18. Memory Management (Garbage Collection, Pointers)
Garbage Collection: Automatic memory management.
Pointers: Variables that hold memory addresses.
Example (using pointers):
cpp
Copy code
int *ptr = new int(10);
delete ptr; // Memory deallocation
19. Method Overloading
Defining multiple methods with the same name but different parameters.
Example:
cpp
Copy code
class Calculator {
public:
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; }
};
20. Method
A function that is associated with an object or class.
Example:
cpp
Copy code
class Car {
public:
    void start() { cout << "Starting car!" << endl; }
};
21. Multiple Inheritance
A class can inherit from more than one class.
Example:
cpp
Copy code
class Animal {
public:
    void eat() { cout << "Eating" << endl; }
};
class Bird {
public:
    void fly() { cout << "Flying" << endl; }
};
class Sparrow : public Animal, public Bird {};
22. Multithreading in OOP (time permitting)
Running multiple threads (independent units of execution) in a program.
Example:
cpp
Copy code
#include <thread>
void printHello() { cout << "Hello, World!" << endl; }
int main() {
    std::thread t(printHello);
    t.join();
}
23. Object Relationships (Association, Aggregation, Composition)
Association: A general relationship between objects.
Aggregation: A "has-a" relationship but objects can exist independently.
Composition: A "contains-a" relationship where objects cannot exist independently.
Example:
cpp
Copy code
class Engine {};  // Aggregation/Composition
class Car {
private:
    Engine engine;  // Composition
public:
    void start() { cout << "Car starting" << endl; }
};
24. Object-Oriented Design Principles
Principles like SOLID, DRY, KISS, etc., that guide the structure and organization of code.
25. Operator Overloading
Defining new behavior for operators like +, -, etc., for custom classes.
Example:
cpp
Copy code
class Point {
public:
    int x, y;
    Point operator+(const Point& p) {
        return Point{x + p.x, y + p.y};
    }
};
26. Overloading
Creating multiple methods or operators with the same name but different signatures (number or types of parameters).
Example (method overloading shown above).
27. Polymorphism
Ability to call the same method on different objects, and it will behave differently based on the object.
Example:
cpp
Copy code
class Animal {
public:
    virtual void speak() { cout << "Animal sound" << endl; }
};
class Dog : public Animal {
public:
    void speak() override { cout << "Woof!" << endl; }
};
28. Public / Private / Protected
Access control for class members (explained under Access Modifiers).
29. SOLID Principles
Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion.
30. Static (Methods and Variables)
Static methods and variables belong to the class, not to instances.
Example:
cpp
Copy code
class Counter {
public:
    static int count;
    static void increment() { count++; }
};
31. Testing in OOP (Unit Testing, Test-Driven Development)
Writing tests for individual methods and classes to ensure correctness.
32. UML Diagrams and Modeling
UML is a standard way to visualize the design of a system, using diagrams like class, sequence, and use-case diagrams.
33. Virtual
The virtual keyword allows a method to be overridden in derived classes, enabling runtime polymorphism.
Example:
cpp
Copy code
class Base {
public:
    virtual void show() { cout << "Base class" << endl; }
};
class Derived : public Base {
public:
    void show() override { cout << "Derived class" << endl; }
};
