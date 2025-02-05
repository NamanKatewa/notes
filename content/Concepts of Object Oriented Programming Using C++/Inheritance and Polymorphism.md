
# Unit 3 - Inheritance and Polymorphism

## **Inheritance**

Inheritance is a mechanism in object-oriented programming (OOP) that allows one class (derived class) to acquire the properties and behavior of another class (base class). This promotes **code reusability** and **hierarchical classification** in C++.

---

## **Types of Inheritance**

### **1. Single Inheritance**

In single inheritance, a derived class inherits from a single base class. This is the simplest form of inheritance and is commonly used when a class needs to extend the functionality of another class.

#### **Syntax:**

```cpp
class BaseClass {
    // Base class members
};

class DerivedClass : public BaseClass {
    // Derived class members
};
```

#### **Example:**

```cpp
#include <iostream>
using namespace std;

class Parent {
public:
    void show() {
        cout << "This is the Parent class." << endl;
    }
};

class Child : public Parent {
};

int main() {
    Child obj;
    obj.show();  // Inherited from Parent class
    return 0;
}
```

---

### **2. Multiple Inheritance**

Multiple inheritance allows a derived class to inherit from more than one base class. This enables a class to inherit attributes and methods from multiple sources but can lead to complexities like the **diamond problem**.

#### **Syntax:**

```cpp
class Base1 {
    // Members of Base1
};

class Base2 {
    // Members of Base2
};

class Derived : public Base1, public Base2 {
    // Members of Derived
};
```

#### **Example:**

```cpp
#include <iostream>
using namespace std;

class ClassA {
public:
    void showA() { cout << "Class A" << endl; }
};

class ClassB {
public:
    void showB() { cout << "Class B" << endl; }
};

class Derived : public ClassA, public ClassB {
};

int main() {
    Derived obj;
    obj.showA();
    obj.showB();
    return 0;
}
```

---

### **3. Hierarchical Inheritance**

In hierarchical inheritance, multiple derived classes inherit from a single base class. This allows for code reuse among multiple classes that share common characteristics.

#### **Syntax:**

```cpp
class Base {
    // Base class members
};

class Derived1 : public Base {
    // Derived1 members
};

class Derived2 : public Base {
    // Derived2 members
};
```

#### **Example:**

```cpp
#include <iostream>
using namespace std;

class Parent {
public:
    void show() { cout << "Parent class" << endl; }
};

class Child1 : public Parent {
};

class Child2 : public Parent {
};

int main() {
    Child1 obj1;
    Child2 obj2;
    obj1.show();
    obj2.show();
    return 0;
}
```

---

## **Access Specifiers in Inheritance**

Access specifiers determine the visibility of inherited members in the derived class. The following table summarizes their behavior:

|Base Class Member|`public` Inheritance|`protected` Inheritance|`private` Inheritance|
|---|---|---|---|
|`public` members|Remain `public`|Become `protected`|Become `private`|
|`protected` members|Remain `protected`|Remain `protected`|Become `private`|
|`private` members|Not inherited|Not inherited|Not inherited|

#### **Example:**

```cpp
#include <iostream>
using namespace std;

class Base {
protected:
    int x;
};

class Derived : public Base {
public:
    void setX(int val) { x = val; }  // x is inherited as protected
};

int main() {
    Derived obj;
    obj.setX(10);
    return 0;
}
```

---

## **Abstract Classes & Pure Virtual Functions**

An **abstract class** is a class that cannot be instantiated and contains at least one **pure virtual function**. These classes provide a blueprint for other classes.

#### **Syntax:**

```cpp
class AbstractBase {
public:
    virtual void show() = 0;  // Pure virtual function
};

class Derived : public AbstractBase {
public:
    void show() { cout << "Implementation in Derived class" << endl; }
};
```

#### **Example:**

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() = 0;  // Pure virtual function
};

class Derived : public Base {
public:
    void show() { cout << "Implementation in Derived class" << endl; }
};

