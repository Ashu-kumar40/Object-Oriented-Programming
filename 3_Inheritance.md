# Inheritance
Certainly! Here's a concise explanation of inheritance in OOP in point form:

1. Inheritance is a fundamental concept in object-oriented programming (OOP) that allows the creation of new classes based on existing classes.
2. It enables code reuse by allowing new classes (derived classes) to inherit the properties and behavior of existing classes (base classes).
3. The derived class is also known as the child class, and the base class is also known as the parent class.
4. Inheritance is represented using an "is-a" relationship, where the derived class is a specialized version of the base class.
5. The derived class inherits the public and protected members (attributes and methods) of the base class, including any fields, properties, and member functions.
6. Inheritance supports the concept of polymorphism, allowing objects of derived classes to be treated as objects of the base class.
7. Derived classes can extend the functionality of the base class by adding new members or overriding inherited members.
8. Inheritance facilitates code organization, as common attributes and methods can be defined in the base class, reducing code duplication.
9. It promotes code maintenance and modularity, as changes made to the base class are automatically reflected in all derived classes.
10. Multiple levels of inheritance can be used, where a derived class can become the base class for another derived class, forming an inheritance hierarchy.

Inheritance in OOP allows for code reuse, modularity, and specialization by creating new classes (derived classes) based on existing classes (base classes). It enables the sharing of common attributes and methods, facilitates polymorphism, and simplifies code maintenance and organization.

#### Example:-
Let's consider an example of a `Vehicle` class as a base class, and two derived classes `Car` and `Motorcycle`:

```cpp
// Base class
class Vehicle {
protected:
    string brand;
    int year;
public:
    Vehicle(string brand, int year) : brand(brand), year(year) {}
    void drive() {
        cout << "Driving the vehicle" << endl;
    }
};

// Derived class 1
class Car : public Vehicle {
private:
    int numDoors;
public:
    Car(string brand, int year, int numDoors) : Vehicle(brand, year), numDoors(numDoors) {}
    void honk() {
        cout << "Car honking" << endl;
    }
};

// Derived class 2
class Motorcycle : public Vehicle {
private:
    string type;
public:
    Motorcycle(string brand, int year, string type) : Vehicle(brand, year), type(type) {}
    void wheelie() {
        cout << "Performing a wheelie" << endl;
    }
};
```

In this example, the `Vehicle` class is the base class. It has common attributes like `brand` and `year`, as well as a method `drive()`.

The `Car` class is derived from the `Vehicle` class using the `public` access specifier. It inherits the `brand` and `year` attributes from the base class and adds a new attribute `numDoors`. It also has its own method `honk()`.

Similarly, the `Motorcycle` class is also derived from the `Vehicle` class. It inherits the `brand` and `year` attributes and adds a new attribute `type`. It also has its own method `wheelie()`.

Now, we can create objects of the derived classes and access both the inherited members and the members specific to each class:

```cpp
int main() {
    Car car("Ford", 2022, 4);
    car.drive(); // Accessing base class method
    car.honk();  // Accessing derived class method

    Motorcycle motorcycle("Harley-Davidson", 2021, "Cruiser");
    motorcycle.drive();  // Accessing base class method
    motorcycle.wheelie();  // Accessing derived class method

    return 0;
}
```

In the `main()` function, we create objects of the `Car` and `Motorcycle` classes. We can access the `drive()` method from the base class as well as the `honk()` method from the `Car` class for the `car` object. Similarly, we can access the `drive()` method from the base class and the `wheelie()` method from the `Motorcycle` class for the `motorcycle` object.

This example demonstrates how inheritance allows derived classes to inherit the attributes and methods of the base class, while also providing the flexibility to add their own specific attributes and methods.