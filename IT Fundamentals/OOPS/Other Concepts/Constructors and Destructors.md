## **Constructors**

- A **constructor** is a special method in a class that is automatically called **when an object is created**.
- Its primary role is to **initialize the object’s data members** and set up its initial state.
- Constructors often share the same name as the class and do not have a return type. They can be overloaded to allow different ways of initializing objects (e.g., default constructor, parameterized constructor, copy constructor).
- When a car rolls off the assembly line, the constructor sets it up → such as choosing the color, installing the engine, and configuring the software version. This prepares the car for use.

## **Destructors**

- A **destructor** is a special method that is called **when an object is destroyed** or goes out of scope.
- Its function is to **perform cleanup**, such as releasing resources, closing files, or deallocating memory.
- Destructors typically have the same name as the class preceded by a tilde (`~`) in languages like C++, and they do not take parameters or return values. Unlike constructors, destructors cannot be overloaded.
- When a car is scrapped, the destructor removes its software, disconnects the battery, and recycles various parts. This cleanup ensures no resources are wasted.

## **Comparison**

| Feature | Constructor | Destructor |
| --- | --- | --- |
| **Purpose** | Initialize object when created | Clean up before object is destroyed |
| **When called** | Automatically on object instantiation | Automatically when object is destroyed |
| **Name** | Same as class name | Same as class name preceded by `~` (in C++) |
| **Parameters** | Can have parameters (overloaded constructors) | No parameters (single destructor only) |
| **Return type** | None | None |
| **Multiple per class** | Yes, overloaded constructors allowed | No, only one destructor |
| **Invocation** | Called by system on object creation | Called by system or garbage collector |

## **Example in C++**

```cpp
class Car {
public:
    Car() {           *// Constructor*
        cout << "Car is being created." << endl;
    }
    ~Car() {          *// Destructor*
        cout << "Car is being destroyed." << endl;
    }
};

int main() {
    Car myCar;       *// Constructor called here// Do something with myCar*
}                   *// Destructor called here when myCar goes out of scope*
```