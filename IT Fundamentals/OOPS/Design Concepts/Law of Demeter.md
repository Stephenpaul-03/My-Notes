- **Remember:**
    - “Talk only to your immediate friends, not strangers.”
    
- **Benefits:**
    - Better encapsulation.
    - Lower impact of changes.
    - Improved readability and testability.

- **Good Practice (Compliance):**
```java
order.getCustomerCity(); // Hide the navigation behind a method
```
- **Bad Practice (Violation):**
```java
order.getCustomer().getAddress().getCity();  // Too many hops
```
- Do not “chain” calls to access data deep inside other objects. 

- **Definition:**
    - A class should only communicate with:
        - Itself
        - Its direct fields
        - Objects passed as parameters
        - Objects it creates internally
