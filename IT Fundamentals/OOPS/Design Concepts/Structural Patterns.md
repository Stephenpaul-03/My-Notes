## **Definition**

- **Structural Patterns** are a core category of design patterns in object-oriented software design that focus on how classes and objects are *composed to form larger, more complex structures*, while keeping these systems both flexible and efficient.
- The main goal is to simplify code organization, manage relationships between components, and allow systems to be modified more easily without breaking existing functionality.

## **Key Aspects of Structural Patterns:**

- Emphasize assembling objects and classes to realize broader functionality.
- Promote *code reuse*, *scalability*, and *maintainability*.
- Allow for *flexible composition* of components, often at runtime
- Decouple subsystems and simplify relationships among entities

## **Common Structural Patterns:**

| Pattern       | Purpose/Benefit                                                                                                                             |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Adapter**   | Allows incompatible interfaces to work together by "adapting" one interface into another                                                    |
| **Bridge**    | Separates abstraction from its implementation, so both can vary independently                                                               |
| **Composite** | Composes objects into tree structures to represent part-whole hierarchies, letting clients treat individual and composite objects uniformly |
| **Decorator** | Adds new responsibilities to objects dynamically without altering their structure                                                           |
| **Facade**    | Provides a unified, simplified interface to a set of interfaces in a subsystem, hiding its complexity from clients                          |
| **Flyweight** | Shares common parts of state between many objects to reduce memory usage (useful for large numbers of similar objects)                      |
| **Proxy**     | Provides a substitute or placeholder for another object, controlling access or adding extra functionality                                   |

## **Example Use Cases:**

- Integrating third-party code or legacy systems (Adapter).
- Allowing unrelated abstractions and implementations to be developed independently (Bridge).
- Organizing graphical objects in a drawing application as hierarchies (Composite).
- Dynamically adding features (logging, security) to components (Decorator).
- Simplifying complex libraries or APIs for easier use (Facade).
- Handling large numbers of similar objects efficiently (Flyweight).
- Controlling or monitoring access to critical resources (Proxy)

## **Benefits:**

- Enable independently developed components to work smoothly together.
- Help with large, complex system restructuring without wide-ranging code changes.
- Reduce coupling between subsystems and improve code clarity