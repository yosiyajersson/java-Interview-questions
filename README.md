# 1.Java 8 features ?
### Lambda expressions: 
Java 8 introduces lambda expressions, which allow developers to write more concise and readable code. Lambda expressions are anonymous functions that can be passed around like values and used to represent code blocks.

### Stream API: 
Java 8 also introduced the Stream API, which provides a functional programming-style approach to processing collections of data. Streams can be used to filter, map, and reduce data, making it easier to work with large data sets.

### Date and Time API: 
Java 8 introduces a new Date and Time API, which provides a more comprehensive and flexible way to work with dates and times. The new API includes classes such as LocalDate, LocalTime, and ZonedDateTime, which are designed to handle time zones and daylight saving time changes.

### Default methods: 
Java 8 introduces the concept of default methods, which allow interfaces to have concrete implementations for their methods. This feature makes it easier to add new functionality to existing interfaces without breaking backward compatibility.

### Optional class: 
Java 8 introduces the Optional class, which is designed to handle null values in a more concise and safe way. The Optional class provides a set of methods for checking whether a value is present, getting the value if it is present, or returning a default value if it is not present.

### Functional interfaces: 
Java 8 introduces the concept of functional interfaces, which are interfaces that have a single abstract method. Functional interfaces can be used with lambda expressions to provide a more concise way to write code.

### Method references: 
Java 8 introduces method references, which provide a way to refer to methods or constructors without actually invoking them. Method references can be used with lambda expressions to provide a more concise and readable syntax.

### Parallel arrays: 
Java 8 introduces parallel arrays, which are arrays that can be processed in parallel using the new Stream API. Parallel arrays can provide a significant performance improvement when working with large data sets.

These are some of the key features of Java 8. Other enhancements include improved annotations, enhanced security, and better support for JavaScript and other scripting languages.

# 2.what is meta space ?
Meta space is a new memory space introduced in Java 8 as a replacement for the permanent generation (PermGen) space in earlier versions of Java. Meta space is used to store metadata about classes, methods, and other structures that are used by the Java Virtual Machine (JVM).

The PermGen space in earlier versions of Java was known to cause problems due to its fixed size and the fact that it could become full if too many classes or other structures were loaded into memory. In contrast, meta space is designed to be more flexible and dynamic, allowing it to expand and contract as needed.

Meta space is a part of the native heap, which means that it is managed by the operating system rather than the JVM. This allows the JVM to allocate and deallocate memory from the meta space more efficiently and with less overhead than was possible with the PermGen space.

Meta space also includes a number of optimizations that are designed to improve performance and reduce memory usage. For example, the JVM can now share common class metadata across multiple instances of the same class, which reduces the amount of memory required to store this data.

Overall, meta space is an important improvement in Java 8 that helps to address some of the memory management issues that were present in earlier versions of the JVM. By providing a more flexible and dynamic memory space for storing metadata, meta space helps to improve performance and reduce the risk of out-of-memory errors.

# 3.what is volatile key word?
In Java, the volatile keyword is used as a modifier for variables to indicate that their values may be modified by multiple threads concurrently. When a variable is declared as volatile, it guarantees that any thread accessing the variable will see the most up-to-date value of the variable, even if it has been modified by another thread.

This behavior is different from non-volatile variables, which may be cached by each thread, leading to the possibility that a thread may not see the most recent value of the variable.

The volatile keyword is often used in multi-threaded programs to ensure that changes made to a shared variable by one thread are visible to all other threads. However, it is important to note that volatile only ensures visibility of changes, not atomicity. This means that if multiple threads are modifying a volatile variable concurrently, it is still possible for race conditions to occur, leading to unexpected behavior.

It is also worth noting that while volatile variables are guaranteed to be visible to other threads, they may not be suitable for all multi-threaded scenarios. In some cases, more advanced synchronization mechanisms such as locks or atomic variables may be required to ensure thread safety and prevent race conditions.
	
# 4.how to achive multiple inheritance in java?
In Java, multiple inheritance is not supported directly. This means that a class cannot inherit from multiple classes at the same time. However, there are a few ways to achieve similar functionality:

### Interfaces: 
Java supports multiple inheritance of interfaces. An interface is like a contract that a class can implement, and a class can implement multiple interfaces at the same time. This allows for multiple inheritance of behavior, but not state.

### Default methods: 
Starting from Java 8, interfaces can have default methods. A default method provides a default implementation of a method in an interface. This allows an interface to provide some implementation while still allowing classes to implement it as usual. By using default methods, a class can inherit behavior from multiple interfaces.

### Composition: 
Instead of inheriting from multiple classes, a class can be composed of multiple objects. This means that the class has references to multiple objects of other classes, and can delegate behavior to those objects. This is known as the "composition over inheritance" principle, and can be a more flexible and extensible approach to code design.

