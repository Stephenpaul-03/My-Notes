## **Definition**

- An **interface** defines a **contract** that classes agree to follow 
- It says *what* must be done, not *how*.
- Contains **method signatures only** (no implementation), though modern languages (like Java & C#) allow:
    - **Default methods** (with a body)
    - **Static methods**
- **No fields or variables** → only **constants** in some languages.
- A class can **implement multiple interfaces** → unlike classes, which typically inherit from one superclass.
- Interfaces can **extend other interfaces**, building layered or modular capabilities.
- Any class that implements an interface must implement **all** its methods → unless it's abstract.
- Interfaces **enforce behavior** → they define capabilities like `Driveable`, `Rechargeable`, or `Serializable`.
- Used for **flexibility**, **decoupling**, and **polymorphism** → lets you code to *interfaces*, not *implementations*.
- An **interface is like a car’s user manual** - it tells you what the car can do (start, stop), but not how the engine actually pulls it off.

## Example:

```java
interface Driveable {
    void start();
    void stop();
}
```

Whether it's a **Car**, **Bike**, or **Toy Drone**, if it implements `Driveable`, you can expect it to start and stop , even if the internal wiring is completely different.
