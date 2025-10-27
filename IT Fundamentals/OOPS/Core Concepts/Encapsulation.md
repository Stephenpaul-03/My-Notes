## **Definition:**
- Encapsulation is the concept of bundling the **data (variables)** and the **methods (functions)** that operate on that data into a single unit, i.e., a class.
- It **hides the internal state** of the object and only exposes what is necessary through a controlled interface (methods).

## **Purpose:**
- To **protect data** from unauthorized access or modification.
- To **control how data is accessed or modified** using access specifiers (`private`, `public`, `protected`).
- Ensures **data integrity** by restricting direct access to some of the object’s components.

## **How It Works:**
- Data members (variables) of a class are typically declared `private`.
- They can be accessed or modified only through `public` getter and setter methods. This acts as a protective layer.

## **Benefits:**
- Improves **security** by preventing accidental or malicious changes.
- Facilitates **maintenance** and **modification** - implementation can change without affecting outside code.
- Promotes **modularity** by strictly defining interaction with an object's data.

## **Data Encapsulation**
- This is the specific act of **hiding data members** inside a class, accessible only via member functions.
- It ensures that **data cannot be altered arbitrarily**; instead, all interaction goes through controlled interfaces.
- It helps enforce **validation rules** when data is set or retrieved.

- The engine control system inside a car is encapsulated.
- You, as the driver, **cannot directly access or tinker with the engine internals**.
- Instead, you use the **driver controls** like the accelerator, brake, and drive mode selector. these provide a safe, controlled interface to operate the complex engine system without exposing its inner workings.