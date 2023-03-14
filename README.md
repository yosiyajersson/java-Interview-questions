# Java 8 features.
## Lambda expressions:
	1.Java 8 introduces lambda expressions, which allow developers to write more concise and readable code. 
	2.Lambda expressions are anonymous functions that can be passed around like values and used to represent code blocks.
## Stream API:
	1.Java 8 also introduced the Stream API, which provides a functional programming-style approach to processing collections of data. 
	2.Streams can be used to filter, map, and reduce data, making it easier to work with large data sets.
## Date and Time API:
	1.Java 8 introduces a new Date and Time API, which provides a more comprehensive and flexible way to work with dates and times. 
	2.The new API includes classes such as LocalDate, LocalTime, and ZonedDateTime, which are designed to handle time zones and daylight saving time changes.
## Default methods:
	1.Java 8 introduces the concept of default methods, which allow interfaces to have concrete implementations for their methods. 
	2.This feature makes it easier to add new functionality to existing interfaces without breaking backward compatibility.
## Optional class:
	1.Java 8 introduces the Optional class, which is designed to handle null values in a more concise and safe way. 
	2.The Optional class provides a set of methods for checking whether a value is present, getting the value if it is present, or returning a default value if it is not present.
## Functional interfaces:
	1.Java 8 introduces the concept of functional interfaces, which are interfaces that have a single abstract method. 
	2.Functional interfaces can be used with lambda expressions to provide a more concise way to write code.
## Method references:
	1.Java 8 introduces method references, which provide a way to refer to methods or constructors without actually invoking them. 
	2.Method references can be used with lambda expressions to provide a more concise and readable syntax.
## Parallel arrays:
	1.Java 8 introduces parallel arrays, which are arrays that can be processed in parallel using the new Stream API. 
	2.Parallel arrays can provide a significant performance improvement when working with large data sets.
These are some of the key features of Java 8. Other enhancements include improved annotations, enhanced security, and better support for JavaScript and other scripting languages.

# what is meta space
	Meta space is a new memory space introduced in Java 8 as a replacement for the permanent generation (PermGen) space in earlier versions of Java. Meta space is used to store metadata about classes, methods, and other structures that are used by the Java Virtual Machine (JVM).

	The PermGen space in earlier versions of Java was known to cause problems due to its fixed size and the fact that it could become full if too many classes or other structures were loaded into memory. In contrast, meta space is designed to be more flexible and dynamic, allowing it to expand and contract as needed.

	Meta space is a part of the native heap, which means that it is managed by the operating system rather than the JVM. This allows the JVM to allocate and deallocate memory from the meta space more efficiently and with less overhead than was possible with the PermGen space.

	Meta space also includes a number of optimizations that are designed to improve performance and reduce memory usage. For example, the JVM can now share common class metadata across multiple instances of the same class, which reduces the amount of memory required to store this data.

	Overall, meta space is an important improvement in Java 8 that helps to address some of the memory management issues that were present in earlier versions of the JVM. By providing a more flexible and dynamic memory space for storing metadata, meta space helps to improve performance and reduce the risk of out-of-memory errors.

# what is voletile key word
	In Java, the volatile keyword is used as a modifier for variables to indicate that their values may be modified by multiple threads concurrently. When a variable is declared as volatile, it guarantees that any thread accessing the variable will see the most up-to-date value of the variable, even if it has been modified by another thread.

	This behavior is different from non-volatile variables, which may be cached by each thread, leading to the possibility that a thread may not see the most recent value of the variable.

	The volatile keyword is often used in multi-threaded programs to ensure that changes made to a shared variable by one thread are visible to all other threads. However, it is important to note that volatile only ensures visibility of changes, not atomicity. This means that if multiple threads are modifying a volatile variable concurrently, it is still possible for race conditions to occur, leading to unexpected behavior.

	It is also worth noting that while volatile variables are guaranteed to be visible to other threads, they may not be suitable for all multi-threaded scenarios. In some cases, more advanced synchronization mechanisms such as locks or atomic variables may be required to ensure thread safety and prevent race conditions.
	
