# Why did you choose Java?
->I chose Java because I was more interested in backend and enterprise application development. Java has a strong ecosystem, good performance, and frameworks like Spring Boot that are widely used for building production applications. Since I enjoyed working with Java during my course and projects, I decided to specialize in it.

# what is java ?
->Java is a high-level, object-oriented, general-purpose programming language developed by Sun Microsystems. It is designed to be platform-independent using the JVM, which follows the principle "Write Once, Run Anywhere."

# Is Java Platform Independent?
-> Java is a platform-independent programming language because its source code is compiled into bytecode rather than machine-specific code. This bytecode can run on any operating system that has a compatible Java Virtual Machine (JVM) installed

# What are the top Java Features?
-> Simple: Java is quite simple to understand and the syntax
Platform Independent: Java is platform independent means we can run the same program in any software and hardware and will get the same result.
Interpreted: Java is interpreted as well as a compiler-based language. 
Robust: features like Garbage collection, exception handling, etc that make the language robust.
Object-Oriented: Java is an object-oriented language that supports the concepts of class,  objects, four pillars of OOPS, etc. 
Secured: As we can directly share an application with the user without sharing the actual program makes Java a secure language. 
High Performance:  faster than other traditional interpreted programming languages.
Dynamic: supports dynamic loading of classes and interfaces.
Distributed: feature of Java makes us able to access files by calling the methods from any machine connected.
Multithreaded: deal with multiple tasks at once by defining multiple threads
Architecture Neutral: it is not dependent on the architecture.

# What is JVM?
-> JVM stands for Java Virtual Machine. It is a part of the Java Runtime Environment that executes Java bytecode.
When we compile a Java program, the Java compiler converts the source code into bytecode. The JVM then executes this bytecode and converts it into machine-level instructions that the operating system can understand.

# What is JIT?
-> JIT stands for Just-In-Time Compiler. It is a component of the JVM that compiles frequently executed Java bytecode into native machine code at runtime.This improves performance because the JVM can execute the compiled native code directly instead of repeatedly interpreting the same bytecode.


# What are Memory storages available with JVM?
-> JVM memory is divided into several runtime data areas: Heap, Stack, Method Area, PC Register, and Native Method Stack.

The Heap is used to store objects and instance variables.
The Stack stores method calls, local variables.
The Method Area stores class-level information such as class metadata, static variables, and method information.
The PC Register keeps track of the current instruction being executed by each thread.
The Native Method Stack is used for executing native methods written in languages such as C or C++.

# What is a classloader?
-> Classloader is a JVM component responsible for loading Java classes into memory at runtime. It loads classes only when they are needed, improving memory efficiency and application performance

# Difference between JVM, JRE, and JDK.
-> 
JVM stands for Java Virtual Machine. It is responsible for executing Java bytecode.

JRE stands for Java Runtime Environment. It provides the JVM along with the required Java libraries and other components needed to run Java applications.

JDK stands for Java Development Kit. It contains the JRE along with development tools such as the Java compiler, debugger, and other tools required to develop Java applications.

# Explain public static void main(String args[]) in Java.
-> The public static void main(String args[]) method is the entry point of a Java application. 

public: Makes the method accessible from anywhere so that the JVM can invoke it.
static: Allows the method to be called without creating an object of the class.
void: Specifies that the method does not return any value.
main: The predefined method name that acts as the starting point of program execution.
String args[]: Stores command-line arguments passed to the Java program as an array of strings.

# What is Java String Pool?
-> The Java String Pool (JSP) is a special memory area inside the heap where Java stores string literals. It helps save memory by reusing existing string objects instead of creating duplicate ones.

# What will happen if we don't declare the main as static?
-> We can declare the main method without using static and without getting any errors. But, the main method will not be treated as the entry point to the application or the program.

# What are Packages in Java?
-> Packages in Java can be defined as the grouping of related types of classes, interfaces

# Why Packages are used?
-> Packages are used in Java to organize related classes and interfaces. They help make the code easier to maintain and understand.

# How many types of packages are there in Java?
-> There are two types of packages in Java
    User-defined packages
    Build In packages

