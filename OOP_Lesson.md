# 🧱 Object-Oriented Programming (OOP) Concepts

![java-badge](https://img.shields.io/badge/Language-Java-red)
![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🧩 Definition

**Object-Oriented Programming (OOP)** is a programming approach based on the concept of **objects**, which can contain **data** (fields or attributes) and **methods** (functions or behaviors).  
It focuses on modeling real-world entities into software objects that interact with one another to perform tasks.  
In Java, everything revolves around **classes** and **objects**, making it a fully object-oriented language.

---

## ⚙️ How It Works & Why It’s Important

In OOP, you create a **class** that defines a blueprint or model for an object. Then, you create **objects (instances)** of that class to use in your program.  
OOP helps in organizing complex programs into smaller, reusable, and more manageable parts.

### 💡 Importance of OOP
1. 🧱 **Modularity** – Code is divided into classes, making it easier to manage.  
2. 🔁 **Reusability** – You can reuse existing classes and extend them.  
3. 🧠 **Maintainability** – Errors are easier to fix and update because each class works independently.  
4. 🧩 **Scalability** – It’s easier to add new features without breaking the existing code.

---

## 🧠 Four Core Principles of OOP

1. **Encapsulation**  
   - Wrapping data (variables) and methods that operate on that data into one unit (class).  
   - Example: Using `private` fields and `public` getter/setter methods.

2. **Inheritance**  
   - Allows a class to **inherit** features (methods and fields) from another class.  
   - Promotes code reusability and avoids redundancy.

3. **Polymorphism**  
   - “Many forms” — allows one interface to be used for different types of objects.  
   - Example: Method overriding and overloading.

4. **Abstraction**  
   - Hiding complex implementation details and showing only the necessary features.  
   - Example: Using abstract classes and interfaces.

---

## 💻 Three Examples of OOP in Java

---

### 🟢 **Encapsulation Explained**

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

#### 🔹 Definition

**Encapsulation** is one of the four main principles of Object-Oriented Programming (OOP).
It means **binding data (variables)** and **methods (functions)** that operate on that data into a single unit — a class.
It also means **restricting direct access** to some of an object’s components, usually by making variables **private** and providing **public methods (getters and setters)** to access or modify them.

---

#### 🔹 How It Works

Encapsulation works through **access modifiers**:

* `private` — members are accessible only within the same class.
* `public` — accessible from anywhere.
* `protected` — accessible within the same package and subclasses.
* `default` — accessible only within the same package.

By declaring data as **private**, you protect it from being directly modified by outside code.
Instead, other classes use **getter** and **setter methods** to read or change the data safely.

---

#### 🔹 Why It’s Important

* ✅ **Data protection** – prevents unwanted changes to variables.
* ✅ **Control** – allows validation before updating data.
* ✅ **Flexibility** – internal changes won’t affect other parts of the program.
* ✅ **Easier maintenance** – you can modify implementation without breaking the code that uses the class.

---

#### 🔹 Example 1 – Basic Encapsulation

```java
public class Student {
    private String name;
    private int age;

    // Getter
    public String getName() {
        return name;
    }

    // Setter
    public void setName(String name) {
        this.name = name;
    }

    // Getter
    public int getAge() {
        return age;
    }

    // Setter with validation
    public void setAge(int age) {
        if (age > 0) {
            this.age = age;
        } else {
            System.out.println("Invalid age!");
        }
    }
}
```

---

#### 🔹 Example 2 – Using Encapsulation in Main Program

```java
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();
        s1.setName("Khiel");
        s1.setAge(17);

        System.out.println("Name: " + s1.getName());
        System.out.println("Age: " + s1.getAge());
    }
}
```

🧠 This ensures that no one can set a negative age or access variables directly.

---

#### 🔹 Example 3 – Encapsulation with a Bank Account

```java
public class BankAccount {
    private double balance;

    public void deposit(double amount) {
        if (amount > 0)
            balance += amount;
    }

    public void withdraw(double amount) {
        if (amount <= balance)
            balance -= amount;
        else
            System.out.println("Insufficient funds");
    }

    public double getBalance() {
        return balance;
    }
}
```

---

#### 🔹 Where It’s Commonly Used

Encapsulation is used in almost all **Java programs**:

* In **banking systems** (to protect account balances).
* In **student information systems** (to hide student data).
* In **games** (to keep player stats secure and controlled).
* In **API design** (to hide implementation details from users).

---

### 🧠 Inheritance in Java

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

#### 🔹 Definition

**Inheritance** is one of the main concepts of Object-Oriented Programming (OOP).
It allows one class (called the **subclass** or **child class**) to **inherit the properties and methods** of another class (called the **superclass** or **parent class**).

This helps developers **reuse code**, **reduce duplication**, and **create a clear class hierarchy**.

#### 🔹 How It Works

In Java, inheritance is done using the keyword **`extends`**.
When a subclass extends a superclass, it automatically gets access to all **non-private** variables and methods of the parent.
You can also **override** methods to change their behavior in the child class.

```java
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

// Dog inherits from Animal
class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}
```

Here, `Dog` can use both `eat()` (from `Animal`) and `bark()` (its own method).

#### 🔹 Why It’s Important

* Promotes **code reusability** (you don’t need to rewrite existing logic).
* Makes programs **easier to maintain** and **extend**.
* Enables **polymorphism**, where a subclass object can be treated as an instance of its parent class.

#### 🔹 Examples of Inheritance

**Example 1 – Basic Inheritance**

```java
class Vehicle {
    void run() {
        System.out.println("Vehicle is running...");
    }
}

class Car extends Vehicle {
    void honk() {
        System.out.println("Car is honking!");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        car.run();   // Inherited from Vehicle
        car.honk();  // Car’s own method
    }
}
```

**Example 2 – Method Overriding**

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}
```

**Example 3 – Multilevel Inheritance**

```java
class Animal {
    void eat() { System.out.println("Eating..."); }
}

class Mammal extends Animal {
    void walk() { System.out.println("Walking..."); }
}

class Dog extends Mammal {
    void bark() { System.out.println("Barking..."); }
}

public class Test {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();
        d.walk();
        d.bark();
    }
}
```

#### 🔹 Where It’s Commonly Used

* **GUI Frameworks**: Swing components (e.g., `JFrame` inherits from `Frame`).
* **Game development**: Player, Enemy, and NPC classes inherit from a base `Character`.
* **Enterprise apps**: Shared base classes for logging, validation, or data models.

---

### 🟣 **Polymorphism**

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

### 🔹 **Definition**

**Polymorphism** in Java means *“many forms.”*
It allows one interface (or reference type) to represent multiple possible underlying data types. In simple words, **the same method can behave differently depending on the object that calls it.**

Polymorphism is one of the **four main pillars of Object-Oriented Programming (OOP)** — along with encapsulation, inheritance, and abstraction.

---

### 🔹 **How It Works**

Polymorphism works mainly through **method overriding** and **method overloading**:

1. **Compile-time polymorphism (Static):**

   * Achieved using **method overloading**.
   * The method that gets executed is determined at *compile time* based on the method signature (number and type of parameters).

2. **Runtime polymorphism (Dynamic):**

   * Achieved using **method overriding**.
   * The method that gets executed is determined *at runtime* based on the actual object type (not the reference type).

---

### 🔹 **Why It Is Important**

* It allows **code reusability** and **flexibility**.
* It makes programs easier to **extend** and **maintain**.
* It supports **“write once, use many times”** — enabling developers to design more generic and reusable code.

---

### 🔹 **Examples**

#### ✅ Example 1 — *Method Overloading (Compile-time Polymorphism)*

```java
class MathOperation {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        MathOperation m = new MathOperation();
        System.out.println(m.add(5, 10));      // Output: 15
        System.out.println(m.add(3.2, 2.8));   // Output: 6.0
    }
}
```

---

#### ✅ Example 2 — *Method Overriding (Runtime Polymorphism)*

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    void sound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a1 = new Dog();
        Animal a2 = new Cat();

        a1.sound();  // Output: Dog barks
        a2.sound();  // Output: Cat meows
    }
}
```

---

#### ✅ Example 3 — *Polymorphism with Interfaces*

```java
interface Shape {
    void draw();
}

class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing a circle");
    }
}

class Square implements Shape {
    public void draw() {
        System.out.println("Drawing a square");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape s1 = new Circle();
        Shape s2 = new Square();

        s1.draw();  // Output: Drawing a circle
        s2.draw();  // Output: Drawing a square
    }
}
```

---

### 🔹 **Where It Is Commonly Used**

* In **real-world applications**, polymorphism is widely used in:

  * **GUI frameworks** (e.g., different buttons having different click behaviors).
  * **Game development** (e.g., different enemies acting differently but sharing the same “attack” method).
  * **Collections Framework** in Java (e.g., `List list = new ArrayList();` — where the `List` interface can refer to different list implementations).

---

### 🟢 Abstraction in Java

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

### 🧩 **Definition**

**Abstraction** in Java is the process of **hiding complex implementation details** and showing only the **essential features** of an object or system.
It focuses on *what an object does* rather than *how it does it*.

In simple words, abstraction lets you use a method or class **without knowing the internal code** that makes it work.

Example in real life:
When you drive a car, you use the steering wheel, brake, and accelerator — you don’t need to know how the engine processes fuel. That’s **abstraction**.

---

### ⚙️ **How It Works**

In Java, abstraction is achieved in two ways:

1. **Abstract Classes** – Classes declared with the `abstract` keyword.

   * May have **abstract methods** (without a body) and **non-abstract methods** (with implementation).
2. **Interfaces** – Define a set of methods that a class must implement.

   * They provide **100% abstraction** (in Java 8+, they can also have `default` and `static` methods).

---

### 💡 **Why It’s Important**

* Simplifies code and increases readability.
* Helps developers focus on *what* an object does, not *how* it does it.
* Makes maintenance and updates easier.
* Promotes reusability and reduces duplication.

---

### 🧠 **Examples**

#### 🔹 Example 1: Abstract Class

```java
abstract class Animal {
    abstract void sound();  // abstract method (no body)

    void sleep() {          // concrete method
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks!");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound();
        dog.sleep();
    }
}
```

**Output:**

```
Dog barks!
Sleeping...
```

---

#### 🔹 Example 2: Interface

```java
interface Vehicle {
    void start();  // abstract method
}

class Car implements Vehicle {
    public void start() {
        System.out.println("Car engine starting...");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle v = new Car();
        v.start();
    }
}
```

**Output:**

```
Car engine starting...
```

---

#### 🔹 Example 3: Real-Life Analogy in Code

```java
interface Payment {
    void processPayment();
}

class CreditCardPayment implements Payment {
    public void processPayment() {
        System.out.println("Processing credit card payment...");
    }
}

class PayPalPayment implements Payment {
    public void processPayment() {
        System.out.println("Processing PayPal payment...");
    }
}

public class Main {
    public static void main(String[] args) {
        Payment p = new PayPalPayment();
        p.processPayment();
    }
}
```

**Output:**

```
Processing PayPal payment...
```

---

### 🌍 **Where It’s Commonly Used**

* In large applications to separate **logic** and **implementation** (e.g., database operations, APIs).
* In frameworks like **Spring** and **JavaFX**, where developers use interfaces and abstract classes.
* When defining **common behavior** for multiple related classes (like `Animal`, `Shape`, or `Vehicle`).

---

# 🧱 Classes and Objects

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧩 Definition

In **Java**, a **class** is a **blueprint** or **template** for creating objects. It defines what data (called **fields** or **attributes**) and actions (called **methods**) an object can have.
An **object** is an **instance** of a class — meaning it’s a real, usable version of that blueprint.

> 📘 Example:
> Think of a **class** as a “cookie cutter,” and the **objects** as the “cookies” made from it.

---

## ⚙️ How It Works

When you create a class, you describe:

* What data the object should store (fields or variables)
* What actions the object can perform (methods)
* How it can be constructed (constructors)

Then, you create an object (an instance) of that class using the `new` keyword.

---

## 🌟 Why It’s Important

Classes and objects are the **foundation of Object-Oriented Programming (OOP)**.
They help you:

* Organize code into reusable, logical units.
* Model real-world things (like cars, students, or bank accounts).
* Encapsulate data and behavior together.

---

## 💻 Examples

### 🧠 Example 1 — Creating a Simple Class and Object

```java
class Car {
    String color;
    String brand;

    void drive() {
        System.out.println("The car is driving...");
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car(); // Object creation
        myCar.color = "Red";
        myCar.brand = "Toyota";
        myCar.drive();
    }
}
```

### 🧠 Example 2 — Using a Constructor

```java
class Student {
    String name;
    int age;

    // Constructor
    Student(String n, int a) {
        name = n;
        age = a;
    }

    void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student("Khiel", 17);
        s1.displayInfo();
    }
}
```

