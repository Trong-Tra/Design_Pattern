1. Class and structs can inherit from multiple interfaces
2. Interfaces can inherit from multiple interfaces
3. An abstract class can have both abstract and regular methods
4. Abstract class is a restricted class that cannot be used to create objects
5. Abstract method: can only be used in an abstract class, and it does not have a body
6. Abstract classes do not need to inherit from another class. They can be inherited by another class, but they are not required to have a base class themselves.
7. When implementing an interface, you do not use override, because there is no base class method to override. Instead, you simply provide the implementation for the interface methods. You would use the override keyword when overriding methods in a base class.
8. By default, members of an interface are abstract and public 
9. Interfaces can contain properties and methods, but not fields
10. Use the override keyword when implementing an interface
11. interfaces cannot be used to create objects
