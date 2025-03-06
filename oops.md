# Object-Oriented Programming (OOP) Notes

## Table of Contents
1. [Review of C and Difference Between C and C++](#review-of-c-and-difference-between-c-and-c)
2. [Procedure-Oriented vs. Object-Oriented Approach](#procedure-oriented-vs-object-oriented-approach)
3. [Basic OOP Concepts](#basic-oop-concepts)
   - [Abstraction](#abstraction)
   - [Encapsulation](#encapsulation)
   - [Inheritance](#inheritance)
   - [Polymorphism](#polymorphism)
   - [Dynamic Binding](#dynamic-binding)
   - [Message Passing](#message-passing)
4. [Characteristics of Object-Oriented Languages](#characteristics-of-object-oriented-languages)
5. [Abstract Data Types](#abstract-data-types)
6. [Objects and Classes](#objects-and-classes)
   - [Attributes and Methods](#attributes-and-methods)
   - [Class Declaration in C++](#class-declaration-in-c)
   - [Local Class and Global Class](#local-class-and-global-class)
   - [State, Identity, and Behavior of Objects](#state-identity-and-behavior-of-objects)
   - [Local Objects vs. Global Objects](#local-objects-vs-global-objects)
   - [Scope Resolution Operator](#scope-resolution-operator)
   - [Friend Functions](#friend-functions)
   - [Inline Functions](#inline-functions)
   - [Constructors and Destructors](#constructors-and-destructors)
   - [Instantiation of Objects](#instantiation-of-objects)
   - [Types of Constructors](#types-of-constructors)
   - [Static Class Data](#static-class-data)
   - [Array of Objects](#array-of-objects)
   - [Constant Member Functions and Objects](#constant-member-functions-and-objects)
   - [Memory Management Operators](#memory-management-operators)
7. [Inheritance and Types of Inheritance](#7-inheritance-and-types-of-inheritance)
   - [Access Modes: public, private, protected](#access-modes-public-private-protected)
8. [Ambiguity in Inheritance and Virtual Base Classes](#ambiguity-in-inheritance-and-virtual-base-classes)
9. [Overriding Inheritance Methods](#overriding-inheritance-methods)
10. [Constructors in Derived Classes](#constructors-in-derived-classes)
11. [Nesting of Classes](#nesting-of-classes)
12. [Abstract Classes](#12-abstract-classes)
13. [Aggregation and Composition vs. Classification Hierarchies](#13-aggregation-and-composition-vs-classification-hierarchies)
14. [Final Tips](#final-tips)

---

## 1. Review of C and Difference Between C and C++
- **Review of C**:
  - Procedural programming language.
  - Uses functions, structures, pointers.
  - Emphasizes procedure (function) calls.
  - No built-in mechanism for object orientation.

- **Differences Between C and C++**:
  - **Paradigm**: C is procedural; C++ supports both procedural and object-oriented.
  - **Data Hiding**: C has no direct support for encapsulation; C++ provides classes for data hiding.
  - **Function Overloading**: Not possible in C; supported in C++.
  - **Reference Variables**: Not available in C; available in C++.
  - **Standard Input/Output**: `scanf`/`printf` in C; `cin`/`cout` in C++ (though C I/O still works in C++).
  - **Memory Management**: `malloc`/`free` in C; `new`/`delete` in C++ (supports operator overloading).

---

## 2. Procedure-Oriented vs. Object-Oriented Approach
- **Procedure-Oriented**:
  - Emphasizes functions and sequences of tasks.
  - Data can move freely across functions.
  - Larger programs can become complex and difficult to maintain.

- **Object-Oriented**:
  - Emphasizes objects that contain both data and methods.
  - Data is protected from unintended access (encapsulation).
  - Encourages modular design and reusability through inheritance and polymorphism.

---

## 3. Basic OOP Concepts

### Abstraction
- **Definition**: Hiding complex implementation details and showing only the necessary features of an object.
- **Example**: A `class` representing a Bank Account, providing methods like `deposit()` and `withdraw()` without showing the internal transaction logic.
- **Benefit**: Simplifies complex reality by modeling classes appropriate to the problem.

### Encapsulation
- **Definition**: Wrapping data and methods into a single unit (class).
- **Benefits**: Protects data from outside interference and misuse.
- **Example**: Private data members and public setter/getter functions in a class.
- **Additional Note**: Often enforced via `private` or `protected` access specifiers.

### Inheritance
- **Definition**: Mechanism where a new class (derived class) acquires properties and behaviors of an existing class (base class).
- **Example**: A `Car` class inherits from a `Vehicle` class.
- **Benefit**: Code reusability and hierarchical classification.

### Polymorphism  
- **Definition**: Ability of functions or methods to take different forms depending on context.  
- **Types**:  
  1. **Compile-time Polymorphism**: Function overloading, operator overloading.  
  2. **Run-time Polymorphism**: Virtual functions (dynamic binding).  
- **Example**:  
  - **Function Overloading**: `int add(int a, int b); double add(double a, double b);`  
  - **Virtual Functions**: Overriding a `display()` function in a derived class.  

---

### **Function Overloading in C++**  
Function overloading is a feature in C++ that allows multiple functions with the same name but different parameter lists (different number or types of parameters). The compiler determines which function to call based on the arguments passed.  

#### **Key Points**  
1. **Same function name** → Functions must have the same name but different parameter lists.  
2. **Different parameter types or counts** → The number or type of parameters must be different.  
3. **Return type does NOT matter** → Overloading is determined only by parameters, not by return type.  
   - If two functions have the same parameters but different return types, the compiler throws an error.  
4. **Overloaded functions can be in the same class or in global scope**.  

---

### **Virtual Functions in C++**  
- A **virtual function** is a member function in a base class that you can override in a derived class.  
- It enables **dynamic binding** (or late binding), meaning the function that gets called is determined at runtime based on the object's type, not the pointer type.  
- Declared using the `virtual` keyword in the base class.  

#### **Example**  
```cpp
class Base {
public:
    virtual void show() { cout << "Base class\n"; }
};

class Derived : public Base {
public:
    void show() override { cout << "Derived class\n"; }
};
```
- If a `Base*` pointer points to a `Derived` object, calling `show()` will invoke `Derived`'s version of `show()`, ensuring runtime polymorphism.
### Dynamic Binding
- **Definition**: Binding of a function call to its definition determined at runtime.
- **Example**: Virtual functions in C++ where the function to call depends on the actual object type at runtime, not the pointer type.

### Message Passing
- **Definition**: Objects communicate with each other by sending and receiving messages (method calls).
- **Relevance**: Promotes modularity and separation of concerns. Each object can offer services via public methods.

---

## 4. Characteristics of Object-Oriented Languages
1. **Encapsulation**  
2. **Inheritance**  
3. **Polymorphism**  
4. **Abstraction**  
5. **Modularity** (classes, objects, modules)

---

## 5. Abstract Data Types
- **Definition**: A data type where only the behavior (operations) is defined but the implementation is hidden.
- **Example**: Stack ADT with `push`, `pop`, and `top` operations without exposing the underlying data structure (array or linked list).
- **Purpose**: Separate the interface from the implementation, improving maintainability.

---

## 6. Objects and Classes

### Attributes and Methods
- **Attributes (Data Members)**: Variables that represent the state of a class/object.
- **Methods (Member Functions)**: Functions that define the behavior or operations on that state.

### Class Declaration in C++
```cpp
class ClassName {
private:
    // private data members
public:
    // public member functions
    ClassName();    // constructor
    ~ClassName();   // destructor
};
```
- **Access Specifiers**: `private`, `public`, `protected` determine visibility and access level.

### Local Class and Global Class
- **Local Class**: A class declared inside a function (its scope is limited to that function).
- **Global Class**: A class declared at the namespace (global) level, visible throughout the program.

### State, Identity, and Behavior of Objects
- **State**: Represented by the object’s data (attributes).
- **Identity**: Uniqueness of an object, even if it has the same state as another object.
- **Behavior**: Defined by the methods/functions an object can perform.

### Local Objects vs. Global Objects
- **Local Objects**: Created within a block or function, destroyed when the block ends.
- **Global Objects**: Declared outside all functions, exist throughout the program execution.

### Scope Resolution Operator
- **Symbol**: `::`
- **Usage**: 
  - Access a global variable when a local variable of the same name exists.
  - Define member functions outside the class definition.
  - Access static members (`ClassName::staticMember`).

### Friend Functions
- **Definition**: A non-member function that has access to the private and protected members of a class.
- **Use Cases**: Overloaded operator functions that need access to private data of multiple classes.
- **Important**: Use them sparingly to maintain encapsulation.

### Inline Functions
- **Definition**: Functions that are expanded at the point of invocation rather than called through a normal function call.
- **Syntax**: `inline returnType functionName(...) { ... }`
- **Benefit**: Reduces function call overhead (but can increase code size).
- **Compiler Hint**: `inline` is a suggestion, the compiler may ignore it if the function is too large.

### Constructors and Destructors
- **Constructor**: Special member function with the same name as the class, initializes objects.
- **Destructor**: Special member function preceded by `~`, cleans up when an object goes out of scope.
- **Properties**:
  - Constructors cannot return values.
  - Destructors cannot have parameters.
  - Automatic invocation at object creation (constructor) and destruction (destructor).

### Instantiation of Objects
- **Definition**: Creating an object of a class (e.g., `ClassName obj;`).
- **Dynamic Allocation**: `ClassName *obj = new ClassName();`
  - Must manually `delete obj;` to avoid memory leaks.

### Types of Constructors
1. **Default Constructor**: No parameters (or all parameters have default values).
   ```cpp
   class A {
   public:
       A() {
           // default initialization
       }
   };
   ```
2. **Parameterized Constructor**: Accepts parameters to initialize data members.
   ```cpp
   class A {
   private:
       int x;
   public:
       A(int val) : x(val) { }
   };
   ```
3. **Copy Constructor**: Initializes an object from another object of the same class (`ClassName (const ClassName &obj)`).
   ```cpp
   class A {
   private:
       int x;
   public:
       A(const A &obj) {
           x = obj.x;
       }
   };
   ```

### Static Class Data
- **Definition**: Class members declared with `static`. Shared among all objects of the class.
- **Example**: A `static` counter tracking the number of objects created.
  ```cpp
  class A {
  private:
      static int count;
  public:
      A() { count++; }
      static int getCount() { return count; }
  };
  int A::count = 0; // definition outside the class
  ```

### Array of Objects
- **Syntax**: `ClassName objArray[5];`
- **Usage**: Each element in `objArray` is an object of `ClassName`.
- **Initialization**: If a constructor requires parameters, you must provide them accordingly (e.g., an initializer list).

### Constant Member Functions and Objects
- **Constant Objects**: Declared with `const`, cannot modify data members.
  ```cpp
  const A obj; // all operations that modify obj are invalid
  ```
- **Constant Member Functions**: Declared with `const` keyword at the end, do not modify any data members.
  ```cpp
  int getValue() const {
      return x; // does not modify x
  }
  ```

### Memory Management Operators
- **`new`**: Allocates memory dynamically for an object or array of objects.
- **`delete`**: Frees the dynamically allocated memory.
- **Example**:
  ```cpp
  ClassName* ptr = new ClassName();
  // ...
  delete ptr;
  ```

---

## 7. Inheritance and Types of Inheritance
- **Definition**: Mechanism of acquiring features from an existing class (base class) to form a new class (derived class).
- **Benefit**: Promotes code reusability and logical hierarchy.

### Types of Inheritance
1. **Single Inheritance**: One base class, one derived class.
2. **Multiple Inheritance**: One derived class inherits from multiple base classes.
3. **Hierarchical Inheritance**: One base class, multiple derived classes.
4. **Multilevel Inheritance**: Derived class becomes a base class for another class (chain).
5. **Hybrid (Virtual) Inheritance**: Combination of multiple and multilevel inheritance.

```cpp
#include <iostream>
using namespace std;

// Base class (Single Inheritance)
class A {
public:
    void showA() { cout << "Class A\n"; }
};

// Single Inheritance (B inherits A)
class B : public A {
public:
    void showB() { cout << "Class B\n"; }
};

// Multiple Inheritance (C inherits from A and B)
class C : public A, public B {
public:
    void showC() { cout << "Class C\n"; }
};

// Multilevel Inheritance (D inherits B, which inherits A)
class D : public B {
public:
    void showD() { cout << "Class D\n"; }
};

// Hierarchical Inheritance (E and F both inherit from A)
class E : public A {
public:
    void showE() { cout << "Class E\n"; }
};

class F : public A {
public:
    void showF() { cout << "Class F\n"; }
};

// Hybrid Inheritance (G uses multiple and multilevel)
class G : public C, public D {
public:
    void showG() { cout << "Class G\n"; }
};

int main() {
    A a;  a.showA();
    B b;  b.showA(); b.showB();
    C c;  c.showB(); c.showC();
    D d;  d.showA(); d.showB(); d.showD();
    E e;  e.showA(); e.showE();
    F f;  f.showA(); f.showF();
    G g;  g.showB(); g.showC(); g.showD(); g.showG(); // Note: A appears twice in G (Diamond Problem)

    return 0;
}

```

### **Diamond Problem**

- The Diamond Problem occurs in multiple inheritance when a derived class inherits from two base classes that both inherit from a common base, causing ambiguity due to multiple copies of the base class.
- A **virtual base class** is used in **multiple inheritance** to **avoid the "Diamond Problem"**, ensuring only **one copy** of the base class is inherited.

---

#### **Diamond Problem (Without Virtual Base Class)**
```cpp
#include <iostream>
using namespace std;

class A {
public:
    void show() { cout << "Class A\n"; }
};

class B : public A {};  
class C : public A {};  
class D : public B, public C {};  // D inherits B and C (causes ambiguity)

int main() {
    D obj;
    obj.show();  // ERROR: Ambiguous (two copies of A)
}
```
❌ **Error:** `request for 'show' is ambiguous`

---

#### **Solution: Using Virtual Base Class**
```cpp
#include <iostream>
using namespace std;

class A {
public:
    void show() { cout << "Class A\n"; }
};

class B : virtual public A {};  // Virtual inheritance
class C : virtual public A {};  
class D : public B, public C {};  // Only one copy of A exists

int main() {
    D obj;
    obj.show();  // Works fine, no ambiguity
}
```
✅ **Output:**  
```
Class A
```

### Access Modes: public, private, protected
- **public**: Public members of the base become public in the derived class.
- **protected**: Public members of the base become protected in the derived class.
- **private**: Public and protected members of the base become private in the derived class.

### Method Hiding in Derived Classes (C++ Behaviour)
If a derived class defines a method with the same name as a method in its base class without virtual, the base class method gets hidden rather than overridden.



---

## 8. Ambiguity in Inheritance and Virtual Base Classes
- **Ambiguity**: Occurs in multiple inheritance when two base classes have a function with the same signature.
- **Scope Resolution Operator**: Used to resolve ambiguity by specifying which base class function to use (`BaseClassName::functionName()`).
- **Virtual Base Class**: Used in multiple or hierarchical inheritance to avoid duplicate copies of the base class data.
  ```cpp
  class Base {
      // ...
  };

  class Derived1 : virtual public Base {
      // ...
  };

  class Derived2 : virtual public Base {
      // ...
  };

  class Final : public Derived1, public Derived2 {
      // avoids duplicate Base sub-objects
  };
  ```

---

## 9. Overriding Inheritance Methods
- **Definition**: Derived class provides a specific implementation of a virtual function already provided by its base class.
- **Syntax**:
  ```cpp
  class Base {
  public:
      virtual void display() {
          // Base implementation
      }
  };

  class Derived : public Base {
  public:
      void display() override {
          // Overridden implementation
      }
  };
  ```
- **Note**: The `override` keyword (C++11+) helps catch errors if the function signature does not match.

---

## 10. Constructors in Derived Classes
- **Order of Execution**:
  1. Base class constructor
  2. Member initializations
  3. Derived class constructor
- **Constructor Initialization Lists**: Used to initialize base class and member data.
  ```cpp
  Derived::Derived() : Base() {
      // derived class constructor body
  }
  ```
- **Why Important**: Ensures proper construction order, especially for complex hierarchies.

---

## 11. Nesting of Classes
- **Definition**: A class defined within another class.
- **Use Case**: Logical grouping of classes, or helper classes that are only relevant within another class.
  ```cpp
  class Outer {
  public:
      class Inner {
          // ...
      };
  };
  ```
- **Access**: `Outer::Inner` if accessing from outside.

---

## 12. Abstract Classes
- **Definition**: A class that **cannot** be instantiated and contains at least one **pure virtual function**.
- In C++, abstraction can be achieved using:  
   1. **Abstract Classes** (using pure virtual functions)  
   2. **Interfaces** (fully abstract classes with only pure virtual functions)
- **Syntax**:
  ```cpp
  class AbstractClass {
  public:
      virtual void pureFunction() = 0; // pure virtual
  };
  ```
- **Purpose**: To define an interface or a base class that other classes must implement.
- **Example**: `Shape` class with a pure virtual `draw()` method. Specific shapes (Circle, Rectangle) implement `draw()`.

---

#### **Key Features of Abstraction**  
- **Simplifies Code**: Hides unnecessary details and provides a clear interface.  
- **Encapsulation**: Works together with encapsulation by restricting direct access to implementation details.  
- **Enforces Consistency**: Ensures that all derived classes follow a standard structure.

---

#### **1. Pure Virtual Functions**  
A **pure virtual function** is a function that **must be overridden** in derived classes. It is declared using `= 0` in the base class.  
```cpp
class AbstractClass {
public:
    virtual void pureFunction() = 0; // Pure virtual function
};
```
Any class **containing at least one pure virtual function** is an **abstract class**.

---

Example:  
```cpp
#include <iostream>
using namespace std;

class Shape {  // Abstract Class
public:
    virtual void draw() = 0;  // Pure virtual function
};

class Circle : public Shape {
public:
    void draw() override {  // Must override draw()
        cout << "Drawing Circle\n";
    }
};

class Rectangle : public Shape {
public:
    void draw() override {
        cout << "Drawing Rectangle\n";
    }
};

int main() {
    // Shape s;  // ❌ Error: Cannot instantiate abstract class
    Shape* s1 = new Circle();
    Shape* s2 = new Rectangle();

    s1->draw();  // ✅ "Drawing Circle"
    s2->draw();  // ✅ "Drawing Rectangle"

    delete s1;
    delete s2;
}
```

---

#### **2. Abstract Class vs Interface**  
| Feature              | Abstract Class          | Interface (Pure Abstract Class) |
|----------------------|------------------------|--------------------------------|
| **Contains Data Members?** | Yes | No |
| **Constructors?**    | Yes | No |
| **Implementation Allowed?** | Yes (normal + virtual functions) | No (only pure virtual functions) |
| **Multiple Inheritance?** | Single + Multiple | Only Multiple |

Example of **Interface-style** abstraction (only pure virtual functions):  
```cpp
class IShape {  // Interface
public:
    virtual void draw() = 0; // Must be overridden
};
```
---

#### **3. Can an Abstract Class Have a Constructor?**  
Yes, an abstract class **can have a constructor**, but it **cannot be instantiated directly**. The constructor is called when an object of a derived class is created.

```cpp
class AbstractClass {
public:
    AbstractClass() { cout << "AbstractClass Constructor\n"; }
    virtual void show() = 0;
};

class Derived : public AbstractClass {
public:
    Derived() { cout << "Derived Constructor\n"; }
    void show() override { cout << "Implementation of show()\n"; }
};

int main() {
    Derived d;
    d.show();
}
```
**Output:**  
```
AbstractClass Constructor  
Derived Constructor  
Implementation of show()  
```
---

## 13. Aggregation and Composition vs. Classification Hierarchies
- **Aggregation**: A “has-a” relationship where the lifetime of the contained object is **not** strictly dependent on the container.
  - Example: A `Team` class having `Player` objects. Players can exist independently of the team.
- **Composition**: A stronger form of “has-a” where the contained object’s lifetime **depends** on the container.
  - Example: A `Car` class with `Engine` objects. If the `Car` is destroyed, the `Engine` is also destroyed.
- **Classification Hierarchies**: Typically refers to inheritance hierarchies (generalization/specialization).



---

### **Composition vs. Aggregation vs. Inheritance**  

| Feature        | **Composition** | **Aggregation** | **Inheritance** |
|---------------|---------------|---------------|--------------|
| Relationship  | **Has-a (Strong)** | **Has-a (Weak)** | **Is-a** |
| Ownership     | Strong (object belongs to the container) | Weak (object can exist independently) | Inherits base class properties |
| Lifespan      | Contained object is destroyed with container | Contained object can outlive container | Derived class exists as long as needed |
| Coupling      | High (tight coupling) | Loose coupling | Tight coupling |
| Flexibility   | Low | High | Low |

---

## 14. Final Tips
1. **Practice Code**: Make sure you can write simple class examples, constructor/destructor examples, and inheritance hierarchies.
2. **Focus on Concepts**: Understand the “why” behind OOP features (abstraction, encapsulation, inheritance, polymorphism).
3. **Syntax vs. Concepts**: Syntax is important, but clarity on concepts is crucial for deeper questions.
4. **Hands-On**: Write small programs demonstrating each concept—constructors, destructors, inheritance, polymorphism, etc.

---