# Explain different data types in Java.
-> Primitive Data Type: Primitive data are single values with no special capabilities. There are 8 primitive data types:

boolean: stores value true or false
byte: stores an 8-bit signed two's complement integer
char: stores a single 16-bit Unicode character
short: stores a 16-bit signed two’s complement integer
int: stores a 32-bit signed two’s complement integer
long: stores a 64-bit two’s complement integer
float: stores a single-precision 32-bit IEEE 754 floating-point
double: stores a double-precision 64-bit IEEE 754 floating-point
Non-Primitive Data Type: Reference Data types will contain a memory address of the variable's values because it is not able to directly store the values in the memory. Types of Non-Primitive are mentioned below:

String: Stores a sequence of characters.
Array: Stores multiple values of the same type.
Class: Blueprint for creating objects.
Object: Instance of a class.
Interface: Defines a contract that classes can implement.


 # Can we declare Pointer in Java?
 -> No, Java doesn't provide the support of Pointer

 # What is the Wrapper class in Java?
-> A Wrapper Class is a class that converts a primitive data type into an object and vice versa. It allows primitive values to be used where objects are required, such as in collections and generic classes.


# Why do we need wrapper classes?
-> We need wrapper classes when an object is required, for example, when working with collections like ArrayList, because collections store objects and cannot directly store primitive data types.

# Differentiate between instance and local variables.
-> Instance variables are declared inside a class but outside any method, constructor, or block. They belong to an object, so each object has its own copy of the instance variable. They get a default value if no value is assigned.

Local variables are declared inside a method, constructor, or block. They belong to that particular method or block and are created when the method is called. They do not get a default value, so we must initialize them before using them.

# What is a Class Variable?
-> A class variable is a variable declared inside a class using the static keyword. It belongs to the class rather than to individual objects.

Only one copy of a class variable is created, and it is shared by all objects of that class. It can be accessed using the class name without creating an object.


# What is the default value stored in Local Variables?
-> There is no default value stored with local variables. Also, primitive variables and objects don't have any default values.

# Explain the difference between instance variable and a class variable.
-> An instance variable is a variable declared inside a class but outside methods, constructors, or blocks, without the static keyword. Each object gets its own separate copy of an instance variable.

A class variable is declared using the static keyword. It belongs to the class, so only one copy is created and shared among all objects of that class.

# What is the difference between System.out, System.err, and System.in?
-> System.out, System.err, and System.in are standard input and output streams in Java.

System.out is used to display normal output to the console.

System.err is used to display error or diagnostic messages to the console.

System.in is used to read input from the user, usually from the keyboard.


# What do you understand by an IO stream?
-> I/O stream stands for Input/Output stream. It represents a flow of data between a Java program and a source or destination.
Input streams are used to read data into the program, while output streams are used to write data from the program to a destination.

# What is the Difference Between the Reader/Writer and InputStream/OutputStream Class Hierarchies?
-> InputStream and OutputStream are used to read and write data in the form of bytes. They are mainly suitable for binary data such as images, videos, audio, and PDF files.

Reader and Writer are used to read and write data in the form of characters. They are mainly designed for text data and handle character encoding more conveniently.


# What are the FileInputStream and FileOutputStream?
-> FileInputStream and FileOutputStream are classes used to perform file operations using byte streams.

FileInputStream is used to read data from a file as bytes. It is mainly suitable for binary files such as images, audio, videos, and PDFs.

FileOutputStream is used to write data to a file as bytes. It can be used to create a new file or write data into an existing file.

# What is the purpose of using BufferedInputStream and BufferedOutputStream classes?
-> BufferedInputStream and BufferedOutputStream are used to improve the performance of input and output operations by reducing the number of direct interactions with the underlying device or file. They achieve this by storing data temporarily in a buffer.

BufferedInputStream reads a large block of data into memory and provides it to the program as needed, reducing disk access.
BufferedOutputStream stores data in a buffer and writes it to the destination in larger chunks, reducing write operations.

# How many ways you can take input from the console?
-> Command-Line Arguments: Input is passed when the program is executed.
BufferedReader Class: Reads character input efficiently from the console.
Console Class: Provides methods for reading text and passwords securely.
Scanner Class: Commonly used to read different types of input such as int, double, and String from the console.