### 🧠 Example 3 — Multiple Objects from One Class

```java
class Dog {
    String name;

    void bark() {
        System.out.println(name + " is barking!");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d1 = new Dog();
        Dog d2 = new Dog();

        d1.name = "Buddy";
        d2.name = "Charlie";

        d1.bark();
        d2.bark();
    }
}
```

---

## 🧭 Where It’s Commonly Used

* In **applications** that model real-world entities (e.g., students, cars, employees)
* In **game development**, where every character or item is an object
* In **software systems**, to organize code into meaningful modules
* In **OOP design**, where reusability, maintainability, and clarity are key

# 🧱 Constructor Overloading

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧩 Definition

**Constructor Overloading** in Java means **having more than one constructor** in the same class **with different parameter lists** (different number or types of parameters).

It allows an object to be created in **multiple ways**, giving flexibility depending on what information is available during object creation.

---

## ⚙️ How It Works

When you create an object using the `new` keyword, **Java automatically decides which constructor to call** based on the **arguments** you pass.

Each constructor must have a **unique parameter list**, but they all share the **same name as the class**.

### 🔹 Example:

```java
class Student {
    String name;
    int age;
    String section;

    // Constructor 1: No parameters
    Student() {
        name = "Unknown";
        age = 0;
        section = "N/A";
    }

    // Constructor 2: One parameter
    Student(String n) {
        name = n;
        age = 0;
        section = "N/A";
    }

    // Constructor 3: Two parameters
    Student(String n, int a) {
        name = n;
        age = a;
        section = "N/A";
    }

    // Constructor 4: Three parameters
    Student(String n, int a, String s) {
        name = n;
        age = a;
        section = s;
    }

    void display() {
        System.out.println(name + " | " + age + " | " + section);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();
        Student s2 = new Student("Khiel");
        Student s3 = new Student("Mark", 18);
        Student s4 = new Student("Ella", 17, "ICT-12A");

        s1.display();
        s2.display();
        s3.display();
        s4.display();
    }
}
```

📘 **Output:**

```
Unknown | 0 | N/A
Khiel | 0 | N/A
Mark | 18 | N/A
Ella | 17 | ICT-12A
```

---

## 💡 Why It’s Important

1. Makes your class **flexible** and **easier to use**.
2. Reduces **repetition** by allowing different initialization options.
3. Helps when some information is **optional** or **unknown** during object creation.

---

## 🧰 Rules of Constructor Overloading

✅ Constructors must have the **same name** as the class.
✅ Each constructor must have a **different parameter list**.
✅ Constructors **can call each other** using `this()` (to avoid code duplication).

---

### 🔹 Example: Using `this()` to Call Another Constructor

```java
class Car {
    String brand;
    String color;
    int year;

    Car() {
        this("Toyota", "White", 2020); // calls the 3-parameter constructor
    }

    Car(String b) {
        this(b, "Black", 2022);
    }

    Car(String b, String c, int y) {
        brand = b;
        color = c;
        year = y;
    }

    void display() {
        System.out.println(brand + " | " + color + " | " + year);
    }
}

public class Main {
    public static void main(String[] args) {
        Car c1 = new Car();
        Car c2 = new Car("Honda");
        Car c3 = new Car("Ford", "Red", 2023);

        c1.display();
        c2.display();
        c3.display();
    }
}
```

📘 **Output:**

```
Toyota | White | 2020
Honda | Black | 2022
Ford | Red | 2023
```

---

## 🧠 Real-World Uses

Constructor overloading is commonly used in:

* **Student or Employee systems** where not all data is available initially.
* **GUI elements**, like buttons or windows that can be created with different settings.
* **Game objects**, like characters that may have default or custom stats.

---

# 🧩 **`this` Keyword in Java**

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧠 Definition

The **`this` keyword** in Java is a **reference variable** that refers to the **current object** of a class.
It helps Java understand which object’s fields or methods you’re referring to — especially when local variables **shadow** (have the same name as) instance variables.

---

## ⚙️ How It Works

When an object is created, Java internally passes the **reference of that object** to non-static methods using the `this` keyword.
So, whenever you use `this`, it points to **the current instance** whose method or constructor is being executed.

---

## 🌟 Why It Is Important

* Avoids **naming conflicts** between instance variables and parameters.
* Helps to **call another constructor** within the same class.
* Passes the **current object** as a parameter to another method or constructor.
* Useful in returning the **current class instance** for method chaining.

---

## 💡 Examples

### ✅ **Example 1: Resolving Variable Shadowing**

```java
class Student {
    String name;
    int age;

    Student(String name, int age) {
        this.name = name; // 'this' refers to the instance variable
        this.age = age;
    }

    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student("Khiel", 17);
        s1.display();
    }
}
```

**🧩 Output:**

```
Name: Khiel, Age: 17
```

---

### ✅ **Example 2: Calling Another Constructor (Constructor Chaining)**

```java
class Box {
    int width, height;

    Box() {
        this(10, 20); // Calls another constructor
    }

    Box(int width, int height) {
        this.width = width;
        this.height = height;
    }

    void display() {
        System.out.println("Box size: " + width + " x " + height);
    }
}

public class Main {
    public static void main(String[] args) {
        Box b = new Box();
        b.display();
    }
}
```

**🧩 Output:**

```
Box size: 10 x 20
```

---

### ✅ **Example 3: Returning the Current Object**

```java
class Calculator {
    int result;

    Calculator add(int num) {
        result += num;
        return this; // Returns current object
    }

    Calculator multiply(int num) {
        result *= num;
        return this;
    }

    void showResult() {
        System.out.println("Result: " + result);
    }
}

public class Main {
    public static void main(String[] args) {
        new Calculator().add(5).multiply(3).showResult(); // Method chaining
    }
}
```

**🧩 Output:**

```
Result: 15
```

---

## 🧭 Where It Is Commonly Used

* In **constructors** to distinguish between local and instance variables.
* In **method chaining**, common in builder patterns or fluent APIs.
* To **pass the current object** as a parameter to another class or method.
* In **inner classes**, when referencing the outer class object (`OuterClass.this`).

### 🧩 Instance vs. Class Variables

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

#### 🧠 Definition

In Java, **variables in a class** can be of two main types:

1. **Instance variables** — belong to an **object (instance)** of a class.
2. **Class variables (static variables)** — belong to the **class itself**, not to any specific object.

---

#### ⚙️ How They Work

* **Instance Variables**

  * Declared **without the `static` keyword** inside a class.
  * Every **object gets its own copy** of these variables.
  * Changing the value in one object doesn’t affect others.
  * Created when the object is created and destroyed when the object is destroyed.

* **Class Variables**

  * Declared **with the `static` keyword** inside a class.
  * There is **only one copy** shared by **all objects** of that class.
  * Changes made by one object are **reflected across all** instances.
  * Created once when the class is loaded into memory and destroyed when the program ends.

---

#### 💡 Why It’s Important

Understanding the difference helps you:

* Manage memory efficiently.
* Decide whether data should be **unique per object** or **shared by all objects**.
* Design better object-oriented programs with **proper encapsulation**.

---

#### 🧮 Examples

**Example 1: Instance Variable**

```java
class Student {
    String name;  // instance variable
    int age;      // instance variable
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();
        Student s2 = new Student();

        s1.name = "Khiel";
        s2.name = "Alex";

        System.out.println(s1.name); // Khiel
        System.out.println(s2.name); // Alex
    }
}
```

👉 Each student object has its own copy of `name`.

---

**Example 2: Class Variable**

```java
class Student {
    static String school = "PHS";  // class variable
}

public class Main {
    public static void main(String[] args) {
        System.out.println(Student.school); // Access via class name

        Student s1 = new Student();
        Student s2 = new Student();
        s1.school = "SHS";

        System.out.println(s2.school); // SHS (shared value)
    }
}
```

👉 Changing `school` affects all instances because it’s shared.

---

**Example 3: Both Used Together**

```java
class Student {
    String name;           // instance variable
    static String school;  // class variable
}

public class Main {
    public static void main(String[] args) {
        Student.school = "PHS"; // Shared among all

        Student s1 = new Student();
        s1.name = "Khiel";

        Student s2 = new Student();
        s2.name = "Alex";

        System.out.println(s1.name + " from " + Student.school);
        System.out.println(s2.name + " from " + Student.school);
    }
}
```

---

#### 🏫 Common Use in Real Programs

* **Instance variables:** for storing unique data per object (e.g., student names, bank account balances).
* **Class variables:** for storing shared data across all objects (e.g., school name, tax rate, company policy).

---

# 🧱 Encapsulation (Getters and Setters)

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧩 Definition

**Encapsulation** is one of the four main principles of Object-Oriented Programming (OOP).
It means **hiding the internal details** (data or variables) of a class and **controlling access** to them through **methods** (usually getters and setters).

This helps protect data from being directly modified by other classes and makes the code easier to maintain and debug.

In Java, encapsulation is done by:

1. Making instance variables **private**
2. Providing **public getter and setter methods** to read and modify the data safely.

---

## ⚙️ How It Works

When variables are private, they **cannot be accessed directly** from outside the class.
To access them, we use **getter methods** (to get the value) and **setter methods** (to set or change the value).

* **Getter Method:** Returns the value of a private variable.

  ```java
  public String getName() {
      return name;
  }
  ```

* **Setter Method:** Updates the value of a private variable, often with validation.

  ```java
  public void setName(String newName) {
      name = newName;
  }
  ```

This ensures that the variable is **only changed in controlled ways**, preventing invalid data.

---

## 💡 Why It’s Important

Encapsulation:

* **Protects data** from unauthorized access or changes.
* **Increases flexibility** — you can change internal implementation without affecting other parts of the program.
* **Improves maintainability** and readability.
* **Supports data validation** inside setters (e.g., not allowing negative age).

---

## 🧠 Example 1 — Basic Getters and Setters

```java
public class Student {
    private String name;
    private int age;

    // Getter for name
    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter for age
    public int getAge() {
        return age;
    }

    // Setter for age with validation
    public void setAge(int age) {
        if (age > 0) {
            this.age = age;
        } else {
            System.out.println("Invalid age!");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Student s = new Student();
        s.setName("Khiel");
        s.setAge(17);

        System.out.println("Name: " + s.getName());
        System.out.println("Age: " + s.getAge());
    }
}
```

---

## 🧠 Example 2 — Validation in Setters

```java
public class BankAccount {
    private double balance;

    public double getBalance() {
        return balance;
    }

    public void setBalance(double balance) {
        if (balance >= 0) {
            this.balance = balance;
        } else {
            System.out.println("Balance cannot be negative!");
        }
    }
}
```

✅ The setter prevents invalid negative values from being stored.

---

## 🧠 Example 3 — Read-Only and Write-Only Fields

```java
public class Product {
    private String productName;
    private double price;

    // Read-only (no setter)
    public String getProductName() {
        return productName;
    }

    // Write-only (no getter)
    public void setPrice(double price) {
        this.price = price;
    }
}
```

✅ This is useful when you want some data to be only readable or only writable for safety reasons.

---

## 🧭 Where It’s Commonly Used

Encapsulation is widely used in:

* **Data models** (like `Student`, `Employee`, `Product`, `BankAccount`)
* **APIs and frameworks**, to hide implementation details
* **Secure applications**, where direct access to variables must be restricted
* **Large systems**, to make maintenance and updates safer

### 🧬 Inheritance

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

### 🧩 **Definition**

**Inheritance** in Java is a mechanism where one class (called a **subclass** or **child class**) **inherits** the fields and methods of another class (called a **superclass** or **parent class**).
It allows you to create a new class based on an existing class, reusing code and extending or modifying existing behavior.

---

### ⚙️ **How It Works**

* The **`extends`** keyword is used to create a subclass.
  Example:

  ```java
  class Animal {
      void eat() {
          System.out.println("This animal eats food.");
      }
  }

  class Dog extends Animal {
      void bark() {
          System.out.println("The dog barks.");
      }
  }
  ```
* Here, `Dog` inherits the `eat()` method from `Animal`.
* You can add new methods (`bark()`) or override existing ones to change behavior.

---

### 🎯 **Why It’s Important**

* Promotes **code reusability** — you don’t need to rewrite code for similar classes.
* Supports **method overriding**, enabling **polymorphism** (one behavior, many forms).
* Makes programs easier to maintain and extend.

---

### 💡 **Examples**

#### 🧠 Example 1: Basic Inheritance

```java
class Vehicle {
    void start() {
        System.out.println("Vehicle started");
    }
}

class Car extends Vehicle {
    void honk() {
        System.out.println("Car horn sounds");
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car();
        myCar.start();  // Inherited from Vehicle
        myCar.honk();   // Defined in Car
    }
}
```

