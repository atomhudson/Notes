## **1. What is a Class in Java?**

A **class** is a blueprint or template to create objects. It defines **fields (variables)** and **methods (functions)** to describe the behavior and state of objects.

**Example:**

```java
class Car {
    String color;
    void drive() {
        System.out.println("Car is driving");
    }
}
```

---

## **2. Types of Classes in Java**

Java supports several types of classes based on their usage and scope.

### **A. Concrete Class**

* A **normal class** that can be instantiated (you can create objects from it).
* Contains fully implemented methods.
* Does not use the `abstract` keyword.

**Example:**

```java
class Dog {
    void bark() {
        System.out.println("Barking");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog(); // concrete class can be instantiated
        d.bark();
    }
}
```

---

### **B. Abstract Class**

* Declared using the `abstract` keyword.
* **Cannot be instantiated directly**.
* Can have **abstract methods (without body)** and **concrete methods (with body)**.
* Used when you want to provide a **base class** with partial implementation.

**Example:**

```java
abstract class Animal {
    abstract void sound(); // abstract method
    void eat() {           // concrete method
        System.out.println("Eating");
    }
}

class Cat extends Animal {
    void sound() {
        System.out.println("Meow");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a = new Cat();
        a.sound();
        a.eat();
    }
}
```

---

### **C. Final Class**

* Declared with the `final` keyword.
* **Cannot be inherited** (no subclass can extend it).
* Used for security, utility classes, or to prevent modification.

**Example:**

```java
final class MathUtils {
    static int square(int x) {
        return x * x;
    }
}

// class MyMath extends MathUtils {} // Error: cannot inherit final class
```

---

### **D. Static Nested Class**

* A **nested class** declared as `static`.
* Does not need an instance of the outer class.
* Can access **only static members** of the outer class directly.

**Example:**

```java
class Outer {
    static int data = 10;
    static class Inner {
        void show() {
            System.out.println("Data: " + data);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Outer.Inner inner = new Outer.Inner();
        inner.show();
    }
}
```

---

### **E. Inner (Non-static Nested) Class**

* Defined **inside another class**, without `static`.
* Can access **all members** (including private) of the outer class.
* Requires an instance of the outer class to be created.

**Example:**

```java
class Outer {
    private String msg = "Hello";
    class Inner {
        void display() {
            System.out.println(msg);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Outer outer = new Outer();
        Outer.Inner inner = outer.new Inner();
        inner.display();
    }
}
```

---

### **F. Local Inner Class**

* Declared **inside a method or block**.
* Scope is limited to that method/block.
* Can access final or effectively final local variables.

**Example:**

```java
class Outer {
    void print() {
        final int num = 100;
        class Inner {
            void show() {
                System.out.println("Number: " + num);
            }
        }
        Inner inner = new Inner();
        inner.show();
    }
}
```

---

### **G. Anonymous Inner Class**

* A class **without a name**, created for **immediate use**.
* Used to override methods of classes or interfaces on the fly.

**Example:**

```java
interface Greeting {
    void sayHello();
}

public class Main {
    public static void main(String[] args) {
        Greeting g = new Greeting() { // anonymous inner class
            public void sayHello() {
                System.out.println("Hello World!");
            }
        };
        g.sayHello();
    }
}
```

---

### **H. POJO (Plain Old Java Object)**

* A simple class that contains:

    * **Private fields**
    * **Public getters and setters**
    * **No complex logic**
* Commonly used in frameworks like Hibernate, Spring.

**Example:**

```java
public class Employee {
    private String name;
    private int age;

    public String getName() { return name; }
    public void setName(String name) { this.name = name; }

    public int getAge() { return age; }
    public void setAge(int age) { this.age = age; }
}
```

---

## **3. Class Modifiers**

* **Access Modifiers:** `public`, `protected`, `default` (package-private), `private` (inner classes only).
* **Non-Access Modifiers:** `abstract`, `final`, `static`, `strictfp`.

---

## **4. Key Points**

1. **Abstract classes** cannot be instantiated.
2. **Final classes** cannot be extended.
3. **Static nested classes** do not require an object of the outer class.
4. **Inner classes** can access outer class’s private members.
5. **Anonymous classes** are great for one-time implementations.
6. Classes can be **top-level** (outer) or **nested**.

---