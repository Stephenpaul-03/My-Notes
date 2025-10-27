## **Shallow Copy**

- **Definition:**
    - Creates a new object, but copies only the references to any nested or mutable objects. Only the top-level container is duplicated.
- **Effect:**
    - Changes to any nested/mutable element (inside a list, map, field, etc.) are reflected in both the original and the copy, since they both point to the same underlying nested objects.
- **Usage:**
    - Shallow copies are **faster** and **more memory efficient** but can cause problems if you expect full independence between objects
    - modifying a mutable element in the copy will affect the original.

- Cloning a car that shares the **same engine** instance—**both cars will break if the shared engine fails**.

- **How to do it:**
    - **Python:**
        - Use `copy.copy()`.
        
	```python
	import copy
	original = [[1, 2], [3, 4]]
	shallow = copy.copy(original)
	```
        
    - **Java:**
        - Default copy constructors and the `clone()` method on objects typically perform shallow copies unless explicitly overridden.
        
	```java
	List<List<Integer>> original = new ArrayList<>();
	List<List<Integer>> shallow = new ArrayList<>(original); 
	*// references to same element lists*
	```
	
    - **C++:**
        - Default copy constructors and assignment operators generate shallow copies for classes that contain pointers/references unless specially handled
        
	```cpp
	MyClass copy = original; *// shallow copy if MyClass has pointer members*
	```

## **Deep Copy**

- **Definition:**
    - Creates a new object and recursively clones all nested objects, resulting in complete independence.
- **Effect:**
    - The copy and the original share **no nested references**.
    - Changing something inside the copied structure does not affect the original in any way.
- **Usage:**
    - Deep copy is **safer** when you need fully independent objects, especially for mutable or stateful data that should not be shared.

- Cloning a car with a **new engine** each car **runs independently**; fixing or breaking one won’t affect the other.

- **How to do it:**
    - **Python:**
        - Use `copy.deepcopy()`.
        
	```python
	import copy
	original = [[1, 2], [3, 4]]
	deep = copy.deepcopy(original)
	```
        
    - **Java:**
        - There is no universal "deep copy" method
        - typically, deep copy must be implemented manually by cloning or copying all nested objects (fields, arrays, etc.) recursively.
        
	```java
	public MyClass(MyClass other) {
		this.field = new AnotherClass(other.field);
		*// ...etc for all nested references*
	}
	```
        
    - **C++:**
        - Like Java, you must write custom copy constructors/assignment operators that also perform deep copies of any owned pointers or dynamic memory.
        
	```cpp
	MyClass(const MyClass& other) {
		ptr = new int[other.size];
		memcpy(ptr, other.ptr, other.size * sizeof(int));
	}
    ```

## **Quick Reference Table**

| Aspect | Shallow Copy | Deep Copy |
| --- | --- | --- |
| Definition | Duplicates only outer object, shares internals | Recursively clones all nested objects |
| Effect | Shared nested/mutable elements | Completely independent objects |
| Python | `copy.copy()` | `copy.deepcopy()` |
| Java | Default copy constructor, `clone()` | Custom/manual implementation |
| C++ | Default copy/assignment | Custom/manual implementation |
| Analogy | Cloned car, shared engine | Cloned car, new engine |