It's worth noting that while multiple inheritance can be useful in some situations, it can also lead to complex and brittle code. By using interfaces, default methods, and composition, it's often possible to achieve similar functionality while maintaining code simplicity and flexibility.
	
# 5.What is Optional In java?
Optional is a class introduced in Java 8 that provides a way to express the presence or absence of a value. It is intended to be used as a safer alternative to using null references, which can often lead to NullPointerException errors.

An Optional instance can either be empty or contain a single non-null value. When an Optional instance contains a value, it is said to be "present", and when it does not contain a value, it is said to be "empty".

Optional provides a number of methods for working with the contained value, including isPresent() to check if a value is present, orElse() to provide a default value if the Optional is empty, orElseGet() to lazily provide a default value using a Supplier, and map() and flatMap() to transform the contained value using functions.

Using Optional can help to make code more robust and less prone to NullPointerException errors, since it forces the programmer to explicitly handle the case where a value may be absent. It also provides a more expressive way to communicate the presence or absence of a value, which can make code more self-documenting and easier to understand.

# 6.what is functional Interface?
In Java, a functional interface is an interface that has only one abstract method, called the "functional method". Functional interfaces are often used in conjunction with lambda expressions, which allow the functional method to be implemented inline without the need for a separate class definition.

Functional interfaces are marked with the @FunctionalInterface annotation, which ensures that the interface has only one abstract method. This annotation is optional, but can help to make the intent of the interface clear to other developers.

Examples of functional interfaces in Java include Runnable, Comparator, and Supplier. In each of these cases, there is only one abstract method that defines the core behavior of the interface.

Functional interfaces are a key concept in functional programming, which emphasizes the use of functions as first-class citizens in programming. By using functional interfaces in Java, it is possible to write code that is more concise, expressive, and composable.

# 7.what is default and static methods?
In Java 8, default and static methods were introduced in interfaces to provide additional functionality without breaking existing implementations.

### Default methods: 
A default method is a method defined in an interface with a default implementation. It can be overridden by implementing classes, but it does not need to be. The purpose of default methods is to provide a default behavior for an interface method that can be overridden by implementing classes if needed.
### Example:

		public interface MyInterface {
		   default void defaultMethod() {
		      System.out.println("This is a default method.");
		   }
		}
### Static methods: 
A static method is a method defined in an interface that can be called directly on the interface, without the need for an implementing class. Static methods in interfaces are similar to static methods in classes, but they cannot be overridden by implementing classes.
### Example:
		public interface MyInterface {
		   static void staticMethod() {
		      System.out.println("This is a static method.");
		   }
		}
Default and static methods are useful for adding new features to existing interfaces without breaking existing code. They also provide a way to implement certain design patterns, such as the adapter pattern, more easily.

# 8.is it possible to override the method inside lamda expression?
Lambda expressions in Java provide a concise way to represent a method as an instance of a functional interface, and they can be used to implement the functional method of a functional interface.

However, a lambda expression is not a method that can be overridden. It is simply an instance of a functional interface that provides an implementation for its functional method.

In other words, a lambda expression provides an implementation for a functional method, but it is not a method itself that can be overridden. When a lambda expression is used to implement a functional interface, the implementation cannot be changed or overridden in the same way that a traditional method can be overridden in a subclass.

That being said, you can still override a method that is implemented using a lambda expression by providing a different implementation of the same functional interface. This can be done either by providing a new lambda expression with a different implementation of the functional method, or by implementing the interface with a traditional method in a subclass.

# 9.what is runtime polimorpism and compile time polimorpism
Polymorphism is a fundamental concept in object-oriented programming that allows objects of different classes to be treated as if they are objects of the same class. There are two types of polymorphism in Java: runtime polymorphism (also known as dynamic polymorphism) and compile-time polymorphism (also known as static polymorphism).

### Runtime Polymorphism: 
Runtime polymorphism is achieved when a subclass of a class overrides a method that is already defined in its superclass. At runtime, the JVM determines which version of the method to call based on the type of the object that is being referred to, not the type of the reference variable.
### Example:

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

# 10.what are the memories are there in java?

In Java, there are several types of memory that are used for different purposes during the execution of a program. Here are some of the main types of memory used in Java:

### Stack Memory: 
The stack is a special area of memory used to store method calls and local variables. When a method is called, a new frame is added to the top of the stack to store its local variables and parameters. When the method returns, the frame is removed from the stack.

### Heap Memory: 
The heap is a region of memory used to store objects and arrays. Unlike stack memory, heap memory is not automatically freed when a method returns. Instead, objects and arrays remain in memory until they are no longer referenced by any part of the program, at which point they are eligible for garbage collection.

### Method Area (PermGen/Metaspace): 
The method area is a region of memory used to store class-level data, such as the class definition, static fields, and method code. In Java 8 and earlier versions, this area was known as the Permanent Generation (PermGen). In Java 9 and later versions, it has been replaced by the Metaspace.

