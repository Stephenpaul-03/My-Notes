## **Dependencies**

- **Dependencies** in relational databases describe how the value of one attribute (or set of attributes) can determine the value of another attribute.

## **# Functional Dependency (FD)**

- A **functional dependency** means that one attribute uniquely determines another.

- **Notation**: `A → B` (A functionally determines B)
    - This means that for every value of attribute `A`, there is a unique corresponding value of attribute `B`.
    - **Example**: In a `Student` table:
        - `StudentID → StudentName`
        - Here, `StudentID` uniquely determines `StudentName`. For each `StudentID`, there is only one `StudentName`.
    - **Analogy**: Think of a **social security number** determining a person's **name**. One SSN corresponds to exactly one person.
- Key Points:
    - The attribute(s) on the left side of the arrow (`A`) are called the **determinants**.
    - The attribute(s) on the right side (`B`) are **dependent** on the determinant(s).
    - **Transitive dependency** and **partial dependency** are special cases of functional dependency (explained below).

## **# Multivalued Dependency (MVD)**

- A **multivalued dependency** means one attribute determines a **set** of values of another, independently of other attributes.

- **Notation**: `A ↠ B` (A multivalued determines B)
    - This means that if we know the value of attribute `A`, we can determine a set of values for attribute `B`, independently of other attributes in the table.
    - **Example**: In a `Student_Course` table:
        - `StudentID ↠ CourseID`
        - Here, `StudentID` determines a set of `CourseID` values (because a student can enroll in multiple courses). However, the courses a student is enrolled in do not depend on other columns, such as `Instructor`.
    - **Analogy**: Think of a **person** owning multiple **phone numbers**. The numbers they own are unrelated to other attributes like their address. Each phone number is associated with the person but not with the others.
- Key Points:
    - MVDs represent a scenario where a single value of `A` is associated with multiple values of `B` but each combination of values is independent of others in the table.
    - Multivalued dependencies are typically handled during **4NF (Fourth Normal Form)** normalization.

## **# Transitive Dependency**

- A **transitive dependency** occurs when one attribute indirectly determines another via a third.
- In other words, if `A → B` and `B → C`, then `A → C` is a transitive dependency.

- **Example**: In an `Employee` table:
    - `EmployeeID → DepartmentName` (EmployeeID determines DepartmentName)
    - `DepartmentName → DepartmentHead` (DepartmentName determines DepartmentHead)
    - Therefore, `EmployeeID → DepartmentHead` (EmployeeID indirectly determines DepartmentHead through DepartmentName).
- **Analogy**: If **you know a student’s school**, and you know that **school has a principal**, then you indirectly know the **student’s principal** through the school. You're not storing the principal directly with the student — it's inferred.
- Key Points:
    - Transitive dependencies can lead to **data redundancy** because the same data (e.g., DepartmentHead) might be stored multiple times.
    - Transitive dependencies are eliminated through **3NF (Third Normal Form)** normalization.

## **# Partial Dependency**

- A **partial dependency** occurs when a non-prime attribute (an attribute that is not part of a candidate key) is functionally dependent on a part (subset) of a candidate key, rather than on the whole key.

- **Example**: In a `Student_Course` table, suppose the composite key is `{StudentID, CourseID}`, and `StudentName` depends only on `StudentID`:
    - `{StudentID, CourseID} → StudentName`
    - But `StudentID → StudentName` (StudentName depends only on `StudentID`, not on the whole key).
    
    This is a **partial dependency** because `StudentName` depends only on part of the composite key (`StudentID`) rather than the entire key (`{StudentID, CourseID}`).
    
- **Analogy**: Imagine a **concert ticket** that includes both a **row and seat number**. If you know the row, you might know the **section color**, but that has nothing to do with the seat. Section color depends only on part of the composite key.
- Key Points:
    - Partial dependencies violate **2NF (Second Normal Form)**, which states that all non-prime attributes should depend on the whole candidate key, not just part of it.
    - Partial dependencies are removed during **2NF** normalization.

## **# Trivial Dependency**

- A **trivial dependency** occurs when an attribute is functionally dependent on itself or on a set of attributes that is a superset of itself.

- **Example**: In a `Student` table, the following are trivial dependencies:
    - `StudentID → StudentID` (an attribute is trivially dependent on itself)
    - `{StudentID, StudentName} → StudentID` (a superset of the attributes determining one of its own attributes)
- **Analogy**: Like saying **a person's name includes their first name** — obvious and not useful for understanding new relationships.
- Key Points:
    - Trivial dependencies are not useful for normalization as they don’t reveal any new information.
    - They are typically ignored during normalization.

## **# Join Dependency**

- A **join dependency** exists when a table can be reconstructed by joining two or more other tables. This means the data can be decomposed into multiple relations and then joined back to get the original relation.

- **Example**: If you have a `Student_Course` table with attributes `StudentID`, `CourseID`, and `InstructorID`, and these attributes can be split into two relations: `Student_Course_1` (containing `StudentID` and `CourseID`) and `Student_Course_2` (containing `CourseID` and `InstructorID`), then the original table can be reconstructed by joining these two tables on `CourseID`.
- **Analogy**: Think of a **recipe** card that can be split into a list of **ingredients** and a list of **cooking instructions**. You can store them separately but rejoin them when cooking.
- Key Points:
    - Join dependencies are related to **5NF (Fifth Normal Form)**, which eliminates join dependencies to prevent redundancy when decomposing tables.
    - This is a more complex form of dependency typically handled in advanced normalization.
