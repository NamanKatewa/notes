## **Inheritance**

Inheritance is a mechanism that allows one class (derived class) to acquire the properties and behavior of another class (base class). This promotes **code reusability** and **hierarchical classification** in object-oriented programming (OOP).

### **Types of Inheritance**

#### **Single Inheritance**

A derived class inherits from a single base class.

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

#### **Multiple Inheritance**

A derived class inherits from more than one base class.

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

#### **Hierarchical Inheritance**

Multiple derived classes inherit from a single base class.

```cpp
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

#### **Multilevel Inheritance**

A derived class inherits from another derived class.

```cpp
class GrandParent {
public:
    void show() { cout << "Grandparent class" << endl; }
};

class Parent : public GrandParent {
};

class Child : public Parent {
};

int main() {
    Child obj;
    obj.show();
    return 0;
}
```

#### **Hybrid Inheritance (Virtual Inheritance)**

A combination of different inheritance types, often requiring **virtual inheritance** to prevent ambiguity.

---

### **Access Specifiers in Inheritance**

|Base Class Member|`public` Inheritance|`protected` Inheritance|`private` Inheritance|
|---|---|---|---|
|`public` members|Remain `public`|Become `protected`|Become `private`|
|`protected` members|Remain `protected`|Remain `protected`|Become `private`|
|`private` members|Not inherited|Not inherited|Not inherited|

Example:

```cpp
class Base {
protected:
    int x;
};

class Derived : public Base {
public:
    void setX(int val) { x = val; }  // x is inherited as protected
};
```

---

### **Abstract Classes & Pure Virtual Functions**

An **abstract class** is a class that has at least one **pure virtual function** (a function declared with `= 0`).  
Example:

```cpp
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

---

## **Advanced Inheritance Concepts**

### **Aggregation vs. Composition**

**Aggregation**: The contained object **can exist independently** of the container class.

```cpp
class Engine {
public:
    void start() { cout << "Engine started" << endl; }
};

class Car {
public:
    Engine *engine;
    Car(Engine *e) { engine = e; }
};

int main() {
    Engine e;
    Car myCar(&e);
    myCar.engine->start();
    return 0;
}
```

**Composition**: The contained object **cannot exist independently** of the container class.

```cpp
class Engine {
public:
    void start() { cout << "Engine started" << endl; }
};

class Car {
private:
    Engine engine;  // Engine is part of Car
public:
    void startCar() { engine.start(); }
};

int main() {
    Car myCar;
    myCar.startCar();
    return 0;
}
```

---

## **Polymorphism in C++**

Polymorphism allows the same function or operator to behave differently depending on the context.

### **Compile-time Polymorphism (Static Binding)**

#### **Function Overloading**

```cpp
class Math {
public:
    void add(int a, int b) {
        cout << "Sum: " << a + b << endl;
    }

    void add(double a, double b) {
        cout << "Sum: " << a + b << endl;
    }
};

int main() {
    Math obj;
    obj.add(2, 3);
    obj.add(2.5, 3.5);
    return 0;
}
```

#### **Operator Overloading**

```cpp
class Complex {
public:
    int real, imag;

    Complex(int r, int i) : real(r), imag(i) {}

    Complex operator+(const Complex &c) {
        return Complex(real + c.real, imag + c.imag);
    }

    void display() {
        cout << real << " + " << imag << "i" << endl;
    }
};

int main() {
    Complex c1(2, 3), c2(4, 5);
    Complex c3 = c1 + c2;
    c3.display();
    return 0;
}
```

---

### **Run-time Polymorphism (Dynamic Binding)**

#### **Function Overriding with Virtual Functions**

```cpp
class Base {
public:
    virtual void show() { cout << "Base class" << endl; }
};

class Derived : public Base {
public:
    void show() override { cout << "Derived class" << endl; }
};

int main() {
    Base *b;
    Derived d;
    b = &d;
    b->show();  // Calls Derived class show() due to dynamic binding
    return 0;
}
```

---

## **Pointers and Virtual Functions**

### **Pointer to Objects**

```cpp
class Demo {
public:
    void show() { cout << "Pointer to object example" << endl; }
};

int main() {
    Demo obj;
    Demo *ptr = &obj;
    ptr->show();
    return 0;
}
```

### **this Pointer**

```cpp
class Example {
public:
    int x;
    Example(int x) { this->x = x; }  // Using this pointer
    void show() { cout << "Value: " << x << endl; }
};

int main() {
    Example obj(10);
    obj.show();
    return 0;
}
```

---
