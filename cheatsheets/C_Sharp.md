# 1. Boxing and Unboxing
| As                                                                            | Cast Expression                                                              |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| It convert value type into an object type.                                    | It convert an object type into value type. Type                              |
| Boxing is an implicit conversion process.                                     | Unboxing is the explicit conversion process.                                 |
| the value stored on the stack copied to the object stored on the heap memory. | the object stored on the heap memory copied to the value stored on the stack |


<b>Read more:</b>

https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/types/boxing-and-unboxing

https://www.geeksforgeeks.org/c-sharp-boxing-unboxing/

# 2. Type casting
`Implicit Type Casting /Automatic Type Conversion`
* The two data types are compatible (for number).
* Assign value of a smaller data type to a bigger data type.

`Explicit Type Casting`
* Assign a value of larger data type to a smaller data type.
* Target-type specifies the desired type to convert the specified value to.
* Sometimes, it may result into <b> the lossy conversion </b>.

`User-defined conversion`  => [detailed](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/user-defined-conversion-operators)


<b>Read more:</b>

https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/types/casting-and-type-conversions#type-conversion-exceptions-at-run-time


# 3. "is" and "as" keyword
##  `is` keyword
* To convert an object(Type) into another object(Type)
* It returns true if the given object is of the same type otherwise, return false.
* It also returns false for null objects.
* Only reference, boxing, and unboxing conversions are considered by the is operator keyword.

## `as` keyword
* To perform conversion between compatible reference types or Nullable types
* Only for nullable, reference and boxing conversions
* <b> Return null if the conversion is not possible </b> instead of raising an exception.
## `as` vs `cast expression`
| As                   | Cast Expression          |
| -------------------- | ------------------------ |
| Only Ref Type        | Ref and Value Type       |
| Return null if error | Throw Exception if error |

<b>Read more:</b>

https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/type-testing-and-cast#cast-expression

# 4. "readonly" and "const" keyword
## `readonly` keyword
* Assign to the field can only occur as part of the declaration or in a constructor in the same class.
* A readonly field can't be assigned after the constructor exits.
* In static and instance constructors, you are allowed to pass a readonly field as an out or ref parameter.

<b>Read more:</b>

https://www.geeksforgeeks.org/readonly-in-c-sharp/?ref=rp
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/readonly#ref-readonly-return-example

## `const` keyword
* Value will not change during the lifetime of the program (as a “compile-time” value).
* Assign a value to a constant variable at the time you define it.
* Only be applied to the primitive data types (such as ints, floats, chars, and booleans) and strings.

<b>Read more:</b>

https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/const
https://www.infoworld.com/article/3546242/how-to-use-const-readonly-and-static-in-csharp.html

## `readonly` vs `const`
| readonly                                                     | const                                  |
| ------------------------------------------------------------ | -------------------------------------- |
| A runtime constant.                                          | A compile time constant.               |
| The value can be changed                                     | The value can not be changed.          |
| Can assign values in declaration and in the constructor part | Only assign values in declaration part |
| Can be used with static modifiers                            | Cannot be used with static modifiers   |
| It cannot be declared inside the method                      | It can be declared inside the method   |

<b>Issue:</b>