### Native Memory: 
Native memory is used by the Java Virtual Machine (JVM) to store data that is not managed by the Java heap, such as JNI (Java Native Interface) code, memory-mapped files, and network sockets.

### Program Counter (PC) Register: 
The program counter register is a small amount of memory used by the JVM to keep track of the current execution point of a thread.

These different types of memory are used for different purposes in Java and are managed by the JVM. Proper management of memory is important to avoid memory leaks, out-of-memory errors, and other performance issues in Java programs.

# 11.how to get data from Optional?
In Java, Optional is a class that is used to represent a value that may or may not be present. If a value is present, you can use the get() method to retrieve it from the Optional object. However, it is generally recommended to avoid using the get() method, as it may throw a NoSuchElementException if the value is not present. Instead, you can use other methods provided by the Optional class to retrieve the value safely.

### Here are some ways to retrieve data from an Optional object:

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
		
### orElseThrow() Method: 
You can use the orElseThrow() method to retrieve the value from the Optional object or throw an exception if the value is not present. 

### For example:
		Optional<Integer> optionalNull = Optional.empty();
		int result = optionalNull.orElseThrow(() -> new RuntimeException("Value not present"));
		
### ifPresent() Method:
You can use the ifPresent() method to perform an action if the value is present in the Optional object. 
### For example:

		Optional<Integer> optionalInt = Optional.of(10);
		optionalInt.ifPresent(value -> {
		    // Perform an action with the value
		    System.out.println("Value is present: " + value);
		});
		
By using these methods, you can safely retrieve data from an Optional object in Java.

# 12.What are the collections you know?
In Java, there are several types of collections that are used to store and manipulate groups of objects. Here are the main types of collections in Java:

### List: 
A List is an ordered collection of elements that can contain duplicates. It is implemented by several classes, including ArrayList, LinkedList, and Vector.

### Set: 
A Set is an unordered collection of elements that does not allow duplicates. It is implemented by several classes, including HashSet, LinkedHashSet, and TreeSet.

### Map: 
A Map is a collection of key-value pairs, where each key is unique and maps to a corresponding value. It is implemented by several classes, including HashMap, LinkedHashMap, and TreeMap.

### Queue: 
A Queue is a collection that allows you to add elements at one end and remove them from the other end. It is implemented by several classes, including LinkedList, ArrayDeque, and PriorityQueue.

### Deque: 
A Deque (short for double-ended queue) is a collection that allows you to add and remove elements from both ends. It is implemented by several classes, including LinkedList and ArrayDeque.

### Stack: 
A Stack is a collection that follows the Last-In-First-Out (LIFO) order, meaning that the last element added is the first one to be removed. It is implemented by the Stack class.

### Vector: 
A Vector is a synchronized version of the ArrayList class, meaning that it is thread-safe but may have lower performance than other collection classes.

Each collection type has its own characteristics, strengths, and weaknesses, and choosing the right collection type for a particular task is an important aspect of programming in Java.

# 13.what is the difference between set and list
In Java, both Set and List are interfaces used to store collections of objects, but they have some fundamental differences:

### Order: 
A List is an ordered collection of elements, meaning that the elements are stored in a specific sequence and each element has a unique index position. In contrast, a Set is an unordered collection of elements, meaning that the elements are not stored in any particular sequence.

### Duplicates: 
A List allows duplicates, meaning that you can store the same element multiple times in the list. A Set, on the other hand, does not allow duplicates, meaning that each element can only appear once in the set.

### Accessing Elements: 
In a List, you can access elements by their index position using the get(int index) method. In a Set, you cannot access elements by their index position, but you can check if an element is present in the Set using the contains(Object o) method.

### Iteration: 
In a List, you can iterate over the elements in the list using the Iterator or foreach loop, and the elements will be returned in the order in which they were added to the list. In a Set, the iteration order is undefined and may vary between implementations.

### Performance: 
In general, List operations that involve adding, removing, or accessing elements by index position are faster than Set operations. However, Set operations that involve checking for the presence of an element are faster than List operations.

In summary, the main difference between Set and List in Java is that a List is an ordered collection that allows duplicates and provides index-based access to its elements, while a Set is an unordered collection that does not allow duplicates and provides faster element lookups.

# 14.what is singleton class

In Java, a Singleton class is a class that can have only one instance (object) at a time, and provides a global point of access to that instance. This is typically achieved by making the constructor of the class private, and providing a static method that returns the instance of the class.

The Singleton design pattern is used when you want to ensure that a class has only one instance and that it can be accessed easily by other classes throughout the application. Examples of singleton classes in Java include logging classes, configuration classes, and database connection classes.

