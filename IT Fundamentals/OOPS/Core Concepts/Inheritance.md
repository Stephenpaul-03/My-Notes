## **Definition:**

- Inheritance is a mechanism where a new class (called **child** or **subclass**) derives properties (fields) and behaviors (methods) from an existing class (called **parent**, **superclass**, or **base class**).
- It promotes **code reuse** and **hierarchical classification**.

## **Key Points:**

- The child class **inherits** attributes and methods from the parent class.
- The child can add new members or **override** existing methods for specialized behavior.
- Use of `super` or `base` keyword to access the parent class’s members.
- Inheritance is **one-directional**: from parent to child (child class knows parent, but parent doesn’t know child).

- Imagine a **Car** (parent class) as a generic vehicle blueprint: it has wheels, doors, and a steering wheel.
- A **Sports Car** (child class) inherits these basic features but adds special features like a turbocharger or aerodynamic design.
- Similarly, an **Electric Car** inherits the core features but replaces the engine with a battery system.

## **Types of Inheritance**

| Type                         | Description                                                                                                        | Example/Analogy                                                     |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------- |
| **Single Inheritance**       | One child class inherits from one parent class.                                                                    | SportsCar inherits from Car.                                        |
| **Multiple Inheritance**     | One child class inherits from more than one parent class (supported directly in C++, but not in Java for classes). | A FlyingCar inherits from both Car and Airplane (when allowed).     |
| **Multilevel Inheritance**   | A child class inherits from a class which itself is a child of another class.                                      | ElectricSportsCar inherits from SportsCar, which inherits from Car. |
| **Hierarchical Inheritance** | Multiple child classes inherit from a single parent class.                                                         | SportsCar and Truck both inherit from Car.                          |
| **Hybrid Inheritance**       | Combination of two or more types of inheritance (for example, both hierarchical and multiple).                     | In C++, a class that combines multilevel and multiple inheritance.  |

![Inheritance.png](Inheritance.png)