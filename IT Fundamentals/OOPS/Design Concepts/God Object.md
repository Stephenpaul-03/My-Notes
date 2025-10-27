## **OOP Anti-Pattern: God Object**

- **Definition:**
    - A **God Object** is a class that **knows too much** or **does too much -** violates the **Single Responsibility Principle**.
- **Symptoms:**
    - Excessive data and logic inside a single class.
    - Many unrelated methods and properties.
    - Other classes become overly dependent on it.
- **Why It's Bad:**
    - **Low cohesion**, **high coupling**.
    - Hard to test, debug, and maintain.
    - Any change risks cascading failures elsewhere.
- **Corrective Measures:**
    - Break down the class into smaller, cohesive components.
    - Apply **SRP** and **encapsulation**.
    - Introduce services or delegate responsibilities to other classes.
- **Example:**
    
```java
class VehicleManagementSystem {
	void registerCar() { ... }
	void sendInvoice() { ... }
	void calculateTax() { ... }
	void trackVehicleLocation() { ... }
	// ... too many unrelated responsibilities
}
```