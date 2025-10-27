## **Definition**

- **Creational Patterns** are a fundamental category of design patterns in object-oriented software development, focused on improving how objects are created and managed. 
- They address the instantiation process, offering *flexible,* *maintainable,* and *decoupled* ways to generate objects compared to simple direct instantiation (e.g., using `new` operator)

## **Key Concepts**

- **Encapsulation of creation logic:** They hide details of how objects are created, composed, or represented, so the client code is independent of these details
- **Promote flexibility:** Enable the system to be easily extended or modified by changing the way objects are created, rather than changing the classes that use them

## **Main Types of Creational Patterns**

Below are the most widely recognized creational patterns, briefly described:

| Pattern              | Purpose                                                                                                                      | Example Scenario                                                                              |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| **Factory Method**   | Defines an interface for creating an object, but allows subclasses to alter the type of objects that will be created         | Creating different types of notifications (email, SMS) depending on user preference.          |
| **Abstract Factory** | Provides an interface for creating families of related or dependent objects without specifying their concrete classes        | Creating UIs for different platforms (Windows, MacOS) using interchangeable widget factories. |
| **Builder**          | Separates complex object construction from its representation, allowing the same process to create different representations | Building complex documents or assembling a meal with different courses.                       |
| **Prototype**        | Creates new objects by copying an existing prototype instance, rather than instantiating new ones directly                   | Duplicating customizable templates or settings profiles.                                      |
| **Singleton**        | Ensures that a class has only one instance and provides a global access point to it                                          | Managing a single configuration manager or database connection in an application.             |
| **Object Pool**      | Recycles and manages a set of initialized objects, instead of creating and destroying them repeatedly                        | Connection pools in database servers.                                                         |

## **Practical Benefits**

- **Loose coupling:** Client code is decoupled from concrete class instantiation, making code more modular and testable
- **Improved maintainability:** Changes in object creation do not affect client code, easing future updates or enhancements
- **Reusability:** Common creation logic can be reused across multiple parts of an application

## **Typical Use Cases**

- Systems where the type or class of object to instantiate must be determined at runtime.
- Applications that require single, global instances (e.g., configuration, logging).
- Creation of families of related objects (e.g., multi-platform UI components)