# how to achive multiple inheritance in java?
	In Java, multiple inheritance is not supported directly. This means that a class cannot inherit from multiple classes at the same time. However, there are a few ways to achieve similar functionality:

	Interfaces: Java supports multiple inheritance of interfaces. An interface is like a contract that a class can implement, and a class can implement multiple interfaces at the same time. This allows for multiple inheritance of behavior, but not state.

	Default methods: Starting from Java 8, interfaces can have default methods. A default method provides a default implementation of a method in an interface. This allows an interface to provide some implementation while still allowing classes to implement it as usual. By using default methods, a class can inherit behavior from multiple interfaces.

	Composition: Instead of inheriting from multiple classes, a class can be composed of multiple objects. This means that the class has references to multiple objects of other classes, and can delegate behavior to those objects. This is known as the "composition over inheritance" principle, and can be a more flexible and extensible approach to code design.

	It's worth noting that while multiple inheritance can be useful in some situations, it can also lead to complex and brittle code. By using interfaces, default methods, and composition, it's often possible to achieve similar functionality while maintaining code simplicity and flexibility.
	
# What is optional In java
	Optional is a class introduced in Java 8 that provides a way to express the presence or absence of a value. It is intended to be used as a safer alternative to using null references, which can often lead to NullPointerException errors.

	An Optional instance can either be empty or contain a single non-null value. When an Optional instance contains a value, it is said to be "present", and when it does not contain a value, it is said to be "empty".

	Optional provides a number of methods for working with the contained value, including isPresent() to check if a value is present, orElse() to provide a default value if the Optional is empty, orElseGet() to lazily provide a default value using a Supplier, and map() and flatMap() to transform the contained value using functions.

	Using Optional can help to make code more robust and less prone to NullPointerException errors, since it forces the programmer to explicitly handle the case where a value may be absent. It also provides a more expressive way to communicate the presence or absence of a value, which can make code more self-documenting and easier to understand.

# what is functional Interface?
	In Java, a functional interface is an interface that has only one abstract method, called the "functional method". Functional interfaces are often used in conjunction with lambda expressions, which allow the functional method to be implemented inline without the need for a separate class definition.

	Functional interfaces are marked with the @FunctionalInterface annotation, which ensures that the interface has only one abstract method. This annotation is optional, but can help to make the intent of the interface clear to other developers.

	Examples of functional interfaces in Java include Runnable, Comparator, and Supplier. In each of these cases, there is only one abstract method that defines the core behavior of the interface.

	Functional interfaces are a key concept in functional programming, which emphasizes the use of functions as first-class citizens in programming. By using functional interfaces in Java, it is possible to write code that is more concise, expressive, and composable.

# what is default and static methods?
	In Java 8, default and static methods were introduced in interfaces to provide additional functionality without breaking existing implementations.

Default methods: A default method is a method defined in an interface with a default implementation. It can be overridden by implementing classes, but it does not need to be. The purpose of default methods is to provide a default behavior for an interface method that can be overridden by implementing classes if needed.
## Example:

public interface MyInterface {
   default void defaultMethod() {
      System.out.println("This is a default method.");
   }
}
Static methods: A static method is a method defined in an interface that can be called directly on the interface, without the need for an implementing class. Static methods in interfaces are similar to static methods in classes, but they cannot be overridden by implementing classes.
## Example:

public interface MyInterface {
   static void staticMethod() {
      System.out.println("This is a static method.");
   }
}
Default and static methods are useful for adding new features to existing interfaces without breaking existing code. They also provide a way to implement certain design patterns, such as the adapter pattern, more easily.