#### 🧠 Example 2: Method Overriding

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}
```

> The `@Override` annotation shows that the subclass changes the parent’s behavior.

#### 🧠 Example 3: Multilevel Inheritance

```java
class Animal {
    void eat() { System.out.println("Eating..."); }
}

class Mammal extends Animal {
    void walk() { System.out.println("Walking..."); }
}

class Dog extends Mammal {
    void bark() { System.out.println("Barking..."); }
}

public class Test {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat();
        dog.walk();
        dog.bark();
    }
}
```

> `Dog` inherits from both `Animal` and `Mammal` through a chain.

---

### 🌍 **Where It’s Commonly Used**

* **Game development** – where different entities (like `Player`, `Enemy`, `NPC`) share common traits from a base `Character` class.
* **GUI applications** – where new components extend classes like `JFrame` or `JButton`.
* **Enterprise software** – in frameworks (e.g., Spring Boot) that use inheritance for controllers, models, and services.

# 🧱 The **super** Keyword in Java

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🔍 Definition

The **`super`** keyword in Java is a **reference variable** used to refer to the **immediate parent class** of a subclass. It is mainly used to **access parent class variables, methods, or constructors** that are hidden or overridden by the subclass.

---

## ⚙️ How It Works and Why It’s Important

When a class inherits another class, sometimes the subclass defines variables or methods with the **same name** as those in the parent class. The `super` keyword allows access to the **original (parent)** version of that data or method.

### Importance:

* It avoids confusion when subclass members hide parent members.
* It helps in **reusing parent constructors and methods**.
* It improves code readability and maintenance in inheritance-based designs.

---

## 💡 3 Examples

### 🧩 Example 1: Accessing Parent Class Variable

```java
class Animal {
    String name = "Animal";
}

class Dog extends Animal {
    String name = "Dog";

    void display() {
        System.out.println("Child name: " + name);
        System.out.println("Parent name: " + super.name);
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.display();
    }
}
```

**Output:**

```
Child name: Dog
Parent name: Animal
```

---

### 🧩 Example 2: Calling Parent Class Method

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void sound() {
        super.sound(); // Calls parent method
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.sound();
    }
}
```

**Output:**

```
Animal makes a sound
Dog barks
```

---

### 🧩 Example 3: Calling Parent Class Constructor

```java
class Animal {
    Animal() {
        System.out.println("Animal constructor called");
    }
}

class Dog extends Animal {
    Dog() {
        super(); // Calls Animal's constructor
        System.out.println("Dog constructor called");
    }
}

public class Main {
    public static void main(String[] args) {
        new Dog();
    }
}
```

**Output:**

```
Animal constructor called
Dog constructor called
```

---

## 🌍 Where It’s Commonly Used

* In **inheritance hierarchies**, when subclass behavior extends or modifies parent behavior.
* In **constructor chaining**, to ensure that the parent class is initialized first.
* When accessing **hidden members** from the parent class that share names with subclass members.
* Common in **frameworks like JavaFX, Swing, and Android**, where custom classes override parent components.

---

# 🧩 Method Overriding

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧠 Definition

**Method Overriding** happens when a **subclass** provides its **own version of a method** that already exists in its **superclass**.
The method in the child class must have:

* The **same name**,
* The **same return type (or a compatible one)**, and
* The **same parameters** as the method in the parent class.

In Java, method overriding is used to **achieve runtime polymorphism** — meaning the method that gets executed depends on the actual object, not the reference type.

---

## ⚙️ How It Works

When you override a method, the **child class** replaces the behavior of the **parent class method**.
When you call that method using an object of the subclass, **the overridden method in the subclass** will be executed — even if the reference type is of the parent class.

To make it clear to the compiler and improve readability, Java uses the **`@Override`** annotation before the method.

---

## 🌟 Why It Is Important

* Allows **customizing or extending** inherited behavior.
* Supports **runtime polymorphism** (dynamic method dispatch).
* Makes code more **flexible and reusable**.
* Enables **method specialization** in subclasses without changing the parent class code.

---

## 💻 Example 1: Basic Method Overriding

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a = new Dog();
        a.sound();  // Output: Dog barks
    }
}
```

✅ The subclass `Dog` overrides the `sound()` method of the superclass `Animal`.

---

## 💻 Example 2: Using `super` Keyword

You can call the **parent class version** of the overridden method using `super`.

```java
class Parent {
    void show() {
        System.out.println("Parent's show method");
    }
}

class Child extends Parent {
    @Override
    void show() {
        super.show();
        System.out.println("Child's show method");
    }
}

public class Main {
    public static void main(String[] args) {
        Child obj = new Child();
        obj.show();
    }
}
```

🧩 Output:

```
Parent's show method
Child's show method
```

---

## 💻 Example 3: Runtime Polymorphism

```java
class Shape {
    void draw() {
        System.out.println("Drawing a shape");
    }
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a circle");
    }
}

class Square extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a square");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape s1 = new Circle();
        Shape s2 = new Square();

        s1.draw();  // Output: Drawing a circle
        s2.draw();  // Output: Drawing a square
    }
}
```

🎨 Here, the program decides at runtime which version of `draw()` to run — this is **runtime polymorphism**.

---

## 🧰 Common Real-World Uses

* In **GUI frameworks**, methods like `paint()` or `onClick()` are overridden to customize component behavior.
* In **web frameworks**, methods such as `doGet()` and `doPost()` in servlets are overridden to handle HTTP requests.
* In **game programming**, classes like `Player`, `Enemy`, and `NPC` may override methods such as `attack()` or `move()` to define their unique behaviors.

---

# 🧩 Polymorphism

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🔹 Definition

**Polymorphism** in Java is the ability of an object to take on many forms.
It allows one interface (or method) to represent different underlying data types or behaviors.
In simple terms, it means **"one name, many actions"** — the same method name can perform different tasks depending on which object it acts upon.

There are two main types of polymorphism in Java:

1. **Compile-time Polymorphism (Static Binding)** → Achieved using **method overloading**.
2. **Runtime Polymorphism (Dynamic Binding)** → Achieved using **method overriding** and **inheritance**.

---

## 🔹 How It Works

Polymorphism works through **inheritance** and **method overriding**:

* A **parent class reference** can point to a **child class object**.
* The method that gets called depends on the **actual object type** (not the reference type) during **runtime**.

Example concept:

```java
Animal a = new Dog(); // Parent reference, child object
a.sound(); // Calls Dog's version of sound() method
```

Here, `sound()` behaves differently depending on the object (Dog, Cat, etc.) — this is **runtime polymorphism**.

---

## 🔹 Why It’s Important

✅ Promotes **code reusability**
✅ Makes code **flexible and maintainable**
✅ Allows **extensibility** — new classes can easily fit into existing systems
✅ Enables **dynamic method invocation** (the actual method that runs is decided during runtime)

---

## 🔹 Example 1 – Compile-time Polymorphism (Method Overloading)

```java
class MathOperation {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        MathOperation m = new MathOperation();
        System.out.println(m.add(3, 5));      // Calls int version
        System.out.println(m.add(2.5, 4.3));  // Calls double version
    }
}
```

---

## 🔹 Example 2 – Runtime Polymorphism (Method Overriding)

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    void sound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a1 = new Dog();
        Animal a2 = new Cat();
        a1.sound(); // Dog barks
        a2.sound(); // Cat meows
    }
}
```

---

## 🔹 Example 3 – Polymorphism in Real Programs

```java
class Payment {
    void pay() {
        System.out.println("General payment");
    }
}

class CreditCardPayment extends Payment {
    void pay() {
        System.out.println("Payment made using Credit Card");
    }
}

class PayPalPayment extends Payment {
    void pay() {
        System.out.println("Payment made using PayPal");
    }
}

public class Main {
    public static void main(String[] args) {
        Payment p1 = new CreditCardPayment();
        Payment p2 = new PayPalPayment();
        p1.pay(); // Credit Card
        p2.pay(); // PayPal
    }
}
```

---

## 🔹 Where It’s Commonly Used

* In **Object-Oriented Programming** (OOP) frameworks.
* In **GUI frameworks** like Swing or JavaFX (e.g., handling events).
* In **Collections Framework** (e.g., `List`, `ArrayList`, `LinkedList` — all used via a common interface).
* In **real-world applications** such as payment systems, where one interface supports multiple payment types.

---

# 🧩 Abstract Classes

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧠 Definition

An **abstract class** in Java is a class that **cannot be instantiated** directly — meaning, you cannot create an object of it using the `new` keyword.
It is declared using the keyword `abstract`, and it is mainly used as a **base or blueprint** for other classes.

An abstract class can have:

* **Abstract methods** (methods without a body).
* **Concrete methods** (methods with a body).
* **Instance variables**, **constructors**, and even **static methods**.

It’s often used when you want to **enforce a certain structure** or behavior for all subclasses but still allow them to **implement specific details**.

---

## ⚙️ How It Works

When a class contains one or more **abstract methods**, it must be declared as **abstract**.
A **subclass** that extends an abstract class must **provide implementations** for all its abstract methods, or else it must also be declared abstract.

**Example structure:**

```java
abstract class Animal {
    abstract void makeSound(); // abstract method (no body)

    void sleep() { // concrete method
        System.out.println("Sleeping...");
    }
}
```

Subclasses inherit from this and provide details:

```java
class Dog extends Animal {
    void makeSound() {
        System.out.println("Woof! Woof!");
    }
}
```

When you run:

```java
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound();
        dog.sleep();
    }
}
```

**Output:**

```
Woof! Woof!
Sleeping...
```

---

## 💡 Why It’s Important

Abstract classes help in:
✅ **Code Reusability** — Common code stays in the abstract class.
✅ **Consistency** — Ensures all subclasses follow the same method structure.
✅ **Flexibility** — Allows different subclasses to define their own behavior for the same abstract method.

---

## 🧩 3 Example Uses

### 🐾 Example 1: Abstract Method Implementation

```java
abstract class Vehicle {
    abstract void startEngine();
}

class Car extends Vehicle {
    void startEngine() {
        System.out.println("Car engine started!");
    }
}
```

### 🧰 Example 2: Shared Functionality

```java
abstract class Employee {
    void workHours() {
        System.out.println("Works 8 hours a day.");
    }
    abstract void jobRole();
}

class Programmer extends Employee {
    void jobRole() {
        System.out.println("Writes code.");
    }
}
```

### 🎮 Example 3: Game Framework

```java
abstract class Game {
    abstract void start();
    abstract void end();

    void play() {
        start();
        System.out.println("Game is running...");
        end();
    }
}

class Chess extends Game {
    void start() { System.out.println("Chess started!"); }
    void end() { System.out.println("Chess ended!"); }
}
```

---

## 🌍 Where It’s Commonly Used

Abstract classes are widely used in:

* **Frameworks** (e.g., JavaFX, Swing, Android SDK)
* **Template Design Pattern** — to define algorithm steps in a base class
* **Game and Simulation Systems** — where different entities share behavior but act differently
* **Enterprise applications** — base classes like `HttpServlet` in Java EE are abstract.

---

# 🧩 Interfaces in Java

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 📘 Definition

An **interface** in Java is a special type that defines a **set of abstract methods** (methods without a body) that a class must implement.
It acts like a **contract** — if a class implements an interface, it agrees to perform the behaviors declared in it.

```java
interface Animal {
    void makeSound(); // abstract method
}
```

A class that implements this interface must provide an implementation for `makeSound()`.

```java
class Dog implements Animal {
    public void makeSound() {
        System.out.println("Woof!");
    }
}
```

---

## ⚙️ How It Works

* Interfaces **cannot contain implementation** (except for `default` and `static` methods introduced in Java 8).
* A class **uses the `implements` keyword** to use an interface.
* A single class can **implement multiple interfaces**, allowing **multiple inheritance of behavior**.
* Interfaces can also include **constants (public static final variables)**.

---

## 🌟 Why It’s Important

* Promotes **abstraction** — you define *what* should be done, not *how*.
* Enables **polymorphism** — different classes can be treated as the same type through an interface.
* Encourages **loose coupling** — code depends on abstract types rather than concrete implementations.

---

## 💻 Examples

### 🧠 Example 1: Basic Interface Implementation

```java
interface Animal {
    void eat();
}

class Cat implements Animal {
    public void eat() {
        System.out.println("Cat eats fish.");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myCat = new Cat();
        myCat.eat();
    }
}
```

---

### 🧠 Example 2: Multiple Interfaces

```java
interface Flyable {
    void fly();
}

interface Swimmable {
    void swim();
}

class Duck implements Flyable, Swimmable {
    public void fly() { System.out.println("Duck flies!"); }
    public void swim() { System.out.println("Duck swims!"); }
}
```

