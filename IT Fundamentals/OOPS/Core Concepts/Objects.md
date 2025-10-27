## **Definition**

- A runtime instance of a Class, encapsulating state and behavior
- Represents the real-life entities
- Object is an instance of a Class.
- Has an identity, state, and behavior.
- Objects can be created dynamically (runtime) or statically (compile-time).
- No memory is allocated when defined but is allocated when it is instantiated (Created).
- Objects can interact without having to know details of each other’s data or code
- Sufficient to know the type of message accepted and type of response returned by the objects.
- A **specific manufactured car** (e.g., a chrome DMC DeLorean) is an object created from the car blueprint. It has its own engine type, color, and performance specs - its **own state and behavior**.

## **Object Components**

- **Identity** : Each object has a unique identity (often its memory address/reference).
- **State** : Defined by the values of its fields (attributes/data members) at a given time.
- **Behavior** : Defined by the methods (member functions) it can perform.

## **Object Lifecycle**

- **Creation/Instantiation :** Using a constructor (e.g., `Car myCar = new Car();`).
- **Usage :** Objects interact, change state, and perform tasks through method calls.
- **Garbage Collection/Destruction**: Objects are destroyed (or collected as garbage) when no longer referenced, freeing up memory.

## **Object Instantiation**

- Default Values are assigned if not explicitly set (Varies for each Language)
    - Numeric Types  : 0 or 0.0
    - Boolean Types : False
    - Character Types : ‘\0’ (string null character)
    - Object Reference : Defaults to NULL
- Constructors (possibly overloaded) initialize objects differently.

## **Object Accessing Members**

- **Dot operator**: Access fields and methods (`myCar.color`, `myCar.drive()`).
- **Encapsulation**: Access modifiers (public/private/protected) control visibility outside the objects

## **Objects Interaction with each other**

| **Relationship** | **Description** | **Example** |
| --- | --- | --- |
| **Association** | General connection between two classes. | A `Car` *has* a `Driver`. |
| **Aggregation** | A *"Has-a"* relationship with **shared lifecycle**. | A `Team` has multiple `Players`. Players can exist without the team. |
| **Composition** | A *"Part-of"* relationship with **dependent lifecycle**. | A `House` contains `Rooms`. Destroy the house, rooms cease to exist. |