int main() {
    Derived obj;
    obj.show();
    return 0;
}
```

**Explanation:**

- The `Base` class contains a **pure virtual function** `show()`, making it an **abstract class**.
    
- The `Derived` class overrides `show()`, providing its own implementation.
    
- Since `Base` is abstract, we **cannot create objects** of `Base`. We can only use it as a reference or pointer to a `Derived` object.
    

---

## **Advanced Inheritance Concepts

## **1. Classification Hierarchy (Generalization-Specialization)**

A **classification hierarchy** in C++ represents a relationship where a **more general class** (superclass or base class) is used as a blueprint for **more specialized classes** (derived or child classes).

### **Key Features of Classification Hierarchy:**

- The base class defines common attributes and methods.
- Derived classes inherit these and extend functionality.
- "IS-A" relationship: A derived class **is a** type of base class.

### **Example of Classification Hierarchy (Generalization-Specialization)**

```cpp
#include <iostream>
using namespace std;

// Base class (General class)
class Animal {
protected:
    string name;
public:
    Animal(string n) : name(n) {}
    void eat() {
        cout << name << " is eating." << endl;
    }
};

// Derived class (Specialized class)
class Dog : public Animal {
public:
    Dog(string n) : Animal(n) {}
    void bark() {
        cout << name << " is barking." << endl;
    }
};

// Derived class (Another specialized class)
class Cat : public Animal {
public:
    Cat(string n) : Animal(n) {}
    void meow() {
        cout << name << " is meowing." << endl;
    }
};

int main() {
    Dog d("Buddy");
    d.eat();   // Inherited from Animal
    d.bark();  // Unique to Dog

    Cat c("Whiskers");
    c.eat();   // Inherited from Animal
    c.meow();  // Unique to Cat

    return 0;
}
```

### **Explanation:**

- `Animal` is the base class.
- `Dog` and `Cat` inherit `Animal` using public inheritance.
- `Dog` and `Cat` add their own unique behaviors (`bark()` and `meow()`).
- This demonstrates **Generalization-Specialization (IS-A relationship).**

---

## **2. Composition and Aggregation (Whole-Part Relationship)**

Inheritance is **not always the best choice**. Sometimes, objects are best described in a **Whole-Part** relationship instead of an **IS-A** relationship.  
This is where **Composition and Aggregation** come into play.

### **Composition**

- **Strong ownership**: The contained object **cannot exist independently** of the container.
- The lifetime of the contained object is **bound** to the lifetime of the container.
- Implemented using **member variables** inside the container class.

### **Aggregation**

- **Weak ownership**: The contained object **can exist independently**.
- The lifetime of the contained object **is not tied** to the container.
- Implemented using **pointers or references**.

---

### **3. Composition Example (Strong Relationship)**

```cpp
#include <iostream>
using namespace std;

// Component class
class Engine {
public:
    Engine() {
        cout << "Engine created!" << endl;
    }
    void start() {
        cout << "Engine started!" << endl;
    }
    ~Engine() {
        cout << "Engine destroyed!" << endl;
    }
};

// Whole class
class Car {
private:
    Engine engine; // Composition: Engine is a part of Car
public:
    Car() {
        cout << "Car created!" << endl;
    }
    void start() {
        engine.start(); // Car uses Engine
        cout << "Car started!" << endl;
    }
    ~Car() {
        cout << "Car destroyed!" << endl;
    }
};

int main() {
    Car myCar;
    myCar.start();
    return 0;
}
```

### **Explanation:**

- `Engine` is an integral part of `Car`.
- When a `Car` object is created, an `Engine` object is automatically created inside it.
- When the `Car` object is destroyed, the `Engine` object is also destroyed.
- This represents **Composition (Strong ownership).**

---

### **4. Aggregation Example (Weak Relationship)**

```cpp
#include <iostream>
using namespace std;

class Engine {
public:
    Engine() {
        cout << "Engine created!" << endl;
    }
    void start() {
        cout << "Engine started!" << endl;
    }
    ~Engine() {
        cout << "Engine destroyed!" << endl;
    }
};

// Whole class
class Car {
private:
    Engine* engine; // Aggregation: Engine exists independently
public:
    Car(Engine* e) : engine(e) { // Injecting existing Engine
        cout << "Car created!" << endl;
    }
    void start() {
        engine->start();
        cout << "Car started!" << endl;
    }
    ~Car() {
        cout << "Car destroyed!" << endl;
    }
};

