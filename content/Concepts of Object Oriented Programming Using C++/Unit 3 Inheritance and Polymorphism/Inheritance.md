
- Inheritance is a mechanism that allows one class (derived class) to acquire the properties and behavior of another class (base class).

- Promotes **code reusability** and **hierarchical classification** in object-oriented programming (OOP).

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