Here is an example of a Singleton class in Java:

		public class Singleton {

		    private static Singleton instance;

		    private Singleton() {
			// Private constructor to prevent external instantiation
		    }

		    public static Singleton getInstance() {
			if (instance == null) {
			    instance = new Singleton();
			}
			return instance;
		    }

		    // Other methods and fields can be added here
		}

In this example, the Singleton class has a private constructor and a static getInstance() method that returns the instance of the class. The instance variable is static, so it is shared by all instances of the class. The getInstance() method checks if the instance has been created, and if not, creates a new instance and returns it. This ensures that only one instance of the class exists at any given time.

# 15.how to restrict the object creation if the object is exist ?

You can restrict the creation of multiple objects for a class using the Singleton design pattern in Java. The basic idea behind this pattern is to have a private constructor that prevents external instantiation of the class, and a static method that provides a global point of access to the single instance of the class.

Here is an example implementation of the Singleton pattern that restricts the creation of multiple objects for a class:

		public class MyClass {
		    private static MyClass instance;

		    // private constructor
		    private MyClass() {}

		    // static method to get the single instance of the class
		    public static MyClass getInstance() {
			if (instance == null) {
			    instance = new MyClass();
			}
			return instance;
		    }
		}
		
In this example, the class MyClass has a private constructor that prevents external instantiation, and a static method getInstance() that returns the single instance of the class. The instance variable is static, so it is shared by all instances of the class. The getInstance() method checks if the instance has been created, and if not, creates a new instance and returns it. This ensures that only one instance of the class exists at any given time, and subsequent calls to getInstance() will return the same instance.

# 16.what will happen when tried to extend the one functional interface into another functional interface?

In Java, when you try to extend one functional interface into another functional interface, the resulting interface is also a functional interface as long as it has only one abstract method. This is because the functional interface concept is based on the presence of a single abstract method, called the functional method, and the resulting interface also has only one abstract method.

Here is an example of extending one functional interface into another:

		@FunctionalInterface
		interface MyFunctionalInterface {
		    void doSomething();
		}

		@FunctionalInterface
		interface MyDerivedFunctionalInterface extends MyFunctionalInterface {
		    void doSomethingElse();
		}

In this example, MyFunctionalInterface is a functional interface with one abstract method doSomething(). MyDerivedFunctionalInterface extends MyFunctionalInterface and adds another abstract method doSomethingElse(). Since MyDerivedFunctionalInterface still has only one abstract method doSomethingElse(), it is also a functional interface.

However, it is worth noting that while it is possible to extend one functional interface into another, it may not always be the best design choice. The goal of functional interfaces is to provide a single abstract method for functional programming, so adding additional methods may not be consistent with the original intent of the interface.

# 17. how to create custom exception?
In Java, you can create custom exceptions by creating a class that extends the Exception class or one of its subclasses such as RuntimeException, IOException, SQLException, etc.

Here's an example of how to create a custom exception:

		public class CustomException extends Exception {
		    public CustomException(String message) {
			super(message);
		    }
		}

In this example, the CustomException class extends the Exception class and has a constructor that takes a String argument to specify the exception message.

To use this custom exception, you can throw it in your code using the throw keyword:

		public void someMethod() throws CustomException {
		    // some code
		    if (someCondition) {
			throw new CustomException("Error message");
		    }
		    // some more code
		}

In this example, the someMethod() method throws the CustomException if a certain condition is met. When the exception is thrown, it will display the error message passed to its constructor.

You can also catch and handle this custom exception like any other exception:

		try {
		    someMethod();
		} catch (CustomException e) {
		    // handle the exception
		}
In this example, the someMethod() method is called in a try-catch block, and any CustomException that is thrown will be caught and handled in the catch block.

# 18.types of exception?

In Java, there are two main types of exceptions: checked exceptions and unchecked exceptions.

Checked Exceptions: These are exceptions that must be declared in the method signature using the throws keyword, or handled using a try-catch block. Checked exceptions are checked at compile time to ensure that they are either declared in the method signature or caught in a try-catch block. Some examples of checked exceptions include IOException, SQLException, and ClassNotFoundException.

Unchecked Exceptions: These are exceptions that do not need to be declared in the method signature or caught in a try-catch block. Unchecked exceptions are also known as runtime exceptions, and they occur at runtime when the program encounters an unexpected situation, such as a division by zero, a null pointer dereference, or an array index out of bounds. Some examples of unchecked exceptions include ArithmeticException, NullPointerException, and ArrayIndexOutOfBoundsException.

There is also a third type of exception called Error, which is similar to unchecked exceptions in that they don't need to be declared or caught, but they are used to indicate serious problems that cannot be handled at runtime. Examples of Error include OutOfMemoryError and StackOverflowError.

It's important to handle exceptions properly in your code to ensure that your program can recover from errors and avoid unexpected crashes.