int main() {
    Engine myEngine;  // Created independently
    Car myCar(&myEngine); // Passing existing Engine
    myCar.start();

    return 0;
}
```

### **Explanation:**

- The `Engine` object is created independently in `main()`.
- The `Car` class only **refers** to an existing `Engine` object via a pointer.
- When the `Car` is destroyed, the `Engine` still exists.
- This represents **Aggregation (Weak ownership).**

---

## **5. Key Differences: Classification Hierarchy vs. Composition/Aggregation**

|Feature|Classification Hierarchy (IS-A)|Composition (HAS-A, Strong)|Aggregation (HAS-A, Weak)|
|---|---|---|---|
|Relationship|IS-A|HAS-A|HAS-A|
|Lifetime Dependency|Derived class exists independently|Contained object depends on the whole|Contained object exists independently|
|Example|`Dog IS-A Animal`|`Car HAS-A Engine (Composition)`|`Car HAS-A Engine (Aggregation)`|
|Implementation|Public inheritance|Member object (no pointers)|Pointer/reference member|

---

## **6. When to Use What?**

|Situation|Best Approach|
|---|---|
|If an object **is a** specialized version of another|**Use Inheritance (IS-A)**|
|If an object **is a part of** another and cannot exist separately|**Use Composition (HAS-A, Strong)**|
|If an object **is a part of** another but can exist independently|**Use Aggregation (HAS-A, Weak)**|

---

## **Polymorphism**

Polymorphism is one of the four fundamental principles of Object-Oriented Programming (OOP) in C++. It allows functions and operators to behave differently based on the context, leading to code that is more **flexible, scalable, and reusable**.

---

## **Types of Polymorphism**

Polymorphism is broadly classified into **Compile-time Polymorphism** and **Run-time Polymorphism**.

|**Type**|**Description**|**Examples**|
|---|---|---|
|**Compile-time Polymorphism**|Function behavior is determined at **compile time**.|Function Overloading, Operator Overloading, Templates|
|**Run-time Polymorphism**|Function behavior is determined at **run time**.|Function Overriding (Virtual Functions)|

---

# **1. Compile-time Polymorphism**

Compile-time polymorphism is achieved through **Function Overloading** and **Operator Overloading**. These allow the same function or operator to perform different tasks based on the number or type of arguments.

### **1.1 Function Overloading**

Function overloading allows multiple functions with the **same name** but **different parameter lists** (number or type of arguments). The compiler determines which function to call based on the arguments provided.

### **Example: Function Overloading**

```cpp
#include <iostream>
using namespace std;

class Math {
public:
    // Function to add two integers
    int add(int a, int b) {
        return a + b;
    }

    // Function to add three integers
    int add(int a, int b, int c) {
        return a + b + c;
    }

    // Function to add two floating-point numbers
    double add(double a, double b) {
        return a + b;
    }
};

int main() {
    Math obj;
    cout << "Sum of 2 and 3: " << obj.add(2, 3) << endl;
    cout << "Sum of 2, 3, and 5: " << obj.add(2, 3, 5) << endl;
    cout << "Sum of 2.5 and 3.5: " << obj.add(2.5, 3.5) << endl;

    return 0;
}
```

### **Explanation:**

- `add(int, int)`, `add(int, int, int)`, and `add(double, double)` are **overloaded** functions.
- The compiler determines which function to call based on **argument types and count**.

---

### **1.2 Operator Overloading**

Operator overloading allows C++ operators (`+`, `-`, `*`, etc.) to be **redefined** for user-defined classes. This enhances code readability and allows intuitive use of objects.

### **Example: Operator Overloading (`+` for Complex Numbers)**

```cpp
#include <iostream>
using namespace std;

class Complex {
private:
    double real, imag;
public:
    Complex(double r = 0, double i = 0) : real(r), imag(i) {}

    // Overloading the + operator
    Complex operator+(const Complex& other) {
        return Complex(real + other.real, imag + other.imag);
    }

    void display() {
        cout << real << " + " << imag << "i" << endl;
    }
};

