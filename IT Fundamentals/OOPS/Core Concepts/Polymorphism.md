## **Definition**

- **Polymorphism** is the ability of a single interface or method to represent or take multiple forms depending on the context, especially the type of the object that invokes it.
- It enables methods to behave differently based on the object that calls them, allowing objects of different classes to be treated through a common interface.

## **Compile-Time Polymorphism (Static Polymorphism)**

- Achieved through **function or method overloading** and **operator overloading**.
- The method to invoke is decided at compile time based on the method signature (number/types of parameters).
- Examples:
    - **Function Overloading:**
        - Multiple methods with the same name but different parameters in the same class.
    - **Operator Overloading:**
        - Customizing the meaning of operators (like `+` or `==`) for user-defined classes.

- Like having several versions of a `startCar()` function → start with a key, fingerprint, or phone app. The appropriate one is chosen based on how you start the car.
- You have several ways to start the car (key, fingerprint, phone app) - depending on input, the right method activates.

## **Run-Time Polymorphism (Dynamic Polymorphism)**

- Achieved through **method overriding**, where a subclass provides its own implementation of a method already defined in its superclass.
- The method to invoke is determined at runtime based on the actual object type.
- Requires inheritance and typically uses **virtual methods** or their equivalent.

- A base class `Car` has a generic `drive()` method assuming a combustion engine. The subclass `ElectricCar` overrides `drive()` to run an electric motor instead. At runtime, calling `drive()` on an object will execute the version matching its actual class.
- When you call `drive()`, the car behaves according to its type: gas engine for traditional cars, electric motor for electric cars. You use the same `drive()` command but get different results.