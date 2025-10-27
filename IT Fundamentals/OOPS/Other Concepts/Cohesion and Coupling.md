## **Cohesion**

- **Definition:** Cohesion refers to how closely related and focused the responsibilities and tasks of a single class or module are.
- A highly cohesive class/module groups related functionalities that belong together.

### **Types of Cohesion (from worst to best)**

- **Coincidental cohesion:** Elements involved have little or no meaningful relationship.
- **Logical cohesion:** Elements perform similar activities (e.g., all input handling) but are different logically.
- **Functional cohesion:** All elements contribute to a single well-defined task — the desired goal.
- (Others: Temporal, Procedural, Communicational cohesion, etc.—gradually improving focus and strength)

### **Advantages**

- Easier to understand, maintain, and debug.
- Enhances reusability.
- Makes unit testing simpler.
- Limits the spread of changes when behavior needs modification.

## **Example**

- A class `OrderProcessor` that only handles order validation and processing has **high cohesion**.
- A class `OrderProcessor` that handles orders, user input, database access, and UI updates has **low cohesion** (too many unrelated responsibilities).

## **Coupling**

- **Definition:** Coupling is the degree of dependency between different classes or modules.
- High coupling means modules are tightly connected, with many direct dependencies.
- Low coupling means modules interact through well-defined interfaces, minimizing knowledge of each other's internals.

### **Types of Coupling (from worst to best)**

- **Content coupling:** One module modifies internal data of another.
- **Common coupling:** Modules share global data.
- **Control coupling:** One module controls the flow of another by passing control flags.
- **Stamp coupling:** Modules share composite data structures but use only parts.
- **Data coupling:** Modules share data via parameters.

### **Advantages**

- Promotes independent module development and testing.
- Simplifies maintenance and refactoring.
- Facilitates flexibility and extensibility.
- Limits ripple effects of changes in one module.

### **Example**

- Tight coupling: A class `Payment` directly instantiates and manipulates a specific `Database` class.
- Loose coupling: A class `Payment` interacts with a `Database` via an interface or abstract class, unaware of the implementation details.

## **Best Practice Summary**

| Principle | Aim | Benefits |
| --- | --- | --- |
| High Cohesion | Each class/module has one clear responsibility | Easier maintenance, understanding, testing |
| Low Coupling | Minimize dependencies between classes/modules | Greater flexibility, easier testing, less ripple impact of changes |