int main() {
    Complex c1(3, 4), c2(2, 5);
    Complex c3 = c1 + c2; // Using overloaded +
    cout << "Sum: ";
    c3.display();

    return 0;
}
```

### **Explanation:**

- The `+` operator is overloaded for `Complex` numbers.
- `operator+` function adds the real and imaginary parts of two `Complex` objects.
- This enables intuitive mathematical operations on objects.

**Commonly Overloaded Operators in C++**

- Arithmetic operators: `+`, `-`, `*`, `/`
- Comparison operators: `==`, `!=`, `<`, `>`
- Assignment operators: `=`, `+=`, `-=`
- Stream operators: `<<`, `>>`

---

# **2. Run-time Polymorphism**

Run-time polymorphism is achieved using **Function Overriding** (also known as **Dynamic Method Dispatch**). It is implemented using **virtual functions** and enables function behavior to be determined at run-time.

### **2.1 Function Overriding**

Function overriding allows a **derived class** to **redefine** a function from its **base class** with the **same signature**.

### **Example: Function Overriding (Run-time Polymorphism)**

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() { // Virtual function
        cout << "Base class show()" << endl;
    }
};

class Derived : public Base {
public:
    void show() override { // Overriding function
        cout << "Derived class show()" << endl;
    }
};

int main() {
    Base* basePtr;
    Derived obj;
    
    basePtr = &obj;
    basePtr->show(); // Calls Derived's show() due to virtual function

    return 0;
}
```

### **Explanation:**

- `Base::show()` is marked `virtual`, enabling function overriding.
- When calling `basePtr->show()`, **the derived class function is called instead of the base class function**.
- This is possible due to **dynamic binding (late binding).**

---

# **3. Differences: Function Overloading vs. Function Overriding**

|Feature|Function Overloading|Function Overriding|
|---|---|---|
|**Definition**|Multiple functions with the same name but different parameters|Derived class redefines a function of the base class|
|**Type**|Compile-time polymorphism|Run-time polymorphism|
|**Signature**|Function name is the same, but parameters differ|Function name and parameters are the same|
|**Inheritance**|Not required|Required|
|**Keyword Used**|No special keyword required|`virtual` keyword in the base class|

---

# **Pointers and Virtual Functions**

In C++, **pointers and virtual functions** are crucial for implementing **dynamic behavior**, **memory management**, and **run-time polymorphism**. Understanding these concepts ensures efficient and flexible object-oriented programming.

---

## **1. Pointer to Objects**

A **pointer to an object** allows us to access the object's members using the arrow (`->`) operator. This is useful for **dynamic memory allocation** and **polymorphism**.

### **Declaring a Pointer to an Object**

```cpp
ClassName *pointer;
```

- This declares a pointer that can store the address of an object of `ClassName`.

### **Example: Pointer to Objects**

```cpp
#include <iostream>
using namespace std;

class Car {
public:
    string brand;
    int speed;

    void show() {
        cout << "Brand: " << brand << ", Speed: " << speed << " km/h" << endl;
    }
};

int main() {
    Car car1 = {"Tesla", 150};   // Normal object
    Car *ptr = &car1;            // Pointer to object

    ptr->show();                 // Accessing function via pointer

    return 0;
}
```

### **Explanation**

- `ptr` is a **pointer** to an object of `Car`.
- We use `ptr->show();` instead of `(*ptr).show();` for cleaner syntax.

---

## **2. `this` Pointer**

The `this` pointer is an **implicit pointer available in all non-static member functions** of a class. It points to the current object that invoked the member function.

### **Use Cases of `this` Pointer**

1. **Avoiding name conflicts between instance variables and parameters**
2. **Returning the current object in method chaining**

### **Example: Using `this` Pointer**

```cpp
#include <iostream>
using namespace std;

class Student {
private:
    string name;
public:
    Student(string name) {
        this->name = name;  // Resolving name conflict
    }

    void show() {
        cout << "Student Name: " << this->name << endl;
    }
};

int main() {
    Student s1("Naman");
    s1.show();

    return 0;
}
```

### **Explanation**

- `this->name = name;` ensures that we are referring to the **instance variable** and not the **parameter**.
- The `this` pointer stores the address of the calling object (`s1` in this case).

---

## **3. Virtual Functions**

A **virtual function** is a member function that is declared in a **base class** and is meant to be **overridden in derived classes**. It allows **run-time polymorphism**, enabling function calls to be resolved dynamically.

### **Why Use Virtual Functions?**

