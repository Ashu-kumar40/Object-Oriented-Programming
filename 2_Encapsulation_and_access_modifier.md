# Acces Modifiers
In object-oriented programming (OOP), access modifiers are keywords that determine the visibility and accessibility of class members (variables and functions). C++ supports three access modifiers: public, private, and protected. 

Here are some examples of how access modifiers work in C++:

1. Public access modifier: 
   - Members declared as public are accessible from anywhere in the program. 
   - Example:

```cpp
class Car {
public:
    string model; // public data member
    void start() { // public member function
        cout << "The car is starting..." << endl;
    }
};
```

2. Private access modifier: 
   - Members declared as private are accessible only from within the class.
   - Example:

```cpp
class Car {
private:
    int fuel; // private data member
    void injectFuel(int amount) { // private member function
        fuel += amount;
    }
public:
    void start() { // public member function
        injectFuel(10); // can access private member function
        cout << "The car is starting..." << endl;
    }
};
```

3. Protected access modifier:
   - Members declared as protected are accessible from within the class and its derived classes.
   - Example:

```cpp
class Vehicle {
protected:
    int fuel; // protected data member
    void injectFuel(int amount) { // protected member function
        fuel += amount;
    }
};

class Car : public Vehicle {
public:
    void start() {
        injectFuel(10); // can access protected member function
        cout << "The car is starting..." << endl;
    }
};
```

Note that in the above example, the class Car inherits the protected members of class Vehicle using the public inheritance mode (denoted by the ": public" keyword). This means that the protected member fuel and the protected member function injectFuel() are accessible from within the class Car.

Access modifiers provide an important mechanism for encapsulation and data hiding in OOP. By controlling the accessibility of class members, we can ensure that the data and behavior of objects are properly encapsulated and protected from unauthorized access and modification.

### Getter and Setter 
In object-oriented programming, a getter is a class method that retrieves the value of a private or protected data member, and a setter is a class method that sets the value of a private or protected data member. Getters and setters are also known as accessor and mutator methods, respectively.

The use of getters and setters allows for encapsulation and data hiding in OOP. By making data members private or protected, we prevent direct access to them from outside the class, and instead provide methods that can be used to access or modify them. This helps to ensure the integrity of the data and makes it easier to maintain and modify the class in the future.

Here's an example of a class with private data members and public getter and setter methods:

```cpp
class Person {
private:
    string name;
    int age;
public:
    void setName(string name) {
        this->name = name; // set name data member
    }
    string getName() const {
        return name; // get name data member
    }
    void setAge(int age) {
        this->age = age; // set age data member
    }
    int getAge() const {
        return age; // get age data member
    }
};
```

In this example, the private data members `name` and `age` are accessed through the public getter and setter methods `setName()`, `getName()`, `setAge()`, and `getAge()`. The `setName()` and `setAge()` methods set the value of the corresponding data members, and the `getName()` and `getAge()` methods retrieve their values.

Using getter and setter methods provides greater control over how data is accessed and modified in a class, and allows for better encapsulation and abstraction.

# Encapsulation
Encapsulation is a fundamental principle in object-oriented programming (OOP) that involves bundling data and the methods/functions that operate on that data within a single unit called a class. It aims to encapsulate the data and provide controlled access to it through methods, also known as getters and setters, or accessor and mutator methods.

The main idea behind encapsulation is to hide the internal implementation details of a class and expose only the necessary information or interfaces to the outside world. This helps in achieving data abstraction, data hiding, and improved code organization.

By encapsulating data within a class, we can protect it from being directly accessed or modified by external entities, preventing unauthorized changes and maintaining data integrity. Instead, access to the data is provided through well-defined methods that enforce any necessary validations, transformations, or business logic.

Encapsulation also allows for better code maintenance and modification. As the internal implementation of a class is hidden, changes to the underlying data structure or algorithms can be made without affecting other parts of the code that rely on the class's public interface. This promotes code reusability, modularity, and separation of concerns.

Overall, encapsulation is a key principle in OOP that promotes information hiding, improves code organization and maintainability, and ensures proper data access and manipulation through well-defined interfaces.

Certainly! Here's an example of encapsulation in object-oriented programming (OOP) using a class called `Person`:

```cpp
class Person {
private:
    string name;
    int age;
public:
    void setName(string newName) {
        name = newName;
    }
    string getName() {
        return name;
    }
    void setAge(int newAge) {
        if (newAge >= 0) {
            age = newAge;
        }
    }
    int getAge() {
        return age;
    }
};
```

In this example, the `Person` class encapsulates the data attributes `name` and `age` by making them private. This means that these attributes cannot be directly accessed or modified from outside the class.

To provide controlled access to these attributes, public member functions (also known as getter and setter methods or accessor and mutator methods) are defined.

The `setName()` method allows setting the value of the `name` attribute, while the `getName()` method retrieves its value. Similarly, the `setAge()` method sets the value of the `age` attribute, but only if the provided age is non-negative. The `getAge()` method returns the value of the `age` attribute.

Here's how the `Person` class can be used:

```cpp
int main() {
    Person person;
    person.setName("John");
    person.setAge(25);

    cout << "Name: " << person.getName() << endl;
    cout << "Age: " << person.getAge() << endl;

    return 0;
}
```

In the `main()` function, an object of the `Person` class is created. The `setName()` and `setAge()` methods are used to set the values of the `name` and `age` attributes, respectively.

To access these attributes, the `getName()` and `getAge()` methods are called, which provide the encapsulated values of `name` and `age`, respectively. This way, the attributes are protected from direct access, and their values can only be retrieved or modified through the defined public methods.

Encapsulation ensures data abstraction, prevents unauthorized modifications, and allows for proper validation and control over the internal state of objects.