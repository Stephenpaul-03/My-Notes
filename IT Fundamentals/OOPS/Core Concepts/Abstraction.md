## **Definition**

- **Data Abstraction** is a foundational concept in object-oriented programming (OOP) that focuses on exposing only the most relevant information and hiding unnecessary internal details of how something works. 

- **Definition:**
    - Data abstraction hides the intricate details and complexity of data or an object from the user, showing only what is necessary to use it effectively.
- **Goal:**
    - To make code simpler to use and maintain by presenting a **high-level view** and reducing dependency on low-level details.
- **How It's Achieved:**
    - Through **abstract data types**, **classes**, **interfaces**, and **access modifiers** (like `private`, `public`).

- When you drive a car, you use the steering wheel, pedals, and dashboard. You don’t need to know the details of its engine, wiring, or fuel injection system to drive it -that’s abstraction in action
- Using a List or Array data type lets you add or remove elements without caring about the underlying implementation - just the available methods and their results.

## **Types of Abstraction**

- **Data Abstraction:**
    - Hides the details of data storage and structure;
    - only essential information is accessible
    - e.g., methods to access or mutate data, not how the data is stored
- **Process (Control) Abstraction:**
    - Hides the details of implementation of operations;
    - users see only high-level operations
    - e.g., calling a method to withdraw money from an ATM without knowing how the ATM dispenses the cash internally.

## **Benefits**

- **Easier Code Maintenance:**
    - Changes in implementation don’t affect users as long as the interface remains the same.
- **Security:**
    - Protects internal data by revealing only what is needed, reducing the risk of direct misuse.
- **Higher Modularity & Reusability:**
    - Abstraction promotes use of components in different parts of a program or across programs.

## **Difference From Encapsulation**

- **Abstraction** is about *what* an object does → showing only essential features and hiding background details (focuses on design interface).
- **Encapsulation** is about *how* an object does it → controlling access and bundling data and methods together for protection (focuses on data security and implementation).