- Ensures the **correct function** is called when using **base class pointers**.
- Prevents **slicing** (where only the base class part of an object is considered).
- Enables **dynamic binding (late binding)** instead of compile-time binding.

---

### **4. Example: Without Virtual Functions (Incorrect Behavior)**

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    void show() {  // Not virtual
        cout << "Base class show()" << endl;
    }
};

class Derived : public Base {
public:
    void show() {  // Overriding
        cout << "Derived class show()" << endl;
    }
};

int main() {
    Base* basePtr;
    Derived obj;
    
    basePtr = &obj;
    basePtr->show();  // Calls Base::show() instead of Derived::show() (Incorrect)

    return 0;
}
```

### **Explanation**

- Since `show()` is **not virtual**, `basePtr->show();` calls `Base::show()` instead of `Derived::show()`, leading to **incorrect behavior**.

---

### **5. Example: Using Virtual Functions (Correct Behavior)**

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() {  // Virtual function
        cout << "Base class show()" << endl;
    }
};

class Derived : public Base {
public:
    void show() override {  // Overriding
        cout << "Derived class show()" << endl;
    }
};

int main() {
    Base* basePtr;
    Derived obj;
    
    basePtr = &obj;
    basePtr->show();  // Calls Derived::show() (Correct behavior)

    return 0;
}
```

### **Explanation**

- `show()` in `Base` is **declared as virtual**, enabling **dynamic binding**.
- `basePtr->show();` correctly calls `Derived::show()` at **run-time**.

---

## **6. Virtual Destructors**

If a base class has **virtual functions**, it should also have a **virtual destructor**. Otherwise, deleting a derived class object using a base class pointer may cause **memory leaks**.

### **Example: Virtual Destructor**

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    Base() { cout << "Base Constructor\n"; }
    virtual ~Base() { cout << "Base Destructor\n"; }  // Virtual destructor
};

class Derived : public Base {
public:
    Derived() { cout << "Derived Constructor\n"; }
    ~Derived() { cout << "Derived Destructor\n"; }  // Destructor
};

int main() {
    Base* ptr = new Derived();
    delete ptr;  // Calls both Derived and Base destructors

    return 0;
}
```

### **Explanation**

- Without a **virtual destructor**, `~Derived()` would **not be called**, leading to memory leaks.

---

## **7. Pure Virtual Functions and Abstract Classes**

A **pure virtual function** is a function that **must be overridden** by derived classes. A class containing at least **one pure virtual function** is called an **abstract class**.

### **Example: Abstract Class**

```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    virtual void draw() = 0;  // Pure virtual function (must be overridden)
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing Circle" << endl;
    }
};

int main() {
    // Shape s;  // Error: Cannot instantiate an abstract class
    Circle c;
    c.draw();

    return 0;
}
```

### **Explanation**

- `Shape` contains a **pure virtual function** (`draw() = 0`), making it an **abstract class**.
- **Abstract classes cannot be instantiated**.
- `Circle` overrides `draw()`, allowing instantiation.

---

## **8. Key Differences: Normal Function vs. Virtual Function vs. Pure Virtual Function**

|Feature|Normal Function|Virtual Function|Pure Virtual Function|
|---|---|---|---|
|**Overriding**|Optional|Allowed|Must be overridden|
|**Binding Type**|Compile-time (Early binding)|Run-time (Late binding)|Run-time (Late binding)|
|**Declaration**|Normal function|`virtual` keyword|`virtual ... = 0;`|
|**Object Instantiation**|Possible|Possible|Not possible (Abstract Class)|

---

## **9. Summary**

| Concept                    | Description                                                             |
| -------------------------- | ----------------------------------------------------------------------- |
| **Pointer to Objects**     | Allows accessing objects dynamically using pointers.                    |
| **`this` Pointer**         | Implicit pointer referring to the current object.                       |
| **Virtual Functions**      | Enable **run-time polymorphism** (dynamic function calls).              |
| **Virtual Destructors**    | Prevent memory leaks when deleting objects through base class pointers. |
| **Pure Virtual Functions** | Enforce overriding in derived classes (abstract classes).               |

---

### **10. When to Use Virtual Functions?**

- When you need **run-time polymorphism**  
- When working with **base class pointers**  
- When designing an **abstract base class** for extensibility