# What are operators? 
-> Operators are special symbols in Java that perform specific operations on variables, values, or expressions. They are used to manipulate data and produce a result.
Java provides various types of operators, including Arithmetic, Relational, Logical, Assignment, Bitwise, Unary, and Ternary operators.

# What is dot operator?
-> The Dot operator in Java is used to access the instance variables and methods of class objects. It is also used to access classes and sub-packages from the package.

 # What is the transient keyword?
-> The transient keyword is used at the time of serialization if we don’t want to save the value of a particular variable in a file. When JVM comes across a transient keyword, it ignores the original value of the variable and saves the default value of that variable data type.

# What is String in Java?
-> A String in Java is an object that represents a sequence of characters. Strings are immutable, meaning their value cannot be changed after creation.

# What are the differences between String and StringBuffer?
-> String is an immutable class, which means its value cannot be changed after the object is created. If we modify a String, a new String object is created.

StringBuffer is a mutable class, which means we can modify its existing object without creating a new object for every change.

# What are the differences between StringBuffer and StringBuilder?
-> StringBuffer and StringBuilder are both mutable classes used to modify character sequences.

The main difference is that StringBuffer is synchronized, so it is thread-safe and can be safely used by multiple threads. Because of synchronization, it is generally slower.

StringBuilder is not synchronized, so it is not thread-safe, but it is generally faster than StringBuffer.


# What is an array in Java?
-> An array in Java is a data structure used to store multiple values of the same data type in a single variable. It allows elements to be stored and accessed using an index.

# On which memory arrays are created in Java?
-> In Java, array objects are created in heap memory, which is used for dynamic memory allocation during program execution.

#  What are the main concepts of OOPs in Java?
-> OOP stands for Object-Oriented Programming. It is a programming approach where we organize a program using classes and objects.
The four main principles of OOP are:
Encapsulation: Bundles data and methods into a single unit (class) and restricts direct access to data using access modifiers.
Inheritance: Allows one class to acquire the properties and behaviors of another class, promoting code reusability.
Polymorphism: Enables a single interface or method to perform different actions depending on the object or context.
Abstraction: Hides implementation details and exposes only the essential features to the user.

# How is the ‘new’ operator different from the ‘newInstance()’ operator in Java? 
->The new operator is used to create an object directly by specifying the class name at compile time. 
newInstance() is used to create an object dynamically at runtime using reflection. 

# What are Classes in Java? 
-> A class in Java is a blueprint or template for creating objects. It defines the properties and behaviors of an object using variables and methods.A class can contain instance variables, methods, constructors, static variables, static methods.

# What is this keyword in Java?
-> The this keyword is a reference variable that refers to the current object of a class. It is used to access the current object's variables, methods, and constructors.

# What are Access Specifiers and their types in Java?
->public: Accessible from anywhere in the program, including different packages.
protected: Accessible within the same package and by subclasses in other packages.
default (package-private): Accessible only within the same package. No keyword is used.
private: Accessible only within the same class.

# What is an object?
-> An object is an instance of a class. It is created using the new keyword and represents a real-world entity.
An object has state, behavior, and identity. The state is represented by instance variables, behavior is represented by methods, and identity is the unique reference of the object.

# What are the different ways to create objects in Java?
-> Using new keyword
Using new instance
Using clone() method
Using deserialization
Using the newInstance() method of the Constructor class

# What is the constructor?
-> A constructor is a special member of a class that is automatically called when an object is created. Its primary purpose is to initialize the object's data members.

# What happens if you don't provide a constructor in a class?
-> If you don't provide a constructor in a class in Java, the compiler automatically generates a default constructor with no arguments and no operation which is a default constructor.

# What is the purpose of a default constructor?
-> A default constructor is a no-argument constructor that is used to initialize an object with default values when no constructor is explicitly defined in a class.

# Where and how can you use a private constructor?
->A private constructor is a constructor with the `private` keyword.
It **stops other classes from creating objects** of that class.
It is mainly used in:
* **Singleton class** – to allow only one object.
* **Utility class** – when we don't want anyone to create an object.
The private constructor can be used **inside the same class**.


