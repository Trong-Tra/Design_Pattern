# OOP Concepts and Principles

## 1. Core Concepts, Major Principles in OOP

### **Core Concepts**
- **Object**: An instance of a class. Represents real-world entities with attributes (data) and methods (operations).
- **Method**: Defines the behavior or actions of an object.
- **Attribute**: Represents the properties or characteristics of an object.
- **Event**: Represents actions or occurrences that the object can respond to.
- **Class**: A blueprint for creating objects, describing their attributes and methods.
- **Constructor**: A special method used to initialize an object when it is created.

### **Four Major Principles**
1. **Abstraction**: Hides unwanted details and focuses on essential information.
   - Example:
     ```csharp
     public abstract class Shape {
         public abstract double CalculateArea();
     }
     ```

2. **Encapsulation**: Combines data and methods in one class while restricting direct access to certain parts of it.
   - Example:
     ```csharp
     public class BankAccount {
         private double balance;
         public double GetBalance() { return balance; }
         public void Deposit(double amount) { balance += amount; }
     }
     ```

3. **Inheritance**: Enables a new class to derive properties and methods from an existing class.
   - Example:
     ```csharp
     public class Parent {
         public void Speak() { Console.WriteLine("Hello"); }
     }
     public class Child : Parent { }
     ```

4. **Polymorphism**: Allows methods to adapt their behavior for different object types.
   - **Static Polymorphism**: Achieved via method overloading or operator overloading.
   - **Dynamic Polymorphism**: Achieved via method overriding.
   - Example:
     ```csharp
     public class Parent {
         public virtual void Speak() { Console.WriteLine("Parent speaking"); }
     }
     public class Child : Parent {
         public override void Speak() { Console.WriteLine("Child speaking"); }
     }
     ```

---

## 2. What is "var" variable?

- The `var` keyword is used to declare variables without explicitly specifying their data type.
- The compiler determines the type based on the assigned value at compile time.
- Example:
  ```csharp
  var number = 10; // inferred as int
  var message = "Hello"; // inferred as string
  ```

---

## 3. Differences Between ArrayList, List, Jagged Array, etc.

| Feature          | **ArrayList**                       | **List<T>**                     | **Jagged Array**                     |
|-------------------|-------------------------------------|----------------------------------|--------------------------------------|
| **Type Safety**   | Stores objects (non-type safe).    | Stores specific types (type-safe). | Array of arrays; can hold different lengths. |
| **Performance**   | Slower (requires boxing/unboxing). | Faster (type-safe, no boxing).  | Optimized for 2D data structures.    |
| **Usage**         | Legacy, avoid using.               | Recommended for most cases.     | Useful for variable-length sub-arrays. |
| **Example**       | ```ArrayList list = new ArrayList();``` | ```List<int> list = new List<int>();``` | ```int[][] jagged = new int[3][];``` |

---

## 4. Keyword "static" (Class, Method, Attribute)

- **Static Class**: Cannot be instantiated and only contains static members.
  - Example:
    ```csharp
    public static class Utility {
        public static void PrintMessage() {
            Console.WriteLine("Message");
        }
    }
    ```
- **Static Method**: Belongs to the class rather than any object. Can be called without an instance.
  - Example:
    ```csharp
    public class MathUtils {
        public static int Add(int a, int b) => a + b;
    }
    ```
- **Static Attribute**: Shared among all instances of the class.
  - Example:
    ```csharp
    public class Counter {
        public static int Count = 0;
    }
    ```

---

## 5. Constructor, Destructor

- **Constructor**:
  - A special method used to initialize objects.
  - Has the same name as the class and no return type.
  - Example:
    ```csharp
    public class Car {
        public Car(string color) {
            Color = color;
        }
    }
    ```
- **Destructor**:
  - A special method used to clean up resources before an object is destroyed.
  - Only available in classes (not structs) and uses the `~` symbol.
  - Example:
    ```csharp
    ~Car() {
        Console.WriteLine("Car object destroyed");
    }
    ```

---

## 6. Access Modifiers and Their Access Range

| Modifier           | Access Level                                                          |
|---------------------|----------------------------------------------------------------------|
| **Public**          | Accessible from anywhere.                                           |
| **Private**         | Accessible only within the same class.                              |
| **Protected**       | Accessible within the class and derived classes.                    |
| **Internal**        | Accessible within the same assembly.                                |
| **Protected internal** | Accessible within the same assembly and derived classes.        |
| **Private protected** | Accessible within the same class and derived classes in the same assembly. |

---

## 7. What Major Principle Did Access Modifier Help Sustain?

- Access modifiers help sustain **Encapsulation** by controlling the visibility of class members and ensuring data is only accessible in controlled ways.

---

## 8. Differences Between Property and Field

| **Aspect**     | **Property**                         | **Field**                          |
|-----------------|--------------------------------------|-------------------------------------|
| **Definition**  | Encapsulated way to access data.    | Directly represents the data.      |
| **Access**      | Can include logic (e.g., validation). | Holds data directly, no logic.     |
| **Example**     | ```public int Age { get; set; }```  | ```private int age;```             |

---

## 9. What Does the "sealed" Keyword Do?

- Prevents a class from being inherited or a method from being overridden.
- **Sealed Class**:
  - Example:
    ```csharp
    public sealed class FinalClass { }
    ```
- **Sealed Method**:
  - Example:
    ```csharp
    public class Parent {
        public virtual void Show() { }
    }
    public class Child : Parent {
        public sealed override void Show() { }
    }
    ```

---

## 10. Difference Between `[][]` and `[,]` Declarations for 2D Arrays

| Feature                 | **Jagged Array (`[][]`)**                               | **Multidimensional Array (`[,]`)**                  |
|--------------------------|--------------------------------------------------------|----------------------------------------------------|
| **Structure**            | Array of arrays, where sub-arrays can have different lengths. | A grid-like structure with fixed dimensions.       |
| **Flexibility**          | Flexible; sub-arrays can vary in size.                 | Fixed; all rows and columns have the same size.    |
| **Memory Allocation**    | Allocates memory separately for each sub-array.        | Allocates memory in a single block.               |
| **Usage**                | Suitable for irregularly structured data.              | Suitable for matrix-like or tabular data.         |
| **Example**              | ```int[][] jagged = new int[2][]; jagged[0] = new int[3];``` | ```int[,] matrix = new int[2, 3];```              |