# 19. is it possible to write multiple catch block for single try block?

Yes, it is possible to write multiple catch blocks for a single try block in Java.

When you have a try block that can throw multiple types of exceptions, you can use multiple catch blocks to handle each type of exception separately. Here's an example:

		try {
		    // some code that may throw exceptions
		} catch (IOException e) {
		    // handle IOException
		} catch (SQLException e) {
		    // handle SQLException
		} catch (Exception e) {
		    // handle any other exceptions
		}

In this example, there are three catch blocks: one for IOException, one for SQLException, and one for any other types of exceptions that might be thrown.

The catch blocks are executed in order, so if the first catch block handles the exception, the subsequent catch blocks will be skipped. If no catch block matches the thrown exception, the exception will propagate up the call stack until it is caught by a matching catch block or until it causes the program to terminate.

Note that catch blocks should be ordered from most specific to least specific, since catch blocks are executed in order and a more general catch block that handles a superclass of the exception may catch the exception before a more specific catch block that handles a subclass of the exception.

# 20. what is the order of catching exceptions?

When you have multiple catch blocks for a single try block, the order in which the catch blocks are defined matters. The catch blocks are executed in the order they are defined, and the first catch block that matches the thrown exception will be executed.

If an exception is caught by a catch block, the subsequent catch blocks will be skipped, even if they could handle the exception. Therefore, it's important to order the catch blocks from most specific to least specific, with the catch block for the most specific exception type defined first.

For example, consider the following code:

		try {
		    // some code that may throw exceptions
		} catch (IOException e) {
		    // handle IOException
		} catch (Exception e) {
		    // handle any other exceptions
		}

In this example, the catch block for IOException is defined first, followed by the catch block for Exception. If an IOException is thrown, it will be caught by the first catch block and the second catch block will be skipped. If an exception other than an IOException is thrown, it will be caught by the second catch block.

If the catch blocks were reversed, with the catch block for Exception defined first, it would catch all exceptions, including IOException, and the catch block for IOException would be skipped. This could lead to unintended behavior if you have different error-handling logic for different types of exceptions.

# 21.why string is immutable?

String is immutable in Java for a few reasons:

Performance: Immutable objects are more efficient to work with than mutable objects because they can be cached and shared among multiple threads without the risk of data corruption. Since strings are widely used in Java programs, making them immutable reduces the overhead of creating and destroying new string objects.

Security: Strings are widely used in Java programs to store sensitive information like passwords and credit card numbers. By making strings immutable, Java ensures that the values of these sensitive strings cannot be modified by external code, which can help prevent security vulnerabilities like buffer overflows and injection attacks.

Thread safety: Since strings are used so frequently in Java programs, it's important that they be thread-safe. By making strings immutable, Java ensures that multiple threads can safely access the same string object without the risk of data corruption.

Caching: Because strings are immutable, Java can cache them for reuse. This can help improve performance by reducing the number of objects that need to be created and destroyed.

Overall, making strings immutable is a design decision that balances performance, security, and thread safety considerations, and it has proven to be a valuable feature of the Java language.

# 22. if string value is changeable what will happen?

In Java, strings are immutable, which means that their values cannot be changed once they are created. If you try to change the value of a string, a new string object will be created with the new value, and the original string object will remain unchanged.

For example, consider the following code:

		String str = "Hello";
		str = "World";

In this code, the variable str is first assigned the value "Hello". However, when the second line executes, the value of str is changed to "World". But what really happens is that a new string object with the value "World" is created, and the variable str is updated to refer to the new object. The original string object with the value "Hello" remains unchanged.

This is different from mutable objects like arrays or collections, where you can modify the contents of the object without creating a new object. If strings were mutable, it would lead to unpredictable behavior and make it difficult to reason about the state of a program.

# 23. Internal working of hashmap ?

HashMap is a widely used data structure in Java, and it is implemented as an array of buckets, where each bucket is a linked list of key-value pairs. Here are the internal workings of HashMap:

Hashing: When you put a key-value pair into a HashMap, the key is hashed using the hashCode() method to get an index into the array of buckets. The hashCode() method returns an integer value that is used to identify the bucket that will contain the key-value pair.

Collision resolution: Since multiple keys may hash to the same index, there may be collisions where multiple key-value pairs end up in the same bucket. To handle this, HashMap uses a linked list to store the key-value pairs in each bucket. If two keys hash to the same index, their key-value pairs are added to the same linked list.

Retrieving values: When you retrieve a value from a HashMap using a key, the key is first hashed to find the index of the bucket that contains the key-value pairs. Then, the linked list in that bucket is searched to find the key-value pair with the matching key. If the key is not found in the linked list, then the value associated with the key is considered to be null.