is it possible to override the method inside lamda expression?
	Lambda expressions in Java provide a concise way to represent a method as an instance of a functional interface, and they can be used to implement the functional method of a functional interface.

	However, a lambda expression is not a method that can be overridden. It is simply an instance of a functional interface that provides an implementation for its functional method.

	In other words, a lambda expression provides an implementation for a functional method, but it is not a method itself that can be overridden. When a lambda expression is used to implement a functional interface, the implementation cannot be changed or overridden in the same way that a traditional method can be overridden in a subclass.

	That being said, you can still override a method that is implemented using a lambda expression by providing a different implementation of the same functional interface. This can be done either by providing a new lambda expression with a different implementation of the functional method, or by implementing the interface with a traditional method in a subclass.

# what is runtime polimorpism and compile time polimorpism
	Polymorphism is a fundamental concept in object-oriented programming that allows objects of different classes to be treated as if they are objects of the same class. There are two types of polymorphism in Java: runtime polymorphism (also known as dynamic polymorphism) and compile-time polymorphism (also known as static polymorphism).

## Runtime Polymorphism: 
	Runtime polymorphism is achieved when a subclass of a class overrides a method that is already defined in its superclass. At runtime, the JVM determines which version of the method to call based on the type of the object that is being referred to, not the type of the reference variable.
## Example:

class Animal {
    void makeSound() {
        System.out.println("Animal is making a sound");
    }
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Dog is barking");
    }
}

Animal animal1 = new Animal();
Animal animal2 = new Dog();

animal1.makeSound(); // Output: "Animal is making a sound"
animal2.makeSound(); // Output: "Dog is barking"
In the above example, animal2 is a reference to a Dog object, but it is declared as an Animal reference. When makeSound() is called on animal2, the JVM knows to call the overridden version of makeSound() in the Dog class, not the original version in the Animal class.

## Compile-time Polymorphism: 
	Compile-time polymorphism is achieved through method overloading, which allows multiple methods with the same name but different parameters to be defined in the same class. The correct version of the method is determined at compile-time based on the number, types, and order of the arguments that are passed to the method.
## Example:

class Calculator {
    int add(int a, int b) {
        return a + b;
    }
    
    double add(double a, double b) {
        return a + b;
    }
}

Calculator calc = new Calculator();
int sum1 = calc.add(2, 3); // Calls int add(int a, int b)
double sum2 = calc.add(2.5, 3.7); // Calls double add(double a, double b)
In the above example, the add() method is overloaded with two versions that accept different types of arguments. The correct version of the method is determined at compile-time based on the types of the arguments that are passed to the method.

# what are the memories are there in java?

	In Java, there are several types of memory that are used for different purposes during the execution of a program. Here are some of the main types of memory used in Java:

## Stack Memory: 
	The stack is a special area of memory used to store method calls and local variables. When a method is called, a new frame is added to the top of the stack to store its local variables and parameters. When the method returns, the frame is removed from the stack.

## Heap Memory: 
	The heap is a region of memory used to store objects and arrays. Unlike stack memory, heap memory is not automatically freed when a method returns. Instead, objects and arrays remain in memory until they are no longer referenced by any part of the program, at which point they are eligible for garbage collection.

## Method Area (PermGen/Metaspace): 
	The method area is a region of memory used to store class-level data, such as the class definition, static fields, and method code. In Java 8 and earlier versions, this area was known as the Permanent Generation (PermGen). In Java 9 and later versions, it has been replaced by the Metaspace.

## Native Memory: 
	Native memory is used by the Java Virtual Machine (JVM) to store data that is not managed by the Java heap, such as JNI (Java Native Interface) code, memory-mapped files, and network sockets.

## Program Counter (PC) Register: 
	The program counter register is a small amount of memory used by the JVM to keep track of the current execution point of a thread.

These different types of memory are used for different purposes in Java and are managed by the JVM. Proper management of memory is important to avoid memory leaks, out-of-memory errors, and other performance issues in Java programs.

# how to get data from Optional
	In Java, Optional is a class that is used to represent a value that may or may not be present. If a value is present, you can use the get() method to retrieve it from the Optional object. However, it is generally recommended to avoid using the get() method, as it may throw a NoSuchElementException if the value is not present. Instead, you can use other methods provided by the Optional class to retrieve the value safely.