# What are the differences between the constructors and methods?
-> A constructor is a special member of a class that is used to initialize an object. It has the same name as the class and does not have a return type. It is automatically called when an object is created.

A method is used to perform a specific operation or define the behavior of an object. A method can have any valid name, must have a return type or void, and is called explicitly.

# What is an Interface?
-> An interface in Java is a blueprint of a class that defines a set of abstract methods that implementing classes must provide. It is used to achieve abstraction and support multiple inheritance.

# Give some features of the Interface.
-> An interface is used to achieve abstraction.
A class can implement multiple interfaces.
Interface methods are public and abstract by default (except default, static, and private methods).
Interface variables are public, static, and final by default.
A class uses the implements keyword to implement an interface.

# What is a marker interface?
An Interface is recognized as an empty interface (no field or methods) it is called a marker interface. Examples of marker interfaces are Serializable, Cloneable, and Remote interfaces. 

# What are the differences between abstract class and interface?
-> An abstract class can have both abstract and normal methods, and it can have instance variables and a constructor. An interface is mainly used to define rules that a class must follow. A class can extend only one abstract class but can implement multiple interfaces

# What do you mean by data encapsulation?
-> Data encapsulation is the process of wrapping data and methods into a single unit, such as a class, and restricting direct access to the data. In Java, we achieve encapsulation mainly by declaring variables as private and providing public getter and setter methods for controlled access.

# What are the advantages of Encapsulation in Java?
-> The main advantages of encapsulation are data hiding, controlled access, data security, and better maintainability.
By keeping variables private and providing public methods, we can control how the data is accessed or modified. We can also add validation inside setter methods.

# What is the primary benefit of Encapsulation? 
-> The primary benefit of encapsulation is data hiding. It protects the internal data of an object from direct access and provides controlled access through methods such as getters and setters.

# Define Inheritance.
-> Inheritance is an OOP concept in which a child class acquires the properties and methods of a parent class.
In Java, inheritance is achieved using the extends keyword. It promotes code reusability and establishes an IS-A relationship between classes.

# What are the multiple type inheritance in java
-> There are five commonly discussed types of inheritance: Single, Multilevel, Hierarchical, Multiple, and Hybrid inheritance.
Java supports Single, Multilevel, and Hierarchical inheritance through classes.
Java does not support Multiple and Hybrid inheritance through classes because they can cause ambiguity. However, multiple inheritance can be achieved using interfaces.

# What is multiple inheritance? Is it supported by Java?
-> Multiple inheritance is a type of inheritance where one child class inherits from two or more parent classes.
Java does not support multiple inheritance through classes because it can cause ambiguity, such as the diamond problem.
However, Java supports multiple inheritance through interfaces. A class can implement multiple interfaces using the implements keyword.

# What is the ‘IS-A ‘ relationship in OOPs Java?
-> The IS-A relationship represents inheritance in Java. It means that one class is a type of another class.
It is achieved using the extends keyword for class inheritance and the implements keyword for interfaces.

# What is an association?
-> Association is a relationship between two independent classes or objects where one object is connected to or interacts with another object.

For example, a Student and a Teacher have an association because a student learns from a teacher. Both Student and Teacher can exist independently.

Association represents a general relationship between objects.

# What do you mean by aggregation?
-> Aggregation is a HAS-A relationship between two classes where one class contains a reference to another class, but both objects can exist independently

For example, an Employee has an Address. If the Employee object is removed, the Address object can still exist independently.

Therefore, aggregation represents a weak relationship between objects.

# What is the composition of Java?
-> Composition is a strong HAS-A relationship between two classes where one class owns another object.
For example, a Car has an Engine. The Car creates and manages its Engine, so this represents composition.

# What is Polymorphism?
-> Polymorphism means one thing having many forms. In Java, polymorphism allows the same method or interface to behave differently depending on the object or situation.

There are two types of polymorphism in Java: compile-time polymorphism, which is achieved through method overloading, and runtime polymorphism, which is achieved through method overriding.

# What is runtime polymorphism or dynamic method dispatch?
-> Runtime polymorphism, also called dynamic method dispatch, is a mechanism in which a parent class reference refers to a child class object, and the overridden method is determined at runtime.
It is achieved through method overriding.