* [Reference between assembly](https://stackoverflow.com/questions/55984/what-is-the-difference-between-const-and-readonly-in-c)


# 5. OOP (Object-Oriented Programming)

## `Object` (a physical entity)
* Is an **abstract data type** created by a developer (a type of variable as int, string, bool...).

* Include multiple properties and methods and may even contain other objects

* Objects are **instance of a class**.

## `Class` (a logical entity)
* To describe one or more objects. Define the fields (attributes, states) and methods which the object will have

* Defined **a blueprint/ structure** for creating an **object** within a program.

* One class can be used to instantiate single or multiple objects

* Essentially **user defined data types**.

* Members in class

| Member | Description     |
| :------------- | :------------- |
| fields   | a variable of any type that is declared directly in a class or struct       |
| constants       | are fields whose value is set at compile time and cannot be changed      |
| properties       | provide protection for a class field to keep it from being changed from outside      |
|methods |define the actions that a class can perform|
|constructors| are methods that are called when the object is first created|


**Note**

The class is a template for modeling a dog, and an object is instantiated from the class representing an individual real world thing.



## Four Principles
### 1. `Inheritance`
* One class is allowed to inherit the features(fields and methods) of another class.

* It provides code **reusability**.

* It is used to achieve runtime polymorphism.

**Note**:
* Super class: The class whose features are inherited (or a base class or a parent class).

* Sub class: The class that inherits the other class (or a derived class, extended class, or child class).

* Constructors are not members, so they are not inherited by subclasses, but the constructor of the superclass can be invoked from the subclass.

### 2. `Encapsulation`
* Prevents the data from being accessed form by the code outside by **hide important information**, only exposing selected.

* In C#, declaring all the variables in the class as private and using C# **Properties** in the class to set and get the values of variables, or **Access modifiers**.

* It provides code **security**.

### 3. `Abstraction`
* **Hiding unnecessary details** (detail hiding) from user, other program and using simple ways to represent complexity, without understanding or even thinking about all the hidden complexity.

* For example phone call, we don't know the internal processing, API.

* Abstraction is an extension of encapsulation but it's simple, high level user interfaces

* Helps to increase security of an application or program as only important details are provided to the user.

* Code updates rarely change abstraction.

* In C#, we use **abstract** (0 to 100%) class and **interface** (100%) to achieve abstraction.

### 4. `Polymorphism`
* One task is **performed in different ways**. For example, a cat speaks meow, dog barks woof, etc.

* Using inheritance, child objects can override parent behaviors,

* In C#, using method **overloading** and method **overriding** to achieve polymorphism.

  * Method Overloading (Compile Time polymorphism): methods or functions may have the same name, but a different **the number, type and order** of parameters passed.

  * Method Overriding (Runtime polymorphism): a child class can provide a different implementation (**override**) than its parent class.

**Note:**

* Method Hidden in C# : Like overriding but it's hide the methods of the parent class from child class (`new` keyword).

## Difference between:
* ### `Class` and `Object`
| Object                                                      | Class                                                                  |
| ----------------------------------------------------------- | ---------------------------------------------------------------------- |
| Object is an <b>instance</b> of a class                     | Class is a <b>blueprint or template</b> from which objects are created |
| Object is <b>a real world entity</b> such as pen, laptop... | Class is <b>a group of similar objects</b>                             |
| Object is <b>a physical</b> entity                          | Class is <b>a logical</b> entity                                       |
| Object is created through <b>new keyword</b> mainly         | Class is declared using <b>class keyword</b>                           |
| Object is created <b>many times</b> as per requirement      | Class is <b>once</b>                                                   |
| Object allocates memory when it is created                  | Class doesn't allocated memory when it is created                      |

* ### `Encapsulation` and `Abstraction`
|  Encapsulation     | Abstraction     |
| :------------- | :------------- |
| Data hiding(information hiding)       | Detail hiding(implementation hiding)       |
| Solves an issue at implementation level| Solves an issue at the design level|
| To hide the code and data into a single unit to secure the data from the outside world |  Focus on what the object does instead of how it does it |
| Use the getters and setters methods to hide the data| Use abstract classes and interfaces to hide the code complexities |
|The process of containing the information | The process of gaining information|

  * While encapsulation groups together data and methods that act upon the data, data abstraction deals with exposing to the user and hiding the details of implementation

* ### `Method Overriding` and `Method Hiding`
| Method Overriding     | Method Hiding     |
| :------------- | :------------- |
| It only redefines the implementation of the method    | In method hiding, you can completely redefine the method       |
|Is an object type| Is a reference type|
|When base class reference variable pointing to the object of the derived class, then it will call the overridden method in the derived class | When base class reference variable pointing to the object of the derived class, then it will call the hidden method in the base class|


**Read more:**

https://www.educative.io/blog/object-oriented-programming#four
https://www.geeksforgeeks.org/c-sharp-inheritance/
https://www.javatpoint.com/java-oops-concepts
https://www.geeksforgeeks.org/c-sharp-encapsulation/
https://www.geeksforgeeks.org/c-sharp-abstraction/
https://www.javatpoint.com/difference-between-object-and-class
https://www.guru99.com/difference-between-object-and-class.html
https://www.geeksforgeeks.org/c-sharp-method-overloading/
https://techterms.com/definition/object
https://techterms.com/definition/class

# 6. `this` keyword
* Refer to the current instance of the class.
* It is used to access members from the constructors, instance methods, and instance accessors.


**Read more:**

https://www.geeksforgeeks.org/c-sharp-this-keyword/

# 7. `Class` vs `Structure`

| Class                                                                             | Structure                                                                                                             |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| Reference types                                                                   | Value types                                                                                                           |
| Allocation of large reference type is cheaper than allocation of large value type | Allocation and de-allocation is cheaper in value type as compare to reference type                                    |
| Contain constructor or destructor                                                 | Not contain parameter less constructor or destructor, but can contain Parameterized constructor or static constructor |
| Used new keyword for creating instances                                           | Create an instance, with or without new keyword                                                                       |
| Can inherit from another class                                                    | Not allowed to inherit from another struct or class                                                                   |
| The data member of a class can be protected                                       | The data member of struct can’t be protected                                                                          |
| Used in large programs                                                            | Used in small programs                                                                                                |

<b>Read more</b>

https://www.geeksforgeeks.org/difference-between-class-and-structure-in-c-sharp/

# 8. Extensions Method
* To add new methods in the existing class without using inheritance.

* Binding parameters are those parameters which are used to bind the new method with the existing class or structure (always present at the first place).

* Always defined as a static method, but when they are bound with any class or structure they will convert into non-static methods.

* Not support method overriding.

* Also add new methods in the **sealed class**

* Cannot apply to fields, properties, or events.

# 9. Abstract method and Abstract class

## Abstract method

* No “body” and declared inside the abstract class only

* An abstract method must be implemented in all non-abstract classes using the override keyword.

##  Abstract class
* Is a parent class for all classes with the same characteristics. Characteristics here are understood as the type, and task of the class.

* To provide a template for child classes and set some rules what the derived classes must implement.

* Use an abstract class as a base class and all derived classes must implement abstract definitions.  

* Not instantiated

**Note**
* Can contains constructors or destructors.

* Contain at least one abstract method.

* It can implement functions with non-Abstract methods.

* Can also work with get and set(properties).

**Read more**

https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/abstract
https://tedu.com.vn/lap-trinh-c/so-sanh-giua-abstract-class-va-interface-trong-cnet-51.html
https://www.geeksforgeeks.org/c-sharp-abstract-classes/

# 10. Interface
An interface defines the behavior an objects (any type) can do. This methods (also properties, events, and indexers) that you can add and any class.

But interfaces will contain only the declaration of the members. The implementation of the interface’s members will be given by class who implements the interface implicitly or explicitly.

* Interfaces can’t have private members.

* By default all the members of Interface are public and abstract.

* Interface cannot contain fields

* Multiple inheritance is possible

* It is used to achieve loose coupling.

* To achieve abstraction

**Read more**

https://yinyangit.wordpress.com/2012/01/15/oop-interface-vs-abstract-class/


# 11. Abstract classes and Interface

| Abstract Class    | Interface     |
| :------------- | :------------- |
| Both declaration and definition part       | Only a declaration part       |
| Not	Multiple inheritance| 	Multiple inheritance |
| Contain constructor| Not contain constructor |
|Contain static members |No contain static members|
| Contain different types of access modifiers  | Only contains public|
|The performance of an abstract class is fast | The performance of interface is slow because it requires time to search actual method in the corresponding class|
|Used to base class | Peripheral abilities of class |
|A class can only use one abstract class | A class can use multiple interface|
| Abstract class can contain methods, fields, constants, etc. |Interface can only contain methods |

**Read more**

https://www.geeksforgeeks.org/difference-between-abstract-class-and-interface-in-c-sharp/

# 11. Array and Collection
| Array     | Collection     |
| :------------- | :------------- |
| Fixed in size       | Resizable in size (grow or shrink)     |
| More memory space | Less memory space |
| Store homogeneous data types | Store both homogeneous and heterogeneous data types |


# 12. Stack and Heap Memory

**Read more**

https://courses.engr.illinois.edu/cs225/sp2020/resources/stack-heap/