---

### 🧠 Example 3: Default Method in Interface

```java
interface Vehicle {
    default void start() {
        System.out.println("Vehicle is starting...");
    }
}

class Car implements Vehicle {}

public class Main {
    public static void main(String[] args) {
        Car c = new Car();
        c.start();  // Output: Vehicle is starting...
    }
}
```

---

## 🌍 Where It’s Commonly Used

* In **large software systems** to define APIs or contracts (e.g., `List`, `Set`, `Map` in Java Collections Framework).
* To support **dependency injection** and **unit testing** (programming to interfaces, not implementations).
* In **frameworks and libraries** — interfaces let developers plug in their own custom classes (like `Runnable`, `Comparable`, `Serializable`).

# 🧱 Final Keyword

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🧩 Definition

The **`final` keyword** in Java is a **modifier** used to restrict the user from changing something. It can be applied to **variables, methods, and classes**. When something is declared as `final`, it **cannot be modified, overridden, or extended**, depending on where it is used.

---

## ⚙️ How It Works & Why It’s Important

* **Final Variable**: Once assigned, its value **cannot be changed**. It becomes a constant.
* **Final Method**: A method marked as final **cannot be overridden** by subclasses.
* **Final Class**: A class declared as final **cannot be inherited** (no subclasses can be created).

This keyword is important for ensuring **data security**, **program stability**, and **preventing accidental modification** of critical parts of your code.

---

## 💡 Examples

### Example 1: Final Variable (Constant)

```java
public class Example1 {
    public static void main(String[] args) {
        final int MAX_SCORE = 100;
        System.out.println("Maximum score: " + MAX_SCORE);

        // MAX_SCORE = 90; // ❌ Error: cannot assign a value to final variable
    }
}
```

✅ Used for constants that should not change (e.g., PI value, max limits).

---

### Example 2: Final Method

```java
class Animal {
    final void sound() {
        System.out.println("Animals make sounds");
    }
}

class Dog extends Animal {
    // void sound() { } // ❌ Error: Cannot override the final method from Animal
}
```

✅ Ensures the original method behavior is preserved in all subclasses.

---

### Example 3: Final Class

```java
final class Constants {
    static final double PI = 3.14159;
}

// class MyConstants extends Constants {} // ❌ Error: cannot inherit from final class
```

✅ Prevents inheritance when you want a class to remain unchanged or secure.

---

## 🌍 Where It’s Commonly Used

* Declaring **constants** (e.g., `final static double TAX_RATE = 0.12;`)
* Making **utility or helper classes** non-inheritable (e.g., `java.lang.Math` is final)
* Protecting important **methods** from being overridden
* Used in **immutable classes** (like `String` class) to ensure safety and consistency

---

# ⚙️ Static Keyword (Methods, Variables, Blocks)

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧩 Definition

In Java, the **`static` keyword** means that a **member (variable, method, or block)** belongs to the **class itself** rather than to any specific object (instance) of that class.
This means you can access it **without creating an object** of the class.

---

## ⚙️ How It Works

When you declare something as **`static`**, it is stored in the **method area** of memory (shared by all objects of that class).
Because of this:

* There is **only one copy** of a static member, regardless of how many objects are created.
* Static methods and variables are accessed using the **class name**, not the object name.

---

## 🧱 1. Static Variables (Class Variables)

A **static variable** is shared by all instances of a class.

```java
class Student {
    static String school = "Central High"; // shared by all students
    String name;

    Student(String name) {
        this.name = name;
    }

    void display() {
        System.out.println(name + " studies at " + school);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student("Khiel");
        Student s2 = new Student("Ava");

        s1.display();
        s2.display();
    }
}
```

🧠 **Explanation:**
Even if there are multiple `Student` objects, the `school` variable is **the same for all**, because it’s static.

---

## 🧮 2. Static Methods

A **static method** belongs to the class, not to any specific object.
You can call it **without creating an object**.

```java
class MathUtils {
    static int add(int a, int b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        int result = MathUtils.add(5, 10); // no object needed
        System.out.println("Sum: " + result);
    }
}
```

📘 **Notes:**

* Static methods **can only access static data**.
* They **cannot use `this` or `super`** because they are not tied to an instance.

---

## 🔒 3. Static Blocks

A **static block** is used to **initialize static variables**.
It runs **only once**, when the class is first loaded into memory.

```java
class Config {
    static int maxUsers;

    // static block
    static {
        System.out.println("Initializing configuration...");
        maxUsers = 100;
    }
}

public class Main {
    public static void main(String[] args) {
        System.out.println("Max Users: " + Config.maxUsers);
    }
}
```

🧠 **Explanation:**
Before the `main` method runs, the static block executes automatically, setting up class-level data.

---

## 💡 Real-Life Uses

| Use Case                 | Description                                                                            |
| ------------------------ | -------------------------------------------------------------------------------------- |
| **Utility Classes**      | Classes like `Math` or `Collections` use static methods (`Math.sqrt()`, `Math.pow()`). |
| **Constants**            | Use static variables for fixed values, e.g. `static final double PI = 3.1416;`.        |
| **Shared Counters**      | Keep track of how many objects are created.                                            |
| **Configuration Blocks** | Static blocks can initialize settings or resources when the program starts.            |

---

## 🧭 Summary

| Type            | When It Runs     | Shared Across Objects? | Accessed By          |
| --------------- | ---------------- | ---------------------- | -------------------- |
| Static Variable | When class loads | ✅ Yes                  | `ClassName.variable` |
| Static Method   | When called      | ✅ Yes                  | `ClassName.method()` |
| Static Block    | When class loads | ✅ Yes                  | Runs automatically   |

---

# 🧩 Inner Classes

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🔍 Definition

**Inner classes** are classes declared **inside another class** in Java. They are used to logically group classes that are only used in one place and to **access members (fields and methods) of the outer class**, even if they are private.

In other words, an **inner class** is a **member of an outer class**, similar to how methods and variables are.

There are **four main types** of inner classes:

1. **Non-static inner class (Member Inner Class)**
2. **Static nested class**
3. **Local inner class** (inside a method)
4. **Anonymous inner class**

---

## ⚙️ How It Works

Inner classes are compiled as separate `.class` files (e.g., `Outer$Inner.class`) but have **special access** to the outer class’s private members.

To create an object of a non-static inner class, you must first create an instance of its outer class.

```java
OuterClass outer = new OuterClass();
OuterClass.InnerClass inner = outer.new InnerClass();
```

Static nested classes, however, **do not need** an instance of the outer class:

```java
OuterClass.StaticNestedClass nested = new OuterClass.StaticNestedClass();
```

---

## 🌟 Why It’s Important

* **Encapsulation:** Keeps helper classes hidden from other classes.
* **Code organization:** Groups related classes together.
* **Improved readability:** Keeps code more structured and meaningful.
* **Access convenience:** Inner classes can directly access private data of the outer class.

---

## 💡 Examples

### 🧱 Example 1 — Member Inner Class

```java
class Outer {
    private String message = "Hello from Outer!";

    class Inner {
        void display() {
            System.out.println(message); // can access private outer data
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

### ⚙️ Example 2 — Static Nested Class

```java
class Outer {
    static class Nested {
        void show() {
            System.out.println("Static nested class example");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Outer.Nested obj = new Outer.Nested();
        obj.show();
    }
}
```

### 🧩 Example 3 — Anonymous Inner Class

```java
abstract class Greeting {
    abstract void sayHello();
}

public class Main {
    public static void main(String[] args) {
        Greeting g = new Greeting() {
            void sayHello() {
                System.out.println("Hello from Anonymous Inner Class!");
            }
        };
        g.sayHello();
    }
}
```

---

## 🧠 Common Uses

* **GUI programming (Swing/JavaFX)** — often used in event listeners.
* **Encapsulating helper logic** — when a small class supports its outer class.
* **Threading or callbacks** — anonymous inner classes used for Runnable or listeners.

**Example (GUI event listener):**

```java
button.addActionListener(new ActionListener() {
    public void actionPerformed(ActionEvent e) {
        System.out.println("Button clicked!");
    }
});
```

---

# 🧩 Anonymous Classes

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧠 Definition

An **anonymous class** in Java is a **local inner class without a name**.
It is used to **create a one-time object** of a class with certain behavior — usually for **short, quick customizations** such as implementing an interface or extending a class.

---

## ⚙️ How It Works

* Anonymous classes are **defined and instantiated at the same time**.
* They are commonly used when you need a **small class implementation** for a specific task — for example, when implementing an interface with only one method.
* Since they don’t have names, they cannot be reused elsewhere in the code.
* Syntax:

  ```java
  new SuperType() {
      // class body
  };
  ```

  Here, `SuperType` can be an **interface** or a **class**.

---

## 🌟 Why It’s Important

Anonymous classes:

* **Reduce boilerplate code** (no need to write a full class definition).
* Make code **more readable** when the class is used only once.
* Are useful for **event handling**, **callbacks**, and **thread creation**.

---

## 💡 Examples

### 🧩 Example 1 — Implementing an Interface

```java
interface Greeting {
    void sayHello();
}

public class Main {
    public static void main(String[] args) {
        Greeting greet = new Greeting() {
            public void sayHello() {
                System.out.println("Hello, world!");
            }
        };
        greet.sayHello();
    }
}
```

✅ Here, the anonymous class implements the `Greeting` interface on the spot.

---

### 🧩 Example 2 — Extending a Class

```java
class Animal {
    void makeSound() {
        System.out.println("Some sound...");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Animal() {
            void makeSound() {
                System.out.println("Bark!");
            }
        };
        dog.makeSound();
    }
}
```

✅ This anonymous class overrides the `makeSound()` method.

---

### 🧩 Example 3 — Event Listener (Common in GUI)

```java
import javax.swing.*;

public class Example {
    public static void main(String[] args) {
        JButton button = new JButton("Click Me!");
        button.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent e) {
                System.out.println("Button clicked!");
            }
        });
        JFrame frame = new JFrame();
        frame.add(button);
        frame.pack();
        frame.setVisible(true);
    }
}
```

✅ The anonymous class is used as an event listener to handle the button click.

---

## 🧭 Common Uses in Real Life

* **Event handling** in GUI programs (Swing, JavaFX, Android).
* **Custom thread behavior** (`new Thread() { public void run() { ... } }`).
* **Passing short behavior implementations** to methods.

---

# 🧱 Enumerations (enum)

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧩 Definition

**Enumeration (enum)** in Java is a special data type that represents a group of **named constants** (fixed values).
For example, the days of the week or the directions (NORTH, SOUTH, EAST, WEST).
Enums are used when you have a fixed set of possible values that do not change during the program’s execution.

Example:

```java
enum Direction {
    NORTH, SOUTH, EAST, WEST
}
```

## ⚙️ How It Works

* Each constant inside an `enum` is **public**, **static**, and **final** by default.
* You can use enums just like objects — they can have **fields, methods, and constructors**.
* You access them using **enum type name** followed by a dot (`.`).

Example:

```java
Direction dir = Direction.NORTH;
System.out.println(dir);  // Output: NORTH
```

Enums help make code **more readable**, **type-safe**, and **error-free** compared to using plain integer constants.

## 🎯 Importance

* Prevents invalid values (only predefined constants allowed)
* Improves readability and maintainability
* Can be used in **switch statements**
* Provides built-in methods like `values()` and `valueOf()`

---

## 💻 Example 1: Basic Enum

```java
enum Day {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
}

public class Example1 {
    public static void main(String[] args) {
        Day today = Day.FRIDAY;
        System.out.println("Today is " + today);
    }
}
```

🧠 *Output:* `Today is FRIDAY`

---

## 💻 Example 2: Enum with switch statement

```java
enum TrafficLight {
    RED, YELLOW, GREEN
}

public class Example2 {
    public static void main(String[] args) {
        TrafficLight signal = TrafficLight.RED;

        switch (signal) {
            case RED -> System.out.println("Stop!");
            case YELLOW -> System.out.println("Get Ready!");
            case GREEN -> System.out.println("Go!");
        }
    }
}
```

🧠 *Output:* `Stop!`

---

## 💻 Example 3: Enum with fields and methods

```java
enum Planet {
    MERCURY(3.303e+23, 2.4397e6),
    EARTH(5.976e+24, 6.37814e6),
    MARS(6.421e+23, 3.3972e6);

    private final double mass;   // in kilograms
    private final double radius; // in meters

    Planet(double mass, double radius) {
        this.mass = mass;
        this.radius = radius;
    }

    double surfaceGravity() {
        double G = 6.67300E-11;
        return G * mass / (radius * radius);
    }
}