# What is method overriding?
-> Method overriding occurs when a child class provides its own implementation of a method that is already defined in the parent class.
The method must have the same name and parameters, with the same or a compatible return type.
Method overriding is used to achieve runtime polymorphism, where the method to be executed is determined at runtime based on the actual object.

# What is method overloading?
-> Method overloading occurs when a class contains multiple methods with the same name but different parameter lists.
The parameters can differ in number, type, or order. Method overloading is an example of compile-time polymorphism because the compiler determines which method to call based on the arguments.

# Can we override the overloaded method?
-> Yes, an overloaded method can be overridden.
If a parent class has multiple overloaded methods, the child class can override any of those methods by providing the same method signature. So, overloading and overriding can exist together, but overloading is based on different parameters, while overriding is based on the same method signature in a child class.


# Can we overload the main() method?
-> Yes in Java we can overload the main method to call the main method with the help of its predefined calling method. 

# Can we override the private methods?
-> No, private methods cannot be overridden in Java because they are accessible only within the class in which they are declared. Since child classes cannot access private methods, they cannot provide an overriding implementation.

# Can we change the scope of the overridden method in the subclass?
-> Yes, a subclass can increase the visibility of an overridden method, but it cannot reduce it.
Visibility can be widened (e.g., protected -> public).
Visibility cannot be narrowed (e.g., public -> protected or private).

# What is Abstraction?
-> Abstraction is the process of hiding implementation details and showing only the essential functionality to the user.
In Java, abstraction can be achieved using abstract classes and interfaces.
For example, an abstract class can define what a method should do, while the child class provides the actual implementation.

# What is Abstract class?
-> An abstract class is a class declared with the abstract keyword that cannot be instantiated directly.
It can contain both abstract methods and concrete methods, along with constructors and instance variables.
An abstract class is mainly used to provide common state and behavior to related child classes while leaving some methods for the child classes to implement.

# When Abstract methods are used?
-> Abstract methods are used when we want to force child classes to implement a particular method. The parent class only declares the method, while the child class provides its implementation.


# What is Collection Framework in Java explain in detail?
->The Java Collection Framework is a set of interfaces, classes, and utility methods provided by Java to store and manipulate groups of objects.

It provides ready-made data structures such as ArrayList, LinkedList, HashSet, TreeSet, HashMap, TreeMap, and PriorityQueue.

The main interfaces are List, Set, Queue, and Map. List allows duplicates and maintains order, Set does not allow duplicates, Queue is used for processing elements in a particular order, and Map stores data in key-value pairs.

The Collection Framework makes data storage and manipulation easier, more flexible, and reusable compared to creating our own data structures.


# What is Exception Handling? explain in detail
->Java exceptions are mainly classified as checked and unchecked exceptions.
Exception handling is a mechanism in Java used to handle runtime errors and maintain the normal flow of the program.

Java provides five keywords for exception handling: try, catch, finally, throw, and throws.

The try block contains code that may cause an exception, the catch block handles the exception, and the finally block is used for cleanup code that normally needs to execute whether an exception occurs or not.

# What do you mean by a Multithreaded program? explain in detail in java
-> A multithreaded program is a program that executes multiple threads concurrently within a single process.
A thread is a lightweight unit of execution, and each thread can perform a different task. Multithreading can improve application responsiveness, throughput, and CPU utilization.
In Java, we can create concurrent tasks using Thread, Runnable, or higher-level concurrency utilities such as ExecutorService.

#  Explain various interfaces used in the Collection framework.
-> List: Stores elements in insertion order and allows duplicate values (e.g., ArrayList, LinkedList).
Set: Stores unique elements and does not allow duplicates (e.g., HashSet, LinkedHashSet, TreeSet).
Queue: Stores elements for processing in a specific order, typically FIFO (e.g., PriorityQueue, ArrayDeque).
Map: Stores data as key-value pairs, where each key is unique (e.g., HashMap, LinkedHashMap, TreeMap).

# How can you synchronize an ArrayList in Java?
-> An ArrayList can be synchronized using two methods mentioned below:

Using Collections.synchronizedList()
Using CopyOnWriteArrayList