Resizing: As more key-value pairs are added to a HashMap, the number of buckets may need to be increased to avoid having too many collisions. When the number of key-value pairs in a HashMap exceeds a certain threshold, the HashMap is resized by creating a new array of buckets with a larger size, and rehashing all of the key-value pairs into the new array.

Overall, HashMap provides fast key-value lookups by using an efficient hashing algorithm and handling collisions with linked lists. However, its performance can degrade if the number of collisions becomes too high, which can be mitigated by tuning the size of the HashMap and choosing appropriate hash functions.

# 24.what is the enhancement of hashmap in java 8 ?

Java 8 introduced several enhancements to the HashMap class, including:

Performance improvements: In Java 8, the hash function used by HashMap has been improved to reduce the likelihood of collisions, leading to better performance in many cases.

Default methods for the Map interface: Java 8 introduced several default methods for the Map interface, which HashMap implements. These methods include forEach(), which allows you to iterate over the key-value pairs in a HashMap using a lambda expression, and computeIfAbsent(), which allows you to compute a value for a given key if it is not already present in the HashMap.

Streams API: With the introduction of the Streams API in Java 8, you can use streams to manipulate HashMaps in various ways. For example, you can use streams to filter the key-value pairs in a HashMap based on some criteria, or to transform the values in a HashMap using a lambda expression.

Null keys and values: In previous versions of Java, HashMap did not allow null keys or values. However, in Java 8, you can add null keys and values to a HashMap, although you still need to be careful when working with nulls to avoid NullPointerExceptions.

Overall, the enhancements to HashMap in Java 8 provide more efficient and flexible ways to work with key-value pairs in a Map, and make it easier to write clean and concise code using lambda expressions and the Streams API.

# 25. what is stream ?

A stream in Java is a sequence of objects that can be processed in parallel or sequentially. Streams are a new feature introduced in Java 8 and are a powerful tool for processing collections of data.

Here are some key points to know about streams:

Streams are not data structures. Instead, they are a way of processing data.

Streams can be created from collections, arrays, I/O channels, and other sources.

Streams can be processed in parallel or sequentially.

Stream operations can be intermediate or terminal. Intermediate operations, such as filter() or map(), return a new stream that can be further processed. Terminal operations, such as forEach() or reduce(), produce a result or a side-effect.

Stream operations can be pipelined, meaning that multiple operations can be combined into a single pipeline.

Streams are designed to be lazy, meaning that they only process the elements in the stream that are needed to produce the desired output.

Streams provide a concise and expressive way of working with collections in Java, and can be especially useful when processing large amounts of data or when working with distributed computing frameworks

# 26. what is intermediate and terminal operations in stream ?

In Java 8 streams, there are two types of operations: intermediate and terminal.

### Intermediate Operations:
Intermediate operations are operations that can be called on a stream and return another stream as the result. Intermediate operations include operations such as filter(), map(), distinct(), sorted(), peek(), and many others. These operations do not produce any final result and can be chained together to form a pipeline.

### Terminal Operations:
Terminal operations are operations that produce a result or a side-effect, such as forEach(), reduce(), collect(), count(), and others. When a terminal operation is invoked on a stream, it processes the elements of the stream and produces a final result. After a terminal operation has been invoked, the stream cannot be used again.

It's important to note that intermediate operations are lazy, which means that they don't actually execute the operations on the stream until a terminal operation is called. This allows for more efficient processing of large datasets, as the intermediate operations can be optimized and executed in parallel.

Overall, the combination of intermediate and terminal operations in Java 8 streams allows for a powerful and expressive way of processing collections of data.

# 27. how do you filter employee data whose age >25 using streams?

Assuming that you have a collection of Employee objects and each Employee object has an 'age' field, you can filter the employee data whose age is greater than 25 using streams in Java 8 as follows:

		List<Employee> employeeList = ... // assume the collection of Employee objects

		List<Employee> filteredList = employeeList.stream()
							   .filter(e -> e.getAge() > 25)
							   .collect(Collectors.toList());
							   
In the above example, we first convert the collection of Employee objects to a stream using the stream() method. Then we use the filter() method to filter out the Employee objects whose age is less than or equal to 25. Finally, we collect the filtered Employee objects back into a list using the collect() method.

Note that the filter() method takes a lambda expression as an argument, which is used to specify the filtering condition. In this case, we are using the getAge() method to access the age field of each Employee object and filtering the ones whose age is greater than 25.

# 28. how to remove object from list?

To remove an object from a list in Java, you can use the remove() method of the List interface. The remove() method removes the first occurrence of the specified object from the list, if it exists. Here's an example:

		List<String> list = new ArrayList<>();
		list.add("apple");
		list.add("banana");
		list.add("orange");

		// remove "banana" from the list
		list.remove("banana");

		// print the updated list
		System.out.println(list); // Output: [apple, orange]