public class Example3 {
    public static void main(String[] args) {
        for (Planet p : Planet.values()) {
            System.out.printf("%s gravity: %.2f m/s²%n", p, p.surfaceGravity());
        }
    }
}
```

🧠 *Output:* Gravity values for each planet.

---

## 🌍 Common Uses in Real Life and Programming

* Representing **days of the week**, **months**, or **directions**
* Handling **states** (e.g., traffic lights, user roles)
* Working with **menu options** or **commands**
* Replacing **integer constants** for more meaningful, readable code

# 🧩 Packages (Creating and Using)

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🧠 Definition

A **package** in Java is a way to **group related classes, interfaces, and sub-packages** together.
It helps **organize code**, **avoid naming conflicts**, and **control access** between classes.

Think of it like folders on your computer — they keep your files organized.

---

## ⚙️ How It Works

When you create a Java class, you can declare a package at the very top of your file using:

```java
package mypackage;
```

This tells Java that the class belongs to the `mypackage` group.
To use a class from another package, you can use the `import` statement:

```java
import mypackage.MyClass;
```

If no package is declared, the class automatically belongs to the **default package**.

---

## 🎯 Why It’s Important

1. **Organizes Code** – keeps related classes together.
2. **Avoids Name Conflicts** – different packages can have classes with the same name.
3. **Controls Access** – package-private members can only be accessed within the same package.
4. **Easier Maintenance** – improves readability and structure in large programs.

---

## 💻 Example 1 — Creating a Package

**File:** `mypackage/Student.java`

```java
package mypackage;

public class Student {
    public void display() {
        System.out.println("This is the Student class inside mypackage.");
    }
}
```

---

## 💻 Example 2 — Using a Package

**File:** `Main.java`

```java
import mypackage.Student;

public class Main {
    public static void main(String[] args) {
        Student s = new Student();
        s.display();
    }
}
```

**Output:**

```
This is the Student class inside mypackage.
```

---

## 💻 Example 3 — Using Multiple Packages

**File:** `school/Teacher.java`

```java
package school;

public class Teacher {
    public void teach() {
        System.out.println("Teaching from the Teacher class in school package.");
    }
}
```

**File:** `app/Main.java`

```java
import mypackage.Student;
import school.Teacher;

public class Main {
    public static void main(String[] args) {
        Student s = new Student();
        s.display();

        Teacher t = new Teacher();
        t.teach();
    }
}
```

---

## 🌍 Where Packages Are Commonly Used

* **Java API** itself is organized into packages:

  * `java.util` → collections (e.g., `ArrayList`, `HashMap`)
  * `java.io` → input/output
  * `java.net` → networking
  * `java.sql` → database operations
* **Real Projects** use custom packages to group features (e.g., `com.school.student`, `com.school.teacher`).

# 🧩 Access Modifiers (public, private, protected, default)

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🔍 Definition

**Access Modifiers** in Java are **keywords** that define the **visibility or accessibility** of classes, methods, and variables to other parts of a program.
They help enforce **encapsulation**, one of the main principles of Object-Oriented Programming (OOP).

There are **four main access modifiers** in Java:

1. `public`
2. `private`
3. `protected`
4. *default* (no modifier specified)

---

## ⚙️ How It Works

Each modifier sets a **different level of access** depending on where the code is being accessed from (same class, package, or subclass).

| Modifier    | Same Class | Same Package | Subclass (different package) | Other Packages      |
| ----------- | ---------- | ------------ | ---------------------------- | ------------------- |
| `public`    | ✅          | ✅            | ✅                            | ✅                   |
| `protected` | ✅          | ✅            | ✅                            | ❌ (unless subclass) |
| *(default)* | ✅          | ✅            | ❌                            | ❌                   |
| `private`   | ✅          | ❌            | ❌                            | ❌                   |

---

## 💡 Why It’s Important

Access modifiers:

* Protect the **data integrity** of a class by controlling how its members are accessed.
* Prevent **unauthorized modification** of data.
* Help maintain **clean code structure** and **modular design**.

---

## 🧠 Examples

### 🧩 Example 1 – `public`

```java
public class Student {
    public String name;

    public void displayName() {
        System.out.println("Student Name: " + name);
    }
}
```

✅ Accessible from **any class** in any package.

---

### 🧩 Example 2 – `private`

```java
public class Student {
    private int age;

    private void displayAge() {
        System.out.println("Age: " + age);
    }
}
```

❌ Can only be accessed **within the same class**.
Trying to access it from outside will cause a **compile-time error**.

---

### 🧩 Example 3 – `protected`

```java
package school;

public class Student {
    protected String grade;
}
```

```java
package university;
import school.Student;

public class Graduate extends Student {
    void showGrade() {
        System.out.println("Grade: " + grade); // ✅ Accessible through inheritance
    }
}
```

✅ Accessible in **subclasses**, even in **different packages**.

---

### 🧩 Example 4 – *Default (Package-Private)*

```java
class Student {
    String course;  // no modifier

    void showCourse() {
        System.out.println("Course: " + course);
    }
}
```

✅ Accessible **only within the same package**.
❌ Not visible from outside the package.

---

## 🌍 Common Usage

* `public` → For classes or methods meant to be used **anywhere**.
* `private` → For **internal data** that must be hidden from other classes.
* `protected` → For **inheritance**, when subclasses need access.
* *default* → For **package-level** collaboration among related classes.

# 🧱 Wrapper Classes (Integer, Double, etc.)

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧩 Definition

In Java, **wrapper classes** are object representations of primitive data types.
They are found in the `java.lang` package and “wrap” primitive values (like `int`, `double`, `char`, etc.) into **objects** so they can be used where objects are required—such as in collections (`ArrayList`, `HashMap`, etc.).

| Primitive Type | Wrapper Class |
| -------------- | ------------- |
| `byte`         | `Byte`        |
| `short`        | `Short`       |
| `int`          | `Integer`     |
| `long`         | `Long`        |
| `float`        | `Float`       |
| `double`       | `Double`      |
| `char`         | `Character`   |
| `boolean`      | `Boolean`     |

---

## ⚙️ How It Works

Primitive types (like `int`) are **not objects**, meaning they cannot call methods or be stored directly in Java collections that work only with objects.
Wrapper classes **encapsulate** (wrap) these values in an object, providing methods for manipulation and conversion.

### 🪄 Autoboxing and Unboxing

Java automatically converts between primitives and wrapper objects:

* **Autoboxing:** Converting a primitive into its wrapper object.
  → Example: `int` → `Integer`
* **Unboxing:** Converting a wrapper object back into a primitive.
  → Example: `Integer` → `int`

```java
int num = 10;
Integer boxedNum = num;       // Autoboxing
int unboxedNum = boxedNum;    // Unboxing
```

---

## 🌟 Why It Is Important

1. **Object Use:** Wrapper classes allow primitives to be used in **collections** (e.g., `ArrayList<Integer>`).
2. **Utility Methods:** They provide helpful **methods** for parsing and converting data types.
3. **Nullability:** Wrapper objects can be **null**, while primitives cannot.
4. **Generic Support:** Generics in Java only work with objects, not primitives.

---

## 🧮 Examples

### 🧩 Example 1 — Autoboxing and Unboxing

```java
public class Example1 {
    public static void main(String[] args) {
        int a = 5;
        Integer b = a; // Autoboxing
        int c = b;     // Unboxing
        System.out.println("Value of b: " + b);
        System.out.println("Value of c: " + c);
    }
}
```

---

### 🧩 Example 2 — Using Wrapper Classes in Collections

```java
import java.util.ArrayList;

public class Example2 {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(10);  // Autoboxing
        numbers.add(20);
        numbers.add(30);
        
        for (Integer num : numbers) {
            System.out.println(num);
        }
    }
}
```

✅ You cannot use `ArrayList<int>` — it must be `ArrayList<Integer>`.

---

### 🧩 Example 3 — Converting Strings to Numbers

```java
public class Example3 {
    public static void main(String[] args) {
        String value = "123";
        int number = Integer.parseInt(value);  // String → int
        double price = Double.valueOf("99.99"); // String → Double object

        System.out.println("Integer value: " + number);
        System.out.println("Double value: " + price);
    }
}
```

---

## 💼 Common Use Cases

* **Collections:** Like `ArrayList<Integer>` or `HashMap<Character, Boolean>`.
* **Data Conversion:** Converting between strings and numbers.
* **Generics:** Wrapper types allow primitives to work with generic methods or classes.
* **Null Handling:** In databases or optional values, wrapper objects can represent “no value” as `null`.

# 🧩 Autoboxing and Unboxing

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🔍 Definition

**Autoboxing** is the automatic conversion that the **Java compiler** makes between the **primitive data types** (`int`, `double`, `char`, etc.) and their corresponding **wrapper classes** (`Integer`, `Double`, `Character`, etc.).

**Unboxing**, on the other hand, is the reverse process — the automatic conversion of **wrapper class objects** back into their **primitive values**.

---

## ⚙️ How It Works and Why It’s Important

Before Java 5, developers had to manually convert between primitives and objects using methods like `Integer.valueOf()` and `intValue()`.

With **autoboxing and unboxing**, the compiler automatically performs these conversions whenever necessary — for example, when you assign a primitive to a wrapper variable or when you use collections that can only store objects (like `ArrayList<Integer>`).

✅ **Why it’s important:**

* Makes code **cleaner** and **easier to read**.
* Reduces the need for **manual conversions**.
* Enables the use of primitives in **Collections Framework** (which works only with objects).

---

## 💡 Examples

### Example 1: Autoboxing

```java
int num = 10;
Integer obj = num;  // Autoboxing: primitive int → Integer object
System.out.println(obj);
```

### Example 2: Unboxing

```java
Integer obj = 25;
int num = obj;  // Unboxing: Integer object → primitive int
System.out.println(num + 5);  // Output: 30
```

### Example 3: Autoboxing with Collections

```java
import java.util.ArrayList;

public class Example {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();

        // Autoboxing: int values automatically converted to Integer objects
        numbers.add(10);
        numbers.add(20);
        numbers.add(30);

        // Unboxing: Integer objects converted back to int
        int sum = 0;
        for (int n : numbers) {
            sum += n;
        }

        System.out.println("Sum = " + sum);
    }
}
```

---

## 🧠 Where It’s Commonly Used

* **Collections Framework** (`ArrayList`, `HashMap`, etc.) because these can only store objects.
* **Mathematical operations** where primitives are retrieved from wrappers.
* **APIs and libraries** that require objects instead of primitives.

# 🧱 ArrayList

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🧩 Definition

In Java, an **ArrayList** is a **resizable array** that is part of the **Java Collections Framework**. Unlike a regular array, its size **can grow or shrink dynamically** as elements are added or removed. It is found in the package `java.util` and is implemented using **arrays internally**.

```java
import java.util.ArrayList;
```

---

## ⚙️ How It Works

* An `ArrayList` starts with a **default capacity** (usually 10).
* When more elements are added beyond this capacity, it **automatically creates a new, larger array** and **copies the old elements** into it.
* It allows **random access** (just like arrays) using indexes, but adding or removing elements in the middle can be slower because it needs to shift elements.

### Basic Syntax:

```java
ArrayList<Type> listName = new ArrayList<>();
```

---

## 🌟 Why It’s Important

* Provides **dynamic resizing** — no need to declare a fixed size like arrays.
* Offers built-in methods for **adding**, **removing**, **searching**, and **iterating** over elements.
* Commonly used for **data storage**, **lists of records**, and **temporary collections** in applications.

---

## 💡 Examples

### 🧠 Example 1: Creating and Adding Elements

```java
import java.util.ArrayList;

public class Example1 {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Mango");

        System.out.println(fruits);
    }
}
```

📤 Output:

```
[Apple, Banana, Mango]
```

---

### 🧠 Example 2: Accessing and Removing Elements

```java
import java.util.ArrayList;

public class Example2 {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(10);
        numbers.add(20);
        numbers.add(30);

        System.out.println(numbers.get(1)); // Access element
        numbers.remove(0); // Remove first element
        System.out.println(numbers);
    }
}
```

📤 Output:

```
20
[20, 30]
```

---

### 🧠 Example 3: Iterating through an ArrayList

```java
import java.util.ArrayList;