# Why do we need a synchronized ArrayList when we have Vectors (which are synchronized) in Java?
-> ArrayList is in need even when we have Vectors because of certain reasons:

ArrayList is faster than Vectors.
ArrayList supports multithreading whereas Vectors only supports single-thread use.
ArrayList is safer to use, as Vectors supports single threads and individual operations are less safe and take longer to synchronize.
Vectors are considered outdated in Java because of their synchronized nature.


# What is a Vector in Java?
-> A Vector is a dynamic array class in Java that can grow or shrink automatically as elements are added or removed. It is similar to ArrayList but is synchronized, making it thread-safe.

# How to make Java ArrayList Read-Only?
->An ArrayList can be made ready only using the method provided by Collections using the Collections.unmodifiableList() method. 

# What is a priority queue in Java?
-> PriorityQueue is a class in Java that implements the Queue interface and processes elements based on their priority rather than insertion order.

By default, it uses natural ordering, so the smallest element has the highest priority for numbers.

# Explain the LinkedList class.
-> LinkedList is a class in the java.util package that implements the List and Deque interfaces. It internally uses a doubly linked list, where each node stores data and references to the previous and next nodes.

It maintains insertion order, allows duplicate and null elements, and supports efficient insertion and deletion when the relevant position or node is known. However, accessing an element by index is slower than ArrayList because LinkedList needs to traverse the nodes.

# What is the Stack class in Java and what are the various methods provided by it?
-> The Stack class in Java is a class from the `java.util` package that follows the LIFO principle, which means Last In, First Out.
It is used when we need to add and remove elements from the top of the stack.
Some commonly used methods are `push()`, `pop()`, `peek()`, `empty()`, and `search()`.

# What is Set in Java?

- Set is a collection that **does not allow duplicate elements**.
Main implementations:
* **HashSet:** Stores unique elements, no guaranteed order.
* **LinkedHashSet:** Maintains insertion order.
* **TreeSet:** Stores elements in sorted order.

# what is List
List is a collection that **allows duplicate elements** and **maintains insertion order**.
Main implementations:
* **ArrayList:** Fast for accessing elements.
* **LinkedList:** Efficient for insertion/deletion at suitable positions.
* **Vector:** Synchronized, legacy implementation.

# what is Queue
Queue is a collection that generally follows **FIFO (First In, First Out)**.
Main implementations:

* **PriorityQueue:** Processes elements based on priority.
* **LinkedList:** Can be used as a Queue.
* **ArrayDeque:** Efficient double-ended queue.

# what is Map
Map stores data in **key-value pairs**. Keys must be unique, but values can be duplicated.
Main implementations:

* **HashMap:** No guaranteed order.
* **LinkedHashMap:** Maintains insertion order.
* **TreeMap:** Stores keys in sorted order.

# What is the HashSet class in Java and how does it store elements?
-> A HashSet is a class in the Java Collections Framework that implements the Set interface and stores only unique elements. It uses a hash table internally to store and retrieve elements efficiently.

# What is LinkedHashSet in Java Collections Framework?
->The LinkedHashSet is an ordered version of Hashset maintained by a doubly-linked List across all the elements. It is very helpful when iteration order is needed. During Iteration in LinkedHashSet, elements are returned in the same order they are inserted.

# Explain Treemap in Java
-> TreeMap is a type of map that stores data in the form of key-value pair. It is implemented using the red-black tree. Features of TreeMap are :
It contains only unique elements.
It cannot have a NULL key 
It can have multiple NULL values.
It is non-synchronized.
It maintains ascending order.

# What is EnumSet?
EnumSet is a specialized implementation of the Set interface for use with enumeration type. A few features of EnumSet are:
It is non-synchronized.
Faster than HashSet.

# What is an Iterator?
-> Iterator is an interface in Java used to traverse or access elements of a collection one by one.
The main methods are:
hasNext() → checks if another element exists.
next() → returns the next element.
remove() → removes the current element.

# What is Enumeration?
->Enumeration (`Enumeration`) is an **interface in Java** used to **traverse elements of legacy collections one by one**.

Main methods:
* `hasMoreElements()` → checks if more elements are available.
* `nextElement()` → returns the next element.

