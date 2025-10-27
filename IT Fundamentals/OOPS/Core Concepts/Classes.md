## **Definition**

- A **class** is a blueprint for creating objects.
- It defines data members (fields/attributes) and member functions (methods).
- Classes themselves do not hold data
- Instances (objects) created from the class do.

## **Types of Classes**

### **Concrete Class**

- Regular Class that can be instntiated to make objects
- contains Complete Implementations for its methods
- Most Common Type
- Used to represent real things or ideas

- Think of a real, drivable car in your garage. It’s a specific vehicle built from a blueprint ,with an engine, doors, wheels, and you can use it on the road.

### **Abstract Class**

- Serves as a base for other classes
- Can have some methods (Abstract Methods) without implementations
- Cannot be Instantiated Directly
- Forces Subclasses to implement abstract methods

- Imagine the idea of a “Vehicle” blueprint that says all vehicles can “move”, but doesn't say how; the details are left for cars, bikes, planes, etc. You can’t drive “a Vehicle” itself, only something built from the idea.

### **Final Class**

- Cannot be Extended (subclassed) by other classes
- Used to prevent inheritance,ensure security, or fix behaviour (final keyword in java)

- Picture a factory making a limited-edition “SuperCar” model. No one can take this model and modify it or make a new version, it’s locked as-is for exclusivity and safety reasons.

### **Static Nested Class**

- Defined inside another class and uses the `static` keyword.
- Doesn’t depend on an instance of the outer class.
- Used for grouping classes logically.

- Imagine the instruction manual packaged inside the car’s glovebox. It’s always the same for every car of that model, doesn’t depend on your particular vehicle, but belongs to the overall design.

### **Inner Class**

- Defined within another class (non-static).
- Exists as part of its outer class
- can access outer class’s members.
- Useful for logically grouping classes that belong together.

- Think of the car’s remote key. It only makes sense in relation to its specific car; you can’t use it on another car, because it’s tied to the one it came with.

### **Anonymous Class**

- A one-off class declared and instantiated in a single expression.
- Used for quick, short-lived customization of behavior.
- Usually implements an interface or extends a class.
- Has no name.

- Picture a one-time-use valet card made just for tonight's event. It’s created on the spot, serves a single purpose, and nobody ever gives it a name or keeps it afterward.

### **Local Class**

- Defined inside a method.
- Only accessible within that method.
- Used to limit scope to a specific block of code.

- Imagine a custom checklist written by a mechanic for a specific repair job. The checklist is only useful during that repair and gets thrown away once the task is done.

### **Sealed Class**

- Restricts which classes can inherit from it.
- explicitly list the allowed subclasses.
- Helps model restricted hierarchies (like states in a finite state machine).

- Like a private club. only members on the list get in. No unexpected subclasses crashing the party.

### **Singleton Class**

- Ensures only one instance of the class exists throughout the app.
- Classic design pattern.
- Central manager or config class

- Think of the one and only president of a company. There's just *one*, and they run the whole show.

### **Utility Class**

- Just holds static methods, no instances needed.
- Usually final with a private constructor.

- Like a toolbox - not a machine, just a bunch of handy tools you can grab anytime.

### **Data Record Class**

- Mainly used to store data, often with automatic getters/setters, `toString()`, `equals()`, etc.
- Just a bucket of data, no real behavior.
- Since Java 14+, `record` is a keyword for this.

- Like a filing cabinet folder - holds facts, doesn’t *do* much.