public class Example3 {
    public static void main(String[] args) {
        ArrayList<String> names = new ArrayList<>();
        names.add("Khiel");
        names.add("Mia");
        names.add("Renz");

        for (String name : names) {
            System.out.println(name);
        }
    }
}
```

📤 Output:

```
Khiel
Mia
Renz
```

---

## 🏗️ Where It’s Commonly Used

* Managing **lists of items** (students, products, etc.)
* **Dynamic data storage** in apps like to-do lists or shopping carts.
* Storing and modifying **objects** that may change in number during program execution.

# LinkedList in Java

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🧩 Definition

A **LinkedList** in Java is a data structure from the **java.util** package that stores elements in a **sequential** manner, where each element (called a *node*) contains both **data** and a **reference (link)** to the next and previous elements in the list.

Unlike an **ArrayList**, which uses a dynamic array, a LinkedList uses **nodes** connected by **pointers**, allowing easy insertion and deletion of elements.

---

## ⚙️ How It Works

* Each node in a LinkedList contains:

  1. **Data** – the value stored in the node.
  2. **Next** – a reference to the next node.
  3. **Previous** – a reference to the previous node (in a doubly-linked list).

Java’s `LinkedList` class implements both the **List** and **Deque** interfaces, meaning it can be used as a **list**, **queue**, or **stack**.

---

## 🎯 Why It’s Important

* Efficient **insertion** and **deletion** (especially at the beginning or middle).
* Ideal when you frequently **add or remove** elements rather than just access them.
* Can function as multiple data structures (list, queue, deque, stack).

---

## 💻 Example 1: Basic LinkedList Usage

```java
import java.util.LinkedList;

public class Example1 {
    public static void main(String[] args) {
        LinkedList<String> fruits = new LinkedList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Mango");

        System.out.println(fruits);  // Output: [Apple, Banana, Mango]
    }
}
```

---

## 💻 Example 2: Adding and Removing Elements

```java
import java.util.LinkedList;

public class Example2 {
    public static void main(String[] args) {
        LinkedList<Integer> numbers = new LinkedList<>();

        numbers.add(10);
        numbers.addFirst(5);  // Add at the beginning
        numbers.addLast(15);  // Add at the end

        System.out.println(numbers);  // [5, 10, 15]

        numbers.removeFirst();
        numbers.removeLast();

        System.out.println(numbers);  // [10]
    }
}
```

---

## 💻 Example 3: Using LinkedList as a Queue

```java
import java.util.LinkedList;
import java.util.Queue;

public class Example3 {
    public static void main(String[] args) {
        Queue<String> tasks = new LinkedList<>();

        tasks.add("Task 1");
        tasks.add("Task 2");
        tasks.add("Task 3");

        System.out.println(tasks.poll()); // Removes and returns first element → Task 1
        System.out.println(tasks);        // [Task 2, Task 3]
    }
}
```

---

## 🧠 Common Uses in Real Life or Programming

* **Implementing Queues or Stacks** (e.g., job scheduling, printer queues)
* **Undo/Redo functionality** in applications
* **Navigation systems** (back and forward history in browsers)
* **Graph or Tree traversal** using linked node structures

# 🗂️ HashMap in Java

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧩 Definition

A **HashMap** in Java is part of the **`java.util`** package and is used to store data in **key-value pairs**. Each key is **unique**, and it maps to exactly one value. If a duplicate key is inserted, the old value is replaced.

It is based on **hashing**, a technique that allows fast access to elements — on average, **O(1)** time for insertion, deletion, and lookup.

---

## ⚙️ How It Works

A HashMap uses a **hash function** to compute an **index (bucket)** where each key-value pair is stored internally.

1. When you add a key, Java computes its **hash code**.
2. The hash code determines where to store it in memory.
3. When you search for a key, the hash code is used again to find its value quickly.

If two keys have the same hash code (called a **collision**), HashMap stores them in a **linked list** or **balanced tree** (in Java 8+ for performance).

---

## 💡 Why It’s Important

HashMap is one of the most commonly used data structures in Java because it provides:

* **Fast data access** (average O(1) performance)
* **Flexible storage** of objects
* **Efficient key-based searching**
* **Useful for caching, counting, and lookups**

---

## 🧠 3 Examples

### Example 1: Basic Usage

```java
import java.util.HashMap;

public class Example1 {
    public static void main(String[] args) {
        HashMap<String, Integer> ages = new HashMap<>();

        ages.put("Khiel", 17);
        ages.put("Anna", 18);
        ages.put("Mark", 19);

        System.out.println(ages.get("Anna")); // Output: 18
    }
}
```

### Example 2: Checking Keys and Values

```java
HashMap<String, String> capitals = new HashMap<>();
capitals.put("Philippines", "Manila");
capitals.put("Japan", "Tokyo");

if (capitals.containsKey("Japan")) {
    System.out.println("Capital: " + capitals.get("Japan"));
}
```

### Example 3: Iterating Through a HashMap

```java
HashMap<String, Double> prices = new HashMap<>();
prices.put("Apple", 25.5);
prices.put("Banana", 10.0);
prices.put("Orange", 15.75);

for (String key : prices.keySet()) {
    System.out.println(key + " = " + prices.get(key));
}
```

---

## 🌍 Common Uses in Real Life

* **Databases**: Mapping student IDs to names or grades.
* **Caching**: Storing frequently accessed data for faster retrieval.
* **Counting frequencies**: Counting how many times a word appears in a text.
* **Configuration settings**: Storing key-value options (like `username → Khiel`).

# 🧱 HashSet and TreeSet

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🔍 Definition

In Java, **`HashSet`** and **`TreeSet`** are two implementations of the **`Set` interface** (from the Java Collections Framework).
Both are used to **store unique elements** — meaning duplicates are **not allowed**.
However, they differ in **ordering** and **performance**.

---

## ⚙️ How They Work

### 🔹 HashSet

* Uses a **hash table** to store elements.
* **Does not maintain any order** (elements appear randomly).
* Provides **constant-time performance** for basic operations like `add`, `remove`, and `contains`.

### 🔹 TreeSet

* Implements a **self-balancing binary search tree** (specifically a Red-Black tree).
* **Maintains elements in sorted (ascending) order** by default.
* Has **logarithmic-time performance** for basic operations.

---

## 💡 Why They’re Important

* They both **prevent duplicates** automatically.
* `HashSet` is great for **fast lookups** when order doesn’t matter.
* `TreeSet` is useful when you need **sorted data** or need to perform **range queries** (e.g., “get elements less than X”).

---

## 🧩 Examples

### 🧠 Example 1 – Using HashSet

```java
import java.util.HashSet;

public class HashSetExample {
    public static void main(String[] args) {
        HashSet<String> names = new HashSet<>();
        names.add("Khiel");
        names.add("Mark");
        names.add("Khiel"); // duplicate ignored
        names.add("Lara");

        System.out.println(names); // Output may vary (unordered)
    }
}
```

✅ Removes duplicates
❌ No guaranteed order

---

### 🧠 Example 2 – Using TreeSet

```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        TreeSet<Integer> numbers = new TreeSet<>();
        numbers.add(5);
        numbers.add(1);
        numbers.add(3);

        System.out.println(numbers); // Output: [1, 3, 5]
    }
}
```

✅ Automatically sorted in ascending order
✅ No duplicates

---

### 🧠 Example 3 – Comparing HashSet and TreeSet

```java
import java.util.*;

public class CompareSets {
    public static void main(String[] args) {
        Set<String> hashSet = new HashSet<>();
        Set<String> treeSet = new TreeSet<>();

        hashSet.add("B");
        hashSet.add("A");
        hashSet.add("C");

        treeSet.add("B");
        treeSet.add("A");
        treeSet.add("C");

        System.out.println("HashSet: " + hashSet); // Unordered
        System.out.println("TreeSet: " + treeSet); // Ordered: [A, B, C]
    }
}
```

---

## 🏁 Where They’re Commonly Used

* **`HashSet`**

  * When you only care about **uniqueness** (like usernames, IDs).
  * When **speed** is more important than order.
* **`TreeSet`**

  * When you need data **sorted automatically**.
  * When performing **range searches** or comparisons (like finding all names alphabetically before “M”).

# 🧱 Stack and Queue

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🔍 Definition

In Java, **Stack** and **Queue** are both **data structures** used to store and organize data.
The main difference lies in **how elements are added and removed**.

* **Stack** → **LIFO** (Last In, First Out)

  * The last element added is the first one removed.
* **Queue** → **FIFO** (First In, First Out)

  * The first element added is the first one removed.

---

## ⚙️ How They Work

### 🔹 Stack

* Works like a stack of plates — you put a plate on top and remove the top plate first.
* **Main operations**:

  * `push()` → Add element to the top.
  * `pop()` → Remove element from the top.
  * `peek()` → Look at the top element without removing it.

### 🔹 Queue

* Works like a line of people — the first person in line is served first.
* **Main operations**:

  * `offer()` or `add()` → Add element at the end.
  * `poll()` or `remove()` → Remove element from the front.
  * `peek()` → Look at the front element without removing it.

---

## 💡 Why They’re Important

* Both help in managing **data flow** efficiently.
* Used in algorithms like:

  * Undo/Redo systems → **Stack**
  * Task scheduling or printers → **Queue**
* Helps structure programs in **a logical and predictable order**.

---

## 🧩 Examples

### 🧠 Example 1 – Stack Example

```java
import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        Stack<String> stack = new Stack<>();

        stack.push("A");
        stack.push("B");
        stack.push("C");

        System.out.println("Stack: " + stack);
        System.out.println("Top element: " + stack.peek());

        stack.pop(); // removes "C"
        System.out.println("After pop: " + stack);
    }
}
```

🧩 Output:

```
Stack: [A, B, C]
Top element: C
After pop: [A, B]
```

✅ Last inserted item (“C”) is removed first.

---

### 🧠 Example 2 – Queue Example

```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {
    public static void main(String[] args) {
        Queue<String> queue = new LinkedList<>();

        queue.add("Khiel");
        queue.add("Mark");
        queue.add("Lara");

        System.out.println("Queue: " + queue);
        System.out.println("Front element: " + queue.peek());

        queue.poll(); // removes "Khiel"
        System.out.println("After poll: " + queue);
    }
}
```

🧩 Output:

```
Queue: [Khiel, Mark, Lara]
Front element: Khiel
After poll: [Mark, Lara]
```

✅ First element added (“Khiel”) is removed first.

---

### 🧠 Example 3 – Real-World Analogy

```java
// Using Stack to simulate undo feature
import java.util.Stack;

public class UndoFeature {
    public static void main(String[] args) {
        Stack<String> actions = new Stack<>();

        actions.push("Type 'Hello'");
        actions.push("Type 'World'");
        actions.push("Delete 'World'");

        System.out.println("Undo last action: " + actions.pop());
        System.out.println("Remaining actions: " + actions);
    }
}
```

✅ Useful in text editors, browsers (back/forward), and calculators.

---

## 🏁 Where They’re Commonly Used

| Structure | Common Uses                                                                       |
| --------- | --------------------------------------------------------------------------------- |
| **Stack** | Undo/Redo operations, expression evaluation, backtracking (e.g., browser history) |
| **Queue** | Task scheduling, order processing, printer queues, multithreading                 |

# 🧩 Collections Framework Overview

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧱 Definition

The **Java Collections Framework (JCF)** is a unified architecture for storing and manipulating groups of objects. It provides **interfaces**, **implementations (classes)**, and **algorithms** that make data management easier and more efficient.

In simple terms, the Collections Framework helps you handle data such as lists of students, sets of unique items, or mappings between keys and values — all with reusable, optimized data structures.

---

## ⚙️ How It Works

The framework is built around **interfaces** like `Collection`, `List`, `Set`, `Queue`, and `Map`.
Each interface defines a type of collection and its basic operations.
Concrete classes (like `ArrayList`, `HashSet`, and `HashMap`) implement these interfaces.

These collections can then be processed using **algorithms** — such as sorting, searching, or shuffling — provided by the `Collections` utility class.

---

### 🧩 Main Interfaces and Their Purposes

| Interface      | Description                                          | Common Implementations        |
| -------------- | ---------------------------------------------------- | ----------------------------- |
| **Collection** | Root interface for groups of objects                 | -                             |
| **List**       | Ordered collection (can contain duplicates)          | `ArrayList`, `LinkedList`     |
| **Set**        | Unordered, unique elements                           | `HashSet`, `TreeSet`          |
| **Queue**      | Elements processed in a specific order (FIFO/LIFO)   | `PriorityQueue`, `ArrayDeque` |
| **Map**        | Key-value pairs (not part of `Collection` hierarchy) | `HashMap`, `TreeMap`          |

---

## 🌟 Importance

* **Simplifies development:** Offers reusable and consistent data structures.
* **Improves performance:** Optimized algorithms and memory handling.
* **Enhances flexibility:** Easy to switch implementations (e.g., `ArrayList` → `LinkedList`) without changing code logic.
* **Supports generics:** Type-safe collections prevent runtime type errors.

---

## 💡 Example Usages

### Example 1: Using a List

```java
import java.util.*;