# Difference between Collection and Collections
-> Collection: An interface used to store and manage a group of objects.
Collections: A utility class that provides methods to manipulate collections, such as sorting and searching.

Example: Collection → List, Set, Queue
Collections → sort(), reverse(), max(), min()

# Difference between Array and ArrayList
-> Array: Fixed-size collection that can store primitive types and objects.
ArrayList: Dynamic-size collection that stores objects only.

# Difference between Array and Collection
->An array has a fixed size, whereas a collection can grow or shrink dynamically.
An array can store both primitive data types and objects, while collections store objects.
Arrays provide basic operations, whereas collections provide many built-in methods for adding, removing, searching, and manipulating elements.

# Difference between ArrayList and LinkedList
ArrayList:
ArrayList is implemented using a dynamic array.
It is faster for accessing elements using an index.
It uses less memory compared to LinkedList.

LinkedList:
LinkedList is implemented using a doubly linked list.
It is generally better for insertion and deletion when the position/node is already known.
It uses more memory because each node stores references to the previous and next nodes.

# Difference between ArrayList and Vector
ArrayList:
ArrayList is a dynamic array.
It is not synchronized, so it is generally faster.
It is preferred when thread safety is not required.

Vector:
Vector is also a dynamic array.
Its methods are synchronized, so it is thread-safe.
It is generally slower than ArrayList because of synchronization.
Vector is a legacy class.

# Difference between Iterator and ListIterator
Iterator:
Can be used with all Collection types.
Traverses elements only in the forward direction.
Main methods: hasNext(), next(), remove().

ListIterator:
Can be used only with List implementations.
Can traverse elements in both forward and backward directions.
Can add and update elements.
Main methods: hasNext(), next(), hasPrevious(), previous(), add(), set()

# Difference between Comparable and Comparator
Comparable:
Provides compareTo() method to sort elements.
It provides single sorting sequences.
Located in java.lang.

Comparator:
Provides compare() method to sort elements.
It provides multiple sorting sequences.
Located in java.util.

# Difference between Set and Map
Set:

Set stores unique elements.
It does not store data in key-value pairs.
Example: HashSet<String>

Map:

Map stores data in key-value pairs.
Keys are unique, but values can be duplicated.
Example: HashMap<Integer, String>


# How many types of exceptions can occur in a Java program?
-> There are mainly two types of exceptions in Java: checked exceptions and unchecked exceptions.
Checked exceptions are checked by the compiler, so we must either handle them using try-catch or declare them using throws. For example, IOException and SQLException.
Unchecked exceptions occur at runtime and are subclasses of RuntimeException. For example, NullPointerException, ArithmeticException, and ArrayIndexOutOfBoundsException.

# Difference between Error and Exception
->The main difference is that an Error represents a serious problem in the JVM or system, which an application usually cannot recover from. For example, OutOfMemoryError and StackOverflowError.
An Exception represents a problem that occurs during program execution and can usually be handled by the application using try-catch or throws. For example, IOException and NullPointerException.

# Explain the hierarchy of Java Exception classes
->In Java, all exceptions and errors are derived from the Throwable class.
Throwable has two main subclasses: Error and Exception.
Error represents serious JVM or system-level problems, such as OutOfMemoryError and StackOverflowError.
Exception represents problems that can usually be handled by the application. It is further divided into checked exceptions and unchecked exceptions. Unchecked exceptions are subclasses of RuntimeException, such as NullPointerException and ArithmeticException.

#  Explain Runtime Exceptions.
->Runtime Exceptions are exceptions that occur during program execution and are not checked by the compiler. They usually result from programming mistakes or improper logic.

# What is NullPointerException?
->NullPointerException is an unchecked exception that occurs when we try to use an object reference that is null.
For example, if we call a method or access a variable using a null reference, Java throws NullPointerException.

# Difference between final, finally, and finalize()
->The final keyword is used to restrict changes. A final variable cannot be changed, a final method cannot be overridden, and a final class cannot be inherited.
finally is a block used with try-catch. It is generally used for cleanup code, and it executes whether an exception occurs or not.

finalize() was a method related to garbage collection. The JVM could call it before an object was garbage-collected, but it is deprecated and should not be used in modern Java.