In the above example, we first create a new ArrayList object and add some elements to it. Then we call the remove() method to remove the element "banana" from the list. Finally, we print the updated list using the println() method.

Note that if the specified object is not present in the list, the remove() method does not do anything and returns false. If you want to remove an object at a specific index in the list, you can use the remove(int index) method, which removes the object at the specified index.

# 29. what will happen when the iteration and removing happening at the same time in the list?

If you try to iterate over a list and remove elements from it at the same time, you may get a ConcurrentModificationException. This exception occurs when the structure of the list is modified while it is being iterated over.

For example, consider the following code:

		List<String> list = new ArrayList<>();
		list.add("apple");
		list.add("banana");
		list.add("orange");

		for (String s : list) {
		    if (s.equals("banana")) {
			list.remove(s);
		    }
		}

In the above code, we are trying to remove the element "banana" from the list while iterating over it using a for-each loop. This will result in a ConcurrentModificationException.

To avoid this exception, you can use an iterator to remove elements from the list while iterating over it. The Iterator interface provides a remove() method that allows you to remove the current element from the list. Here's an example:

		List<String> list = new ArrayList<>();
		list.add("apple");
		list.add("banana");
		list.add("orange");

		Iterator<String> iterator = list.iterator();
		while (iterator.hasNext()) {
		    String s = iterator.next();
		    if (s.equals("banana")) {
			iterator.remove();
		    }
		}
		
In the above code, we are using an iterator to iterate over the list and remove the element "banana" from it. The remove() method of the iterator removes the current element from the list without throwing a ConcurrentModificationException.

# 30. does set maintain the order of insertion?

The HashSet implementation of the Set interface in Java does not maintain the order of insertion of elements. The elements in a HashSet are stored in an unordered manner, based on their hash code values. This means that the order in which the elements were added to the set may not be the same as the order in which they are returned by an iterator or retrieved using a for-each loop.

However, there are other implementations of the Set interface in Java, such as LinkedHashSet and TreeSet, which do maintain the order of insertion of elements.

LinkedHashSet: This implementation of Set extends HashSet and maintains a doubly-linked list of the elements in the order in which they were added to the set. This means that the order of iteration over a LinkedHashSet is the same as the order in which the elements were added to the set.

TreeSet: This implementation of Set stores its elements in a sorted order, based on their natural ordering or a custom Comparator. The order of iteration over a TreeSet is the order defined by the sorting criteria.

So, if you need to maintain the order of insertion of elements in a Set, you can use LinkedHashSet. If you need to maintain a sorted order of elements, you can use TreeSet.

# 31. what is concurrent hashmap ?

ConcurrentHashMap is a thread-safe implementation of the Map interface in Java that allows concurrent access to its elements without the need for explicit synchronization. It is designed to be highly scalable and efficient in a multi-threaded environment.

ConcurrentHashMap achieves this by dividing the map into several segments, each of which can be locked independently. This allows multiple threads to access different segments of the map concurrently, without the need for them to wait for each other. This improves the concurrency and performance of the map in highly concurrent applications.

Additionally, ConcurrentHashMap provides several atomic operations, such as putIfAbsent, replace, and remove, which allow multiple threads to update the map concurrently, without the need for explicit synchronization.

ConcurrentHashMap was introduced in Java 5 as a replacement for the synchronized Hashtable and Collections.synchronizedMap() implementations, which were not designed for high concurrency scenarios. It is recommended to use ConcurrentHashMap instead of synchronized maps in highly concurrent applications to achieve better scalability and performance.

# 32. what is join in thread?

In Java, the join() method is used to wait for a thread to complete its execution before the current thread continues.

When a thread invokes the join() method on another thread, the current thread is suspended and waits for the other thread to finish its execution. The join() method blocks the current thread until the specified thread completes, either by finishing its execution normally or by throwing an exception.

The syntax of the join() method is as follows:

		public final void join() throws InterruptedException

The join() method is useful in scenarios where one thread must wait for another thread to complete before proceeding with its own work. For example, if a main thread creates several worker threads to perform some tasks, it may need to wait for all the worker threads to complete before printing the final result.

Here is an example that demonstrates the usage of the join() method:

		Thread t1 = new Thread(new Task());
		Thread t2 = new Thread(new Task());

		t1.start();
		t2.start();

		t1.join();
		t2.join();

		// Both t1 and t2 have completed their execution
		System.out.println("All tasks are completed");


In this example, the main thread creates two worker threads t1 and t2, and starts their execution. It then waits for both threads to complete using the join() method, and finally prints a message indicating that all tasks are completed.

# 33. what is thread pool?

In Java, a thread pool is a collection of worker threads that are managed by a thread pool manager. The thread pool manager is responsible for creating, starting, and stopping threads, as well as distributing tasks to the worker threads.

