## **Static Members**

- **Definition:**
    - Static members - both fields (variables) and methods - belong to the class itself, **not to any specific object**.
    - They are shared by all instances of the class.
- **Accessing:**
    - Accessed using the class name (e.g., `Car.numberOfCars`, `Math.max()`), though you may also access them via an object reference (not recommended for clarity).
- **Purpose:**
    - Used for data or behavior that should be **common to all objects** of the class.
    - Good for utility methods or keeping a count of all objects created.
- **Memory allocation:**
    - Static members are allocated **once per class**, not per object.

- Think of a traffic law, like the **speed limit** - it’s common to all cars (all instances) on the road; every car refers to the same rule.

## **Non-Static Members**

- **Definition:**
    - Non-static members (also called instance members) ( both fields and methods) **belong to individual objects**.
    - Each object of the class has its own copy of these variables.
- **Accessing:**
    - Accessed via an object reference (e.g., `myCar.color`, `myCar.drive()`).
- **Purpose:**
    - Store **object-specific state** or provide object-specific behavior.
    - Each object can have different values for its non-static fields.
- **Memory allocation:**
    - Allocated **separately for each object** created from the class.


- Think of a car’s **paint color** - each car (object) can have its own color, independent of other cars.

| Aspect                | Static Member                          | Non-Static Member                    |
| --------------------- | -------------------------------------- | ------------------------------------ |
| **Belongs to**        | Class (shared)                         | Individual object (instance)         |
| **Accessed via**      | Class name (recommended)               | Object reference                     |
| **Example**           | `Car.numberOfCars`, `Math.PI`          | `myCar.color`, `myCar.startEngine()` |
| **Memory allocation** | Once per class                         | Once per object                      |
| **Change affects**    | All objects (since shared)             | Only that specific object            |
| **Typical uses**      | Counters, constants, utility functions | Object state, regular methods        |