# Difference between this() and super() in Java
->this() is used to call another constructor of the same class.
super() is used to call the constructor of the parent class.
For example, if a child class has multiple constructors, we can use this() to call another constructor in the same class. We use super() to initialize the parent class.
Both this() and super() must be the first statement inside a constructor.

# What is a Multithreaded Program?
->A multithreaded program is a program in which multiple threads execute concurrently within the same process.
Each thread can perform a different task, which helps improve responsiveness and performance.
For example, in a web application, one thread can handle a user request while other threads handle other requests.

# What is a thread?
->A thread is the smallest unit of execution within a process that allows tasks to run concurrently. It helps improve application performance by enabling multiple operations to execute at the same time.

# Describe the life cycle of the thread?
->New: The thread has been created but has not yet started.
Runnable: The thread is running, executing its task, or is ready to run if there are no other higher-priority threads.
Blocked: The thread is temporarily suspended, waiting for a resource or an event.
Waiting: The thread is waiting for another thread to perform a task.
Terminated: The thread has completed its task or been terminated by another thread.

# Explain sleep() method in Thread class
-> The sleep() method of the Thread class is used to pause the execution of the current thread for a specified amount of time.

# What is a Daemon Thread?
->A daemon thread is a background thread that provides services to other threads.
The JVM does not wait for daemon threads to finish. When all user threads have completed, the JVM terminates even if daemon threads are still running.

For example, garbage collection is performed by a daemon thread.
We can create one using setDaemon(true) before starting the thread.

# Difference between sleep() and wait()
->The main difference is that sleep() pauses the current thread for a specific period, while wait() makes a thread wait until another thread notifies it.
sleep() is a method of the Thread class, whereas wait() is a method of the Object class.

# What is the difference between an abstract class and a concrete class in Java?
-> An abstract class is a class declared with the abstract keyword. It can contain both abstract and concrete methods, and we cannot create its object directly. A concrete class is a normal class that provides implementations for its methods, and we can create its objects.



Why is Java not 100% object-oriented?
Why does Java not support pointers?
Why is Java pass-by-value?
Difference between primitive and reference types
Autoboxing and unboxing
static keyword
final vs static
const vs final — why doesn't Java use const?
instanceof operator
var in Java
Command-line arguments
Can we create an object of an abstract class?
13. Can an abstract class have a constructor?
14. Can an abstract class have zero abstract methods?
15. Can a constructor be overridden?
16. Can a constructor be inherited?
17. Can we overload a constructor?
18. Can we override a method with a different return type?
19. Covariant return type
20. Difference between composition and inheritance
21. Why doesn't Java support multiple inheritance with classes?
Why is String final?
23. How many objects are created by String s = new String("Java")?
24. Difference between String s = "Java" and new String("Java")
25. == vs .equals() with Strings
26. Why is String Pool useful?
How does HashMap work internally? ⭐
28. What happens when two keys have the same hashcode?
29. Why should we override equals() and hashCode() together? ⭐
30. Difference between HashMap, LinkedHashMap, and TreeMap
31. Why doesn't HashMap allow duplicate keys?
32. Difference between HashSet and HashMap
33. What is load factor in HashMap?
34. What is fail-fast vs fail-safe iterator?
35. Why is ConcurrentHashMap preferred in concurrent applications?
Can we have try without catch?
37. Can we have multiple catch blocks?
38. Can finally execute without catch?
39. Can we throw checked and unchecked exceptions?
40. How to create a custom exception?
41. Difference between throw and throws with example
Difference between process and thread
43. How can we create a thread in Java?
44. Thread vs Runnable
45. What is synchronization?
46. What is a race condition?
47. What is deadlock?
48. Difference between wait(), notify(), and notifyAll()
49. What is ExecutorService?
50. What is thread safety?
Why Java is pass-by-value
static keyword
Autoboxing/unboxing
String + String Pool
equals() and hashCode()
HashMap internal working
HashMap collision
HashSet internal working
Comparable vs Comparator
Exception hierarchy
Thread vs Runnable
Synchronization
Race condition
Deadlock
wait/notify/notifyAll
ExecutorService