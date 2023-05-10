# Polymorphism

1. Polymorphism allows objects of different types to be treated as objects of a common base type.
2. It enables writing code that can operate on objects of multiple classes without the need for explicit type checking.
3. Polymorphism is achieved through method overriding and method overloading.
4. Method overriding involves creating a method in a derived class that has the same name, return type, and parameters as a method in its base class.
5. When a method is invoked on an object of the derived class, the overridden method in the derived class is executed instead of the base class method.
6. Method overloading involves defining multiple methods with the same name but different parameters within a class.
7. The appropriate method is selected at compile-time based on the arguments provided during method invocation.
8. Polymorphism promotes code reusability, modularity, and flexibility in software design.
9. It allows for specialized behavior to be implemented in derived classes while maintaining a common interface through inheritance.
10. Polymorphism simplifies adding new types or modifying existing ones without impacting the existing code that uses the base type.

In essence, polymorphism in OOP allows for writing flexible and reusable code by treating objects of different types as objects of a common base type, utilizing method overriding and method overloading to achieve specialized behavior and code flexibility.

#### Example
Here's an example of polymorphism in object-oriented programming (OOP) using a base class called `Shape` and two derived classes `Circle` and `Rectangle`:

```cpp
#include <iostream>

using namespace std;

// Base class
class Shape {
public:
    virtual void draw() {
        cout << "Drawing a shape" << endl;
    }
};

// Derived class 1
class Circle : public Shape {
public:
    void draw() {
        cout << "Drawing a circle" << endl;
    }
};

// Derived class 2
class Rectangle : public Shape {
public:
    void draw() {
        cout << "Drawing a rectangle" << endl;
    }
};
```

In this example, the `Shape` class is the base class, which has a virtual `draw()` method. The `Circle` and `Rectangle` classes are derived from the `Shape` class and override the `draw()` method with their own implementation.

Here's how polymorphism can be demonstrated using these classes:

```cpp
int main() {
    Shape* shape1 = new Circle();
    Shape* shape2 = new Rectangle();

    shape1->draw();  // Calls the draw() method of the Circle class
    shape2->draw();  // Calls the draw() method of the Rectangle class

    delete shape1;
    delete shape2;

    return 0;
}
```

In the `main()` function, two pointers of type `Shape*` are created. The first pointer `shape1` points to an object of the `Circle` class, and the second pointer `shape2` points to an object of the `Rectangle` class.

When the `draw()` method is called on each pointer, polymorphism comes into play. The appropriate `draw()` method of the derived class is invoked based on the actual type of the object being pointed to. This means that `shape1->draw()` calls the `draw()` method of the `Circle` class, and `shape2->draw()` calls the `draw()` method of the `Rectangle` class.

Polymorphism allows objects of different types, but related through inheritance, to be treated as objects of their common base type (`Shape` in this case). This enables writing flexible and reusable code that can work with different derived classes through a common interface, without the need for explicit type checking.