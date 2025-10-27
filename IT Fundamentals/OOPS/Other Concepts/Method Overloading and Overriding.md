## **Method Overloading**

- **Definition:**
    - Method overloading occurs when a class contains multiple methods with the same name but different parameter lists (number, type, or order of parameters).
- **Purpose:**
    - Makes code more readable and flexible
    - lets you perform similar tasks with different inputs without duplicating logic or creating confusing method names.
- **Where Used:**
    - Within the same class.
- **Requirements:**
    - Methods must differ by parameter signature.
    - Method return type can be different, but return type *alone* does not constitute overloading.
    - No inheritance required.
- **Example:**
    
```java
class Calculator {
	int add(int a, int b) { return a + b; }
	int add(int a, int b, int c) { return a + b + c; }
	double add(double a, double b) { return a + b; }
}
```

## **Method Overriding**

- **Definition:**
    - Method overriding happens when a subclass defines a method with the same name, parameters, and return type as a method in its superclass, thus replacing the inherited method's implementation.
- **Purpose:**
    - To let subclass customize or extend inherited behavior, enabling dynamic (runtime) polymorphism.
- **Where Used:**
    - Between a superclass and one or more subclasses.
- **Requirements:**
    - Requires inheritance (“is-a” relationship).
    - Method name, parameter list, and return type (or covariant subtype) must match exactly.
    - Only public or protected methods can be overridden; private and static methods cannot.
    - Annotating with `@Override` (in Java) is good practice to catch errors.
- **Example:**
    
```java
class Animal {
	void makeSound() { System.out.println("Animal makes a sound"); }
}
class Dog extends Animal {
	@Override
	void makeSound() { System.out.println("Woof!"); }
}
```

## Comparison Table

| Feature           | Overloading (Same Class)                                               | Overriding (Inheritance/Subclass)                  |
| ----------------- | ---------------------------------------------------------------------- | -------------------------------------------------- |
| Definition        | Multiple methods, same name, different params (signature) in one class | Redefining a superclass method in subclass         |
| Where Used        | Within a single class                                                  | Superclass ↔ Subclass                              |
| Parameters        | Must differ (number, type, or order)                                   | Must match exactly                                 |
| Return Type       | Can differ                                                             | Must be the same or a subtype                      |
| Inheritance       | Not required                                                           | Required                                           |
| Purpose           | Code flexibility, readability, reusability                             | Customize inherited behavior, runtime polymorphism |
| Method Resolution | Compile-time                                                           | Runtime                                            |
| Example           | `add(int, int)`, `add(double, double)`                                 | `Animal.makeSound()`, `Dog.makeSound()`            |
| Constructors      | Can be overloaded                                                      | Cannot be overridden                               |
| Static Methods    | Can be overloaded                                                      | Cannot be overridden                               |

## When to Use Each

- **Overloading:**
    - Use when you want the same behavior (e.g., addition, logging) to work with different types or numbers of arguments without changing the method name.
    
- **Overriding:**
    - Use when you want a subclass to alter or refine the inherited behavior of one or more methods from the parent class.