Thread pools are used to improve the performance and scalability of multi-threaded applications. Rather than creating a new thread every time a task needs to be executed, a thread pool maintains a pool of pre-created threads that are ready to handle tasks as soon as they become available. This reduces the overhead of thread creation and destruction and allows the application to handle a large number of concurrent tasks without running out of system resources.

The size of the thread pool is typically configurable and depends on the characteristics of the application and the underlying hardware. A larger thread pool can handle more concurrent tasks, but also consumes more system resources. Conversely, a smaller thread pool may be more efficient in terms of resource usage but may not be able to handle as many concurrent tasks.

Java provides a built-in implementation of a thread pool through the java.util.concurrent.ExecutorService interface. The ExecutorService interface defines methods for submitting tasks to a thread pool and managing the execution of those tasks. There are several implementations of the ExecutorService interface, including the ThreadPoolExecutor, which is a general-purpose thread pool, and the ScheduledThreadPoolExecutor, which is a thread pool that is optimized for executing scheduled tasks at specified intervals.

# 34.How to join two tables in entity class?

In Java Persistence API (JPA), you can use the @JoinColumn annotation to join two tables in an entity class. The @JoinColumn annotation is used to specify the foreign key column in a relationship between two entities.

Here is an example of how to join two tables in an entity class using the @JoinColumn annotation:

		@Entity
		@Table(name = "employee")
		public class Employee {

		    @Id
		    @GeneratedValue(strategy = GenerationType.IDENTITY)
		    private Long id;

		    @Column(name = "name")
		    private String name;

		    @ManyToOne(fetch = FetchType.LAZY)
		    @JoinColumn(name = "department_id")
		    private Department department;

		    // other fields, getters, and setters
		}

		@Entity
		@Table(name = "department")
		public class Department {

		    @Id
		    @GeneratedValue(strategy = GenerationType.IDENTITY)
		    private Long id;

		    @Column(name = "name")
		    private String name;

		    // other fields, getters, and setters
		}


In this example, the Employee entity has a many-to-one relationship with the Department entity. The @JoinColumn annotation is used to specify the foreign key column department_id in the employee table that references the primary key column id in the department table. The fetch attribute is set to LAZY to indicate that the department should be loaded lazily when it is accessed.

To perform a join query using JPA, you can use JPQL (Java Persistence Query Language) or Criteria API. Here is an example of how to use JPQL to join the Employee and Department entities:

		String jpql = "SELECT e FROM Employee e JOIN e.department d WHERE d.name = :deptName";
		TypedQuery<Employee> query = entityManager.createQuery(jpql, Employee.class);
		query.setParameter("deptName", "IT");
		List<Employee> employees = query.getResultList();

In this example, the JOIN keyword is used to join the Employee and Department entities on the department field. The WHERE clause is used to filter the results by department name. The entityManager object is an instance of EntityManager, which is used to interact with the JPA persistence context.

# default functional interfaces in java 8 ?

In Java 8, default functional interfaces are interfaces that have a single abstract method (SAM) and a default implementation for one or more additional methods. These interfaces are also known as "functional interfaces" because they can be used as the target type for lambda expressions or method references.

Some of the default functional interfaces in Java 8 include:

Predicate<T> - Represents a function that takes an argument of type T and returns a boolean value.

Consumer<T> - Represents a function that takes an argument of type T and returns no result.

Supplier<T> - Represents a function that takes no arguments and returns a value of type T.

Function<T, R> - Represents a function that takes an argument of type T and returns a result of type R.

UnaryOperator<T> - Represents a function that takes an argument of type T and returns a result of type T.

BinaryOperator<T> - Represents a function that takes two arguments of type T and returns a result of type T.

Runnable - Represents a function that takes no arguments and returns no result.

Callable<T> - Represents a function that takes no arguments and returns a value of type T.

These default functional interfaces provide a convenient and easy-to-use way to implement functional programming in Java 8.


# Exception Hierarchy
		Throwable
		├── Error
		│   ├── AssertionError
		│   ├── OutOfMemoryError
		│   ├── StackOverflowError
		│   ├── ThreadDeath
		│   └── ...
		│
		└── Exception
		    ├── RuntimeException
		    │   ├── ArithmeticException
		    │   ├── ArrayIndexOutOfBoundsException
		    │   ├── ClassCastException
		    │   ├── NullPointerException
		    │   ├── IllegalArgumentException
		    │   ├── IndexOutOfBoundsException
		    │   ├── IllegalStateException
		    │   ├── UnsupportedOperationException
		    │   └── ...
		    │
		    ├── IOException
		    │   ├── FileNotFoundException
		    │   ├── InterruptedIOException
		    │   ├── EOFException
		    │   └── ...
		    │
		    ├── SQLException
		    ├── ClassNotFoundException
		    ├── CloneNotSupportedException
		    ├── InterruptedException
		    ├── ReflectiveOperationException
		    └── ...