## Here are some ways to retrieve data from an Optional object:

### orElse() Method: 
	You can use the orElse() method to retrieve the value from the Optional object, or a default value if the value is not present. 
### For example:

Optional<Integer> optionalInt = Optional.of(10);
int result = optionalInt.orElse(0); // Returns 10

Optional<Integer> optionalNull = Optional.empty();
int result2 = optionalNull.orElse(0); // Returns 0

### orElseGet() Method: 
	Similar to orElse(), you can use the orElseGet() method to retrieve the value from the Optional object or a default value, but you can provide a Supplier as an argument to generate the default value only if the value is not present. 
### For example:

Optional<Integer> optionalNull = Optional.empty();
int result = optionalNull.orElseGet(() -> {
    // Generate a default value
    return 0;
}); // Returns 0
orElseThrow() Method: You can use the orElseThrow() method to retrieve the value from the Optional object or throw an exception if the value is not present. For example:

Optional<Integer> optionalNull = Optional.empty();
int result = optionalNull.orElseThrow(() -> new RuntimeException("Value not present"));
ifPresent() Method: You can use the ifPresent() method to perform an action if the value is present in the Optional object. For example:

Optional<Integer> optionalInt = Optional.of(10);
optionalInt.ifPresent(value -> {
    // Perform an action with the value
    System.out.println("Value is present: " + value);
});
By using these methods, you can safely retrieve data from an Optional object in Java.

# What are the collections you know?
	In Java, there are several types of collections that are used to store and manipulate groups of objects. Here are the main types of collections in Java:

List: A List is an ordered collection of elements that can contain duplicates. It is implemented by several classes, including ArrayList, LinkedList, and Vector.

Set: A Set is an unordered collection of elements that does not allow duplicates. It is implemented by several classes, including HashSet, LinkedHashSet, and TreeSet.

Map: A Map is a collection of key-value pairs, where each key is unique and maps to a corresponding value. It is implemented by several classes, including HashMap, LinkedHashMap, and TreeMap.

Queue: A Queue is a collection that allows you to add elements at one end and remove them from the other end. It is implemented by several classes, including LinkedList, ArrayDeque, and PriorityQueue.

Deque: A Deque (short for double-ended queue) is a collection that allows you to add and remove elements from both ends. It is implemented by several classes, including LinkedList and ArrayDeque.

Stack: A Stack is a collection that follows the Last-In-First-Out (LIFO) order, meaning that the last element added is the first one to be removed. It is implemented by the Stack class.

Vector: A Vector is a synchronized version of the ArrayList class, meaning that it is thread-safe but may have lower performance than other collection classes.

Each collection type has its own characteristics, strengths, and weaknesses, and choosing the right collection type for a particular task is an important aspect of programming in Java.

# what is the difference between set and list
	In Java, both Set and List are interfaces used to store collections of objects, but they have some fundamental differences:

	Order: A List is an ordered collection of elements, meaning that the elements are stored in a specific sequence and each element has a unique index position. In contrast, a Set is an unordered collection of elements, meaning that the elements are not stored in any particular sequence.

	Duplicates: A List allows duplicates, meaning that you can store the same element multiple times in the list. A Set, on the other hand, does not allow duplicates, meaning that each element can only appear once in the set.

	Accessing Elements: In a List, you can access elements by their index position using the get(int index) method. In a Set, you cannot access elements by their index position, but you can check if an element is present in the Set using the contains(Object o) method.

	Iteration: In a List, you can iterate over the elements in the list using the Iterator or foreach loop, and the elements will be returned in the order in which they were added to the list. In a Set, the iteration order is undefined and may vary between implementations.

	Performance: In general, List operations that involve adding, removing, or accessing elements by index position are faster than Set operations. However, Set operations that involve checking for the presence of an element are faster than List operations.

	In summary, the main difference between Set and List in Java is that a List is an ordered collection that allows duplicates and provides index-based access to its elements, while a Set is an unordered collection that does not allow duplicates and provides faster element lookups.