public class Example1 {
    public static void main(String[] args) {
        List<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");

        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```

🟢 *Stores and iterates through ordered elements.*

---

### Example 2: Using a Set

```java
import java.util.*;

public class Example2 {
    public static void main(String[] args) {
        Set<Integer> numbers = new HashSet<>();
        numbers.add(10);
        numbers.add(20);
        numbers.add(10); // duplicate ignored

        System.out.println(numbers);
    }
}
```

🟢 *Stores unique elements, ignoring duplicates.*

---

### Example 3: Using a Map

```java
import java.util.*;

public class Example3 {
    public static void main(String[] args) {
        Map<String, Integer> scores = new HashMap<>();
        scores.put("Alice", 90);
        scores.put("Bob", 85);
        scores.put("Charlie", 95);

        System.out.println(scores.get("Alice"));
    }
}
```

🟢 *Stores key-value pairs for fast lookups.*

---

## 🧭 Common Real-Life Uses

* Managing lists of data (students, products, etc.)
* Removing duplicates from a dataset (using `Set`)
* Storing key-value data (like dictionaries or user records)
* Implementing queues or stacks in simulations and games
* Efficiently sorting and searching data collections

# 🌀 Iterator and ListIterator in Java

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🔹 Definition

**Iterator** and **ListIterator** are interfaces in Java that allow you to traverse (or loop through) elements in a collection such as an `ArrayList`, `HashSet`, or `LinkedList`.
They provide a safer and more flexible way to iterate over a collection than using a simple `for` loop.

---

## 🔹 Iterator

The **Iterator** interface is used to **traverse collections** (like lists and sets) in a **forward direction only**.

### ✳️ Common Methods:

* `hasNext()` → returns `true` if there are more elements to iterate.
* `next()` → returns the next element.
* `remove()` → removes the last element returned by `next()` (optional operation).

### 💡 Example:

```java
import java.util.*;

public class IteratorExample {
    public static void main(String[] args) {
        List<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");

        Iterator<String> itr = fruits.iterator();
        while (itr.hasNext()) {
            String fruit = itr.next();
            System.out.println(fruit);
        }
    }
}
```

🧠 **Output:**

```
Apple
Banana
Cherry
```

---

## 🔹 ListIterator

The **ListIterator** interface is a **subinterface of Iterator** that works only with lists (like `ArrayList` or `LinkedList`) and allows **bidirectional traversal** (forward and backward).

### ✳️ Common Methods:

* `hasNext()` / `next()` → move forward.
* `hasPrevious()` / `previous()` → move backward.
* `add(E e)` → add an element.
* `remove()` → remove an element.
* `set(E e)` → replace the last element returned.

### 💡 Example:

```java
import java.util.*;

public class ListIteratorExample {
    public static void main(String[] args) {
        List<String> names = new ArrayList<>();
        names.add("Khiel");
        names.add("Alex");
        names.add("Mark");

        ListIterator<String> listItr = names.listIterator();

        System.out.println("Forward Direction:");
        while (listItr.hasNext()) {
            System.out.println(listItr.next());
        }

        System.out.println("\nBackward Direction:");
        while (listItr.hasPrevious()) {
            System.out.println(listItr.previous());
        }
    }
}
```

🧠 **Output:**

```
Forward Direction:
Khiel
Alex
Mark

Backward Direction:
Mark
Alex
Khiel
```

---

## 🔹 Key Differences Between Iterator and ListIterator

| Feature          | Iterator                | ListIterator                                     |
| ---------------- | ----------------------- | ------------------------------------------------ |
| Direction        | Forward only            | Both forward and backward                        |
| Collection Type  | Works on any collection | Works only on List (e.g., ArrayList, LinkedList) |
| Add elements     | ❌ Not allowed           | ✅ Allowed using `add()`                          |
| Replace elements | ❌ Not allowed           | ✅ Allowed using `set()`                          |
| Index access     | ❌ Not possible          | ✅ Possible (`nextIndex()`, `previousIndex()`)    |

---

## 🔹 Common Uses in Real Programming

1. **Safely removing elements** from a collection during iteration (avoiding `ConcurrentModificationException`).
2. **Navigating lists** both ways (like undo-redo systems).
3. **Updating list contents** while iterating.

# 🌀 For-Each Loop in Java

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🧩 Definition

The **for-each loop** (also called the **enhanced for loop**) in Java is a special kind of loop introduced in **Java 5** that simplifies iterating over arrays and collections.
Instead of using an index variable (like in a regular `for` loop), the for-each loop automatically goes through every element in the sequence.

📘 **Syntax:**

```java
for (dataType variable : collectionOrArray) {
    // use variable here
}
```

---

## ⚙️ How It Works

* The loop automatically retrieves each element from the array or collection, starting from the first up to the last element.
* It **does not** require a counter variable or use indexing.
* It is mainly used for **reading** data (not modifying the structure like adding/removing elements).

---

## 🌟 Why It Is Important

✅ **Simpler and cleaner code** — no need to manually manage loop indexes.
✅ **Less error-prone** — avoids mistakes like “off-by-one” errors.
✅ **Perfect for iteration** — useful when you only need to read each element.

---

## 💻 Examples

### 🧠 Example 1: Iterating over an Array

```java
public class ForEachExample1 {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};

        for (int n : numbers) {
            System.out.println(n);
        }
    }
}
```

🗒️ *This prints each number in the array without needing `numbers[i]`.*

---

### 🧠 Example 2: Iterating over a String Array

```java
public class ForEachExample2 {
    public static void main(String[] args) {
        String[] fruits = {"Apple", "Banana", "Cherry"};

        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```

🗒️ *Each fruit name is displayed — simple and readable.*

---

### 🧠 Example 3: Iterating over a Collection (ArrayList)

```java
import java.util.ArrayList;

public class ForEachExample3 {
    public static void main(String[] args) {
        ArrayList<String> names = new ArrayList<>();
        names.add("Khiel");
        names.add("Jessa");
        names.add("Mark");

        for (String name : names) {
            System.out.println(name);
        }
    }
}
```

🗒️ *The loop automatically iterates through all names in the list.*

---

## 🏁 Where It’s Commonly Used

* When reading values from **arrays** or **collections** (like `ArrayList`, `HashSet`, etc.)
* In **data processing** (printing, calculating totals, etc.)
* When you **don’t need to modify** the collection structure while looping

# 🗂️ File Handling (Read/Write)

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧩 Definition

**File Handling** in Java is the process of reading from and writing to files stored on a computer’s disk using the classes provided in the `java.io` and `java.nio` packages. It allows a program to **store data permanently**, unlike variables which lose their values once the program ends.

---

## ⚙️ How It Works

Java provides several classes to perform file operations:

* **FileReader / FileWriter** — for character-based file handling.
* **BufferedReader / BufferedWriter** — for efficient reading/writing.
* **FileInputStream / FileOutputStream** — for binary file handling.
* **Scanner** — for easy reading of text files.
* **PrintWriter** — for formatted text output.

When reading:

1. The program opens a file.
2. Reads data line by line or byte by byte.
3. Closes the file to free system resources.

When writing:

1. The program creates or opens a file.
2. Writes data into it.
3. Closes the file to save changes.

---

## 🎯 Importance

* Enables **data persistence** (data saved beyond program execution).
* Used in **log files**, **configuration files**, **report generation**, and **data processing**.
* Makes applications more powerful and realistic (e.g., saving user progress, storing transactions).

---

## 💻 Examples

### 🧠 Example 1: Writing to a File using `FileWriter`

```java
import java.io.FileWriter;
import java.io.IOException;

public class WriteExample {
    public static void main(String[] args) {
        try {
            FileWriter writer = new FileWriter("output.txt");
            writer.write("Hello, this is a file write example!");
            writer.close();
            System.out.println("Successfully wrote to the file.");
        } catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```

🟢 **Output:** Creates a file `output.txt` and writes text into it.

---

### 🧠 Example 2: Reading from a File using `BufferedReader`

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ReadExample {
    public static void main(String[] args) {
        try {
            BufferedReader reader = new BufferedReader(new FileReader("output.txt"));
            String line;
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
            reader.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

🟢 **Output:** Displays each line from `output.txt` on the console.

---

### 🧠 Example 3: Using `Scanner` for File Reading

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class ScannerReadExample {
    public static void main(String[] args) {
        try {
            File file = new File("output.txt");
            Scanner sc = new Scanner(file);
            while (sc.hasNextLine()) {
                System.out.println(sc.nextLine());
            }
            sc.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

🟢 **Output:** Reads and prints the content of `output.txt` using a `Scanner`.

---

## 🌍 Common Uses

* Saving user input or program output (e.g., **logs**, **reports**).
* Loading configuration or settings from a file.
* Reading datasets for analysis.
* Writing results from a computation to share or reuse later.
* Managing local storage in desktop applications.

# 🧱 Exception Handling (try, catch, finally, throws, throw)

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

## 🧩 Definition

**Exception Handling** in Java is a mechanism that allows programmers to **handle runtime errors** (like division by zero, invalid input, or file not found) in a structured and controlled way.
Instead of abruptly stopping the program, Java lets you detect and respond to these errors using special blocks like `try`, `catch`, `finally`, `throw`, and `throws`.

---

## ⚙️ How It Works

When a program runs and an error occurs:

1. Java **creates an Exception object** describing the error.
2. The program **searches for a matching catch block** to handle it.
3. If no match is found, the program stops and prints an error message.

The keywords used are:

* **`try`** — contains code that might cause an exception.
* **`catch`** — handles the exception if one occurs.
* **`finally`** — contains code that always runs (cleanup, closing files, etc.).
* **`throw`** — is used to **manually throw** an exception.
* **`throws`** — declares exceptions that a method **might throw** to its caller.

---

## 🔍 Why It’s Important

* Prevents **program crashes** by handling unexpected situations.
* Makes code **more reliable and readable**.
* Encourages **clear error messages and recovery mechanisms**.
* Separates **normal code** from **error-handling code**.

---

## 💻 Examples

### 🧠 Example 1: Basic try-catch

```java
public class Example1 {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // This causes ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero!");
        }
    }
}
```

**Output:**

```
Cannot divide by zero!
```

---

### 🧠 Example 2: try-catch-finally

```java
public class Example2 {
    public static void main(String[] args) {
        try {
            int[] numbers = {1, 2, 3};
            System.out.println(numbers[5]); // ArrayIndexOutOfBoundsException
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Index out of range!");
        } finally {
            System.out.println("Execution finished!");
        }
    }
}
```

**Output:**

```
Index out of range!
Execution finished!
```

---

### 🧠 Example 3: throw and throws

```java
class Example3 {
    static void checkAge(int age) throws Exception {
        if (age < 18) {
            throw new Exception("Not eligible to vote!");
        } else {
            System.out.println("Eligible to vote!");
        }
    }

    public static void main(String[] args) {
        try {
            checkAge(16);
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```
Not eligible to vote!
```

---

## 🌍 Real-Life / Programming Use Cases

* **File Handling:** Handling `IOException` when reading or writing files.
* **User Input Validation:** Avoiding crashes due to wrong input types.
* **Networking:** Managing connection errors during data transfer.
* **Database Access:** Catching SQL errors and retrying transactions.

# 🧱 Custom Exceptions

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

## 🧩 Definition

**Custom Exceptions** in Java are **user-defined exception classes** that allow developers to create their own types of errors. These are used when the built-in Java exceptions (like `NullPointerException`, `IOException`, etc.) do not clearly describe a specific problem in your program.

By extending the `Exception` or `RuntimeException` class, you can define an exception that fits your application’s needs.

---

## ⚙️ How It Works

* A **custom exception** is a **class** that extends `Exception` (for **checked exceptions**) or `RuntimeException` (for **unchecked exceptions**).
* You can define **constructors** in your custom exception class to pass error messages or other data.
* You then **throw** the custom exception using the `throw` keyword when a specific error occurs.

---

## 💡 Why It’s Important

Custom exceptions make your code:

* **More readable** — the exception name tells you exactly what went wrong.
* **More maintainable** — each error type can be handled differently.
* **More meaningful** — it provides domain-specific feedback, such as `InvalidAgeException` or `InsufficientFundsException`.

---

## 🧠 Examples

### 🧩 Example 1: Creating a Custom Checked Exception

```java
class InvalidAgeException extends Exception {
    public InvalidAgeException(String message) {
        super(message);
    }
}

public class TestAge {
    static void checkAge(int age) throws InvalidAgeException {
        if (age < 18)
            throw new InvalidAgeException("Age must be at least 18.");
        else
            System.out.println("Valid age!");
    }

    public static void main(String[] args) {
        try {
            checkAge(15);
        } catch (InvalidAgeException e) {
            System.out.println("Caught: " + e.getMessage());
        }
    }
}
```

**Output:**

```
Caught: Age must be at least 18.
```

---

### 🧩 Example 2: Custom Unchecked Exception

```java
class NegativeNumberException extends RuntimeException {
    public NegativeNumberException(String message) {
        super(message);
    }
}

public class Calculator {
    public static int squareRoot(int number) {
        if (number < 0)
            throw new NegativeNumberException("Number must be positive.");
        return (int)Math.sqrt(number);
    }

    public static void main(String[] args) {
        System.out.println(squareRoot(9));  // Works fine
        System.out.println(squareRoot(-4)); // Throws exception
    }
}
```

---

### 🧩 Example 3: Custom Exception in Bank Application

```java
class InsufficientFundsException extends Exception {
    public InsufficientFundsException(String message) {
        super(message);
    }
}

public class BankAccount {
    private double balance = 1000;

    public void withdraw(double amount) throws InsufficientFundsException {
        if (amount > balance)
            throw new InsufficientFundsException("Insufficient funds!");
        balance -= amount;
        System.out.println("Withdrawn: " + amount + " | Remaining: " + balance);
    }

    public static void main(String[] args) {
        BankAccount account = new BankAccount();
        try {
            account.withdraw(1500);
        } catch (InsufficientFundsException e) {
            System.out.println("Transaction failed: " + e.getMessage());
        }
    }
}
```

---

## 🏗️ Common Uses in Real Life

Custom exceptions are often used in:

* **Banking systems** (e.g., `InsufficientFundsException`)
* **User validation** (e.g., `InvalidEmailException`, `PasswordTooShortException`)
* **File operations** (e.g., `FileFormatException`)
* **Business logic errors** (e.g., `OrderNotFoundException`)

### StringTokenizer

![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

#### 🧩 Definition

`StringTokenizer` is a **utility class in Java** (found in `java.util` package) used to **split a string into smaller parts called tokens** based on a specified **delimiter** (like space, comma, etc.).
It’s an older way of breaking strings apart — newer programs often use `String.split()` or the `Scanner` class, but `StringTokenizer` is still useful for quick parsing tasks.

#### ⚙️ How It Works

* When you create a `StringTokenizer` object, you pass the **string** and an optional **delimiter**.
* It then scans the string and **extracts tokens** one by one each time you call `nextToken()`.
* The `hasMoreTokens()` method checks if there are more tokens left to read.

#### 🧠 Why It’s Important

`StringTokenizer` is lightweight and efficient for simple text parsing tasks such as reading comma-separated values or breaking up text commands.

---

#### 💻 Examples

**Example 1: Splitting words in a sentence**

```java
import java.util.StringTokenizer;

public class Example1 {
    public static void main(String[] args) {
        StringTokenizer st = new StringTokenizer("Java is fun");
        while (st.hasMoreTokens()) {
            System.out.println(st.nextToken());
        }
    }
}
```

📤 **Output:**

```
Java
is
fun
```

---

**Example 2: Using a custom delimiter**

```java
import java.util.StringTokenizer;

public class Example2 {
    public static void main(String[] args) {
        StringTokenizer st = new StringTokenizer("Apple,Orange,Banana", ",");
        while (st.hasMoreTokens()) {
            System.out.println(st.nextToken());
        }
    }
}
```

📤 **Output:**

```
Apple
Orange
Banana
```

---

**Example 3: Counting tokens**

```java
import java.util.StringTokenizer;

public class Example3 {
    public static void main(String[] args) {
        String data = "one two three four";
        StringTokenizer st = new StringTokenizer(data);
        System.out.println("Total tokens: " + st.countTokens());
    }
}
```

📤 **Output:**

```
Total tokens: 4
```

---

#### 🌍 Common Uses

* Parsing text files or CSV data
* Breaking user input into parts (like commands)
* Tokenizing strings for data processing or search functions

**Date and Time (LocalDate, LocalTime, LocalDateTime)**
![java-badge](https://img.shields.io/badge/Language-Java-red) ![level-badge](https://img.shields.io/badge/Level-Intermediate--Friendly-orange)

---

### 🧩 **Definition**

In Java, the `java.time` package (introduced in Java 8) provides powerful classes to handle **dates and times** easily and safely.
Three of the most commonly used classes are:

* **`LocalDate`** — represents a date (year, month, day) without time.
* **`LocalTime`** — represents a time (hour, minute, second) without a date.
* **`LocalDateTime`** — represents both date and time together.

---

### ⚙️ **How It Works**

These classes belong to the `java.time` API and are **immutable** (cannot be changed once created).
They are part of Java’s effort to replace the older `Date` and `Calendar` classes, which were confusing and error-prone.

You can use static methods like `now()`, `of()`, and `parse()` to create date/time objects, and methods like `plusDays()`, `minusHours()`, or `getYear()` to manipulate or access them.

---

### 🌟 **Why It’s Important**

* Provides **clear and easy-to-read** time handling.
* Avoids **time zone issues** (these classes don’t include zones).
* Makes **date and time arithmetic** simpler (like adding days, hours, or seconds).
* Fully **thread-safe** and **immutable**, reducing bugs in concurrent programs.

---

### 💻 **Examples**

#### 1. **Using LocalDate**

```java
import java.time.LocalDate;

public class Example1 {
    public static void main(String[] args) {
        LocalDate today = LocalDate.now(); // current date
        LocalDate birthday = LocalDate.of(2007, 3, 15); // specific date
        System.out.println("Today: " + today);
        System.out.println("Birthday: " + birthday);
    }
}
```

#### 2. **Using LocalTime**

```java
import java.time.LocalTime;

public class Example2 {
    public static void main(String[] args) {
        LocalTime timeNow = LocalTime.now();
        LocalTime classStart = LocalTime.of(8, 30); // 8:30 AM
        System.out.println("Current Time: " + timeNow);
        System.out.println("Class Starts At: " + classStart);
    }
}
```

#### 3. **Using LocalDateTime**

```java
import java.time.LocalDateTime;

public class Example3 {
    public static void main(String[] args) {
        LocalDateTime now = LocalDateTime.now();
        LocalDateTime future = now.plusDays(7).minusHours(3);
        System.out.println("Now: " + now);
        System.out.println("Next Week (3 hours earlier): " + future);
    }
}
```

---

### 🌍 **Where It’s Commonly Used**

* **Logging events** — timestamps for when actions happen.
* **Scheduling tasks** — setting reminders or deadlines.
* **Recording transactions** — in banking, e-commerce, and booking systems.
* **Tracking user activity** — login time, post date, etc.

Perfect — let’s **deep dive directly** into these four pillars of Java development.
No simplified prompts — just a professional-level exploration designed to build your core programming strength.

---

## 🧩 1. Object-Oriented Programming (OOP)

### 🔹 What It Really Is

OOP is a programming paradigm based on **objects** — bundles of **state** (fields) and **behavior** (methods).
It models software as a set of **interacting entities**, similar to how real-world systems work.
Java is **purely object-oriented** (except for primitives) and enforces OOP principles throughout.

### 🔹 Core Principles

1. **Encapsulation** – Binding data and methods into one unit (the class) and restricting access with access modifiers (`private`, `public`, `protected`).

   * Ensures controlled access via getters/setters.
2. **Inheritance** – Allows a subclass to reuse and extend behavior from a superclass (`extends` keyword).

   * Promotes code reuse and hierarchy modeling.
3. **Polymorphism** – Objects of different classes can be treated uniformly via inheritance or interfaces.

   * Achieved through method overriding and dynamic binding.
4. **Abstraction** – Hiding complex implementation details behind a simple interface (`abstract` classes or `interfaces`).

   * Encourages cleaner APIs and modular design.

### 🔹 Advanced Design Concepts (from *Effective Java*)

* Prefer **composition over inheritance** — instead of extending classes, hold references to them.
* Keep classes **immutable** whenever possible.
* Use **interfaces** to define contracts rather than implementation details.

### 🔹 Example Use Cases

* Modeling entities like `Student`, `Employee`, `Account`, or `Vehicle`.
* Creating frameworks (e.g., Spring, Hibernate) that heavily rely on interfaces, inheritance, and polymorphism.
* Building scalable systems using clean, modular OOP design.

---

## 🧮 2. Collections Framework

### 🔹 Purpose

Collections manage **groups of objects** efficiently — storing, searching, sorting, and iterating.
They are part of `java.util` and include **interfaces**, **implementations**, and **algorithms**.

### 🔹 Core Interfaces

* **Collection** – the root interface (except `Map`).
* **List** – ordered, allows duplicates (`ArrayList`, `LinkedList`).
* **Set** – unique elements only (`HashSet`, `TreeSet`).
* **Queue/Deque** – process elements in specific orders (FIFO, LIFO).
* **Map** – key-value pairs (`HashMap`, `TreeMap`, `LinkedHashMap`).

### 🔹 Key Features

* **Generic typing** (`List<String> names = new ArrayList<>();`)
* **Iterators and for-each loops** for traversal.
* **Utility methods** (`Collections.sort()`, `Collections.shuffle()`, etc.)
* **Concurrent Collections** (`ConcurrentHashMap`, `CopyOnWriteArrayList`) for thread-safe use.

### 🔹 Professional Practice (from *Effective Java* and *Java Concurrency in Practice*)

* Always use **interfaces** as reference types (`List` instead of `ArrayList`).
* Prefer **unmodifiable collections** for read-only data.
* Use **streams and lambdas** for functional-style processing (`list.stream().filter(...).collect(...)`).

### 🔹 Example Use Cases

* Maintaining a user database in a `HashMap`.
* Managing a task queue with `LinkedList` or `PriorityQueue`.
* Handling concurrent requests using `ConcurrentHashMap`.

---

## 📂 3. File Handling

### 🔹 Overview

Java provides both **classic I/O (java.io)** and **modern NIO (java.nio)** for working with files.
File handling enables programs to **read, write, and manipulate external data**.

### 🔹 Classic I/O

* `FileReader` / `BufferedReader` – for text input
* `FileWriter` / `BufferedWriter` – for writing text
* `FileInputStream` / `FileOutputStream` – for binary data

### 🔹 Modern NIO (Non-blocking I/O)

* `Files`, `Paths`, `Path`, `FileChannel`, `ByteBuffer` classes
* Easier and faster for large data and real-time applications
  Example:

```java
Path path = Paths.get("data.txt");
List<String> lines = Files.readAllLines(path);
Files.write(path, "New Line".getBytes(), StandardOpenOption.APPEND);
```

### 🔹 Best Practices (from *Java Performance: The Definitive Guide*)

* Use **buffered I/O** to minimize disk access time.
* Always **close resources** using `try-with-resources`.
* Avoid unnecessary reads/writes — work with memory buffers if possible.
* For large files, consider **streaming** or **memory-mapped I/O**.

### 🔹 Example Use Cases

* Reading configuration files.
* Writing logs or saving reports.
* Processing CSV or JSON data.

---

## ⚙️ 4. Exception Management

### 🔹 Purpose

Exception handling ensures a program can **handle runtime errors** gracefully without crashing.
Java’s exception model separates **normal flow** from **error handling** logic.

### 🔹 Types of Exceptions

1. **Checked Exceptions** – must be declared or handled (`IOException`, `SQLException`).
2. **Unchecked Exceptions** – runtime errors (`NullPointerException`, `ArrayIndexOutOfBoundsException`).
3. **Errors** – serious problems not meant to be caught (`OutOfMemoryError`).

### 🔹 Key Mechanisms

* `try`, `catch`, `finally`, `throw`, `throws`
* `try-with-resources` for automatic closing
* Custom exceptions:

  ```java
  class InvalidAgeException extends Exception {
      public InvalidAgeException(String message) {
          super(message);
      }
  }
  ```

### 🔹 Best Practices (from *Effective Java*, Items 69–77)

* Don’t use exceptions for normal control flow.
* Always **include meaningful messages**.
* Catch only exceptions you can handle.
* Wrap and rethrow when translating lower-level errors.
* Avoid swallowing exceptions silently.

### 🔹 Example Use Cases

* File not found or permission denied.
* Invalid user input in form processing.
* Network or database disconnection.

---

## 🚀 Summary Roadmap

| Area                     | Core Skills to Master                                 | Professional Focus                    |
| ------------------------ | ----------------------------------------------------- | ------------------------------------- |
| **OOP**                  | Encapsulation, Inheritance, Polymorphism, Abstraction | System Design, Framework Architecture |
| **Collections**          | Lists, Sets, Maps, Generics, Iterators, Streams       | Data Management, Efficiency           |
| **File Handling**        | Buffered I/O, NIO, Serialization                      | Data Storage, Logging, Configurations |
| **Exception Management** | Checked/Unchecked, Custom Exceptions                  | Robust, Reliable Code                 |
















