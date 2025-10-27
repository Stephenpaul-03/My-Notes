## **Definition**

- **Behavioral Patterns** are a key category of software design patterns that focus on how objects interact and communicate to fulfill responsibilities within a system. 
- Unlike creational patterns (object creation) and structural patterns (object composition), behavioral patterns emphasize efficient collaboration, responsibility delegation, and flexible interaction among loosely coupled objects

## **Key Behavioral Design Patterns (Gang of Four and Beyond)**

| Pattern                     | Purpose/Benefit                                                                                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Chain of Responsibility** | Passes requests along a chain of potential handlers, with each handler having the chance to process or forward the request                             |
| **Command**                 | Encapsulates a request as an object, separating the request's sender from its executor; supports undo/redo and request queuing.                        |
| **Interpreter**             | Defines a grammar and interpreter for a language within the application, useful for specialized scripting or rule engines.                             |
| **Iterator**                | Provides a standardized way to traverse elements in a collection without exposing its internal structure                                               |
| **Mediator**                | Centralizes communication between objects, reducing direct dependencies and simplifying complex interaction networks                                   |
| **Memento**                 | Captures and restores an object's internal state without exposing implementation details, enabling features like undo/rollback                         |
| **Observer**                | Establishes a notification system so that dependent objects (observers) are automatically updated when a subject changes state                         |
| **State**                   | Allows an object to alter its behavior when its internal state changes, appearing as if the object's class changes at runtime                          |
| **Strategy**                | Defines a family of interchangeable algorithms or behaviors, encapsulates each, and makes them interchangeable at runtime                              |
| **Template Method**         | Specifies the overall structure of an algorithm in a superclass, letting subclasses override specific steps without changing the algorithm's structure |
| **Visitor**                 | Lets you add new operations to a group of objects without modifying their classes by passing an operation ("visitor") to elements of a structure       |
| **Null Object**             | Provides an object with default "do nothing" behavior, avoiding explicit null checks and simplifying client code                                       |

## **Why Use Behavioral Patterns?**

- They improve **flexibility** by decoupling classes, making systems easier to modify and extend.
- They organize **complex workflows** (e.g., chains, notifications, state changes) in a maintainable way.
- They help adhere to object-oriented principles like **loose coupling** and **single responsibility**

## **Typical Use Cases**

- Implementing **undo/redo** in GUIs (Command, Memento).
- Notifying subscribers of changes (Observer).
- Selecting processing logic at runtime (Strategy).
- Organizing workflow chains (Chain of Responsibility).
- Simplifying complex object interactions (Mediator).