# JAVA basics

**Get familiar with the basic elements that constitute a Java Console Application.**


### Structure of a Java Program

:question: **1. What are packages?**

* Packages are collections of types (classes and interfaces) organized into a unit.
* Companies name their packages by reversing their Internet domain name (e.g.: `com.company.package`).
* Packages are declared using `package` keyword at the beginning of the source file.
* To avoid conflicts between the names of the packages and the ones of classes and interfaces, packages names are written entirely in lower case.
*  If the domain name contains a hyphen or other special character, or if the package name begins with a digit or other character that is illegal to use as the beginning of a Java name, or if the package name contains a reserved Java keyword, such as "int", the suggested convention is to add an underscore to that name in order to be a valid package name.

---

:question: **2. Describe the access modifiers available in Java.**

:black_nib: The access modifiers available in Java are:

* Public. A public class/ method/ variable/ property has no accesibility restrictions and therefor can be accessed from any class, package or subclass.

* Private. A private class/ method/ variable/ property can only be accessed within the same class where it is defined. The access from another class or package or subclass is restricted.

* Protected. A protected class/ method/ variable/ property can be accessed within the same package or from its subclass in a different package, but the access to it from another class in another package is forbidden.

* Default: A default class/ method/ variable/ property can be accessed only within the same package.

---

:question: **3. What is the meaning of the static keyword?**

* In Java, the `static` keyword is a fundamental concept used to define class-level variables or methods. In order to access a static variable or a static method, we have to invoke the class name (e.g.: `ClassName.variableName` or `ClassName.methodName()`). If we don't want to specify the class name, we can use static import.

---

:question: **4. What are the requirements of the method that will serve as the entry point of a Java application?**

* The main method (the entry point method) has to be declared with the following signature: 

```
public static void main(String[] args){
// ...
}
```
* The entry point method must be declared as public in order to be accessed by the Java Virtual Machine (JVM).

* Conventionally, the entry point method must be called `main`.

* The entry point method must accept a single parameter (`args`) of String or an array of strings (`String`/ `String[]`).

---

:question: **5. What is a static import in Java? Describe the two options available.**

* To access static variables or methods without invoking the class name, we use static import. There are 2 ways to use static import: one is to import a single static member of the class (variable or method), another is to import all static members of the class. Here are 2 examples from Codecool:

```
package com.codecool.hellomaven;

import static java.lang.System.out; // We import the public static field called 'out' from the System class

public class Application {
    public static void main(String[] args){
        out.println("Hello Maven");
    }
}
```

and:

```
package com.codecool.hellomaven;

import static java.lang.System.*; // We import all public static members from the System class

public class Application {
    public static void main(String[] args){
        out.println("Hello Maven");
    }
}
```

___
---

### The build process and execution

:question: **6. What is the build process? Describe its steps.**

* The build process converts the source code into distributable format (JAR file or executable file) and it is initiated after pressing `Run` to execute the application. Building the application involves several steps:
- Java compiler performs static analysis to validate the syntax and semantics of the code;
- the Java compiler (Javac) transforms the source code (.java files) into platform-independent format (bytecode) and the content of each class in a source file is stored in a separate .class file;
- the compiled class files and other resources are packaged into distributable format (using Maven or Gradle);
- the code is tested;
- the packaged application is deployed to a target environment.

---

:question: **7. What is an .class file?**

* Java compiler translates human-readable Java code into platform-independent java bytecode instructions which are saved in a `.class` binary file that can be executed by every platform with a Java Virtual Machine (JVM).

---

:question: **8. What is bytecode?**

* Bytecode is a platform-independent code that can be executed on every platform that has a Java Virtual Machine (JVC) and it is generated after the Java compiler (Javac) converts the source code (.java file).

---

:question: **9. What is the JVM?**

* JVM (Java Virtual Machine) is an abstract machine responsible for interpreting the bytecode generated from a Java source code by a Java compiler.
* JVM provides runtime environment for Java programs and also manages memory and provides runtime services.

---

:question: **10. What is JIT?**

* JIT (Just-In-Time) is a technology/compiler used by Java Virtual Machine to optimize the bytecode and to generate high-quality platform-specific (native) machine code (with faster execution time and improved performance).

---

:question: **11. What are managed languages?**

* Java is a managed language because some aspects of the program execution (memory management, garbage collection, thread management, exception handling, security) are being done automatically.
* Java, C#, Python, Ruby and Swift are managed languages.

---

:question: **12. What is a Garbage Collector?**

* Garbage Collector is a component of Java Virtual Machine that automatically manages allocation and de-allocation of memory for Java objects. Garbage Collector periodically scans the memory to identify and remove objects that are no longer needed, in order to prevent memory leaks.

___
---

### Methods

:question: **13. What is the difference between a method and a function?**

* In Java, there is no difference between a method and a function - the two names are interchangeable.

---

:question: **14. What are the benefits of using methods?**

* The benefits of using methods in Java are: code reusability (methods encapsulate functionalities that can be re-used), modularity (breaking code into small, manageable pieces), abstraction (code is easier to understand and more abstract), readability (descriptive names), encapsulation (implementation details are hidden from other parts of the program).

---

:question: **15. How does a good method name look like?**

* According to Codecool, method names should reflect the operations they perform. 
* A good method name has the following features:
- uses verbs to describe the method (`get`, `set`, `calculate`, `validate`, etc.);
- uses camelCase (`calculateSalary`);
- is descriptive (gives the reader an idea of what the method does);
- follows naming conventions of the Java language (`get` should return a value, `set` should set a value);
- easy to read and understand;
- clear and concise.

---

:question: **16. What do we mean by the return type of a method?**

* The return type of a method is the data type of the value returned by the method and it can be any of the Java primitives types (int, double, float, byte, boolean, char, short, long).
* If the method doesn't return a value, then the return type should be `void`.

* :black_nib: Example:
```
public int addNumbers(int num1, int num2) {
    int sum = num1 + num2;
    return sum;
}
```

---

:question: **17. What is a method's signature?**

* A method signature is an unique identifier that includes: method name, parameter types and parameter order.

---

:question: **18. What is overloading?**

* (Method) Overloading is a feature that allows a class to have multiple methods with the same name, but with different parameters (in terms of type, number or order).

* :black_nib: Example:

```
public class Calculator {
   public int add(int x, int y) {
      return x + y;
   }

   public double add(double x, double y) {
      return x + y;
   }
}
```

:question: **19. What is the difference between instance and static methods?**

* Instance methods are associated with an instance of a class and can access instance variables, whislt static methods are associated with the class itself and cannot access instance variables directly.
* :black_nib: Examples of static methods: `copyValueOf()`, `format()`, `join()`, `valueOf()` [source: https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/String.html].
* :black_nib: Examples of instance methods: `charAt()`, `chars()`, `codePointAt()`, `codePointBefore()`, `compareTo()`, `compareToIgnoreCase()`, `concat()`, `contains()`, etc.
___
---

### Primitives vs Reference types

:question: **20. Can you describe the main distinction between reference and value types?**

* Value types are primitives (byte, short, long, char, int, double, float, boolean) that store the actual value in memory and are copied by value. Changes made to the copy will not affect the original.

* Reference types are objects, arrays, strings, lists, sets, maps that do not hold data directly, but rather contain a reference to a pointer to the memory location of the object that is stored in a variable. Changes made to the copy also affect the original and vice versa, because they share the same memory reference.

* :black_nib: Example of reference type from Codecool:
```
int[] numbers1 = {1,2,3};
int[] numbers2 = numbers1;

numbers2[0] = 0;
numbers1[1] = 0;

System.out.println(String.join(",", numbers1)); //Prints 0,0,3
System.out.println(String.join(",", numbers2)); //Prints 0,0,3
```
---

:question: **21. What is the keyword for creating reference types?**

* The keyword for creating reference types is `new`.

* :black_nib: Examples: 

```
// new object:
MyClass myObject = new MyClass();
// new array:
int[] myArray = new int[10];
```

---

:question: **22. Mention some built-in primitives and reference types.**

* :black_nib: Build-in primitives:
```
byte: 8-bit integer
short: 16-bit integer
int: 32-bit integer
long: 64-bit integer
float: 32-bit floating-point number
double: 64-bit floating-point number
boolean: true or false
char: 16-bit Unicode character
```

* :black_nib: Reference types: 
```
String: a sequence of characters
Object: the root of the class hierarchy
Array: a collection of elements of the same type
List: an ordered collection of elements that can contain duplicates
Set: a collection of unique elements, without any particular order
Map: a collection of key-value pairs, where each key maps to a value
```

---

:question: **23. What can you do if you need to modify a value type variable inside of a method?**

* To modify a value type inside a method, we need something to store and pass by reference.
Example from Codecool:

* :black_nib: Example from Codecool:

```
If you pass an int into a method, you're not going to be able to modify that int.

public static void main(String[] args)
{
    int counter = 0;
    
    increment(counter);
    
    System.out.println(counter); // Prints 0
}

private static void increment(int num)
{
    num += 1;
}
Of course, under most circumstances, you're better of with returning a value from the method anyways. This makes the code more easy to follow and less prone to errors.

public static void main(String[] args)
{
    int counter = 0;
    
    counter = increment(counter);
    
    System.out.println(counter); // Prints 1
}

private static int increment(int num)
{
    return num + 1;
}
```

---

:question: **24. What is the main difference between a primitive and its wrapper class?**

```
In Java, a primitive type is a basic data type, such as int, double, boolean, etc. A wrapper class is a class that provides an object representation of a primitive type. For example, the Integer class provides an object representation of the int primitive type.

The main difference between a primitive type and its wrapper class is that primitive types are not objects and do not have methods, while wrapper classes are objects and provide additional functionality. Here are some specific differences:

Representation: Primitive types are represented directly as values, while wrapper classes are represented as objects. For example, an int can be assigned a value directly, like int x = 42;, while an Integer must be assigned an object reference, like Integer y = new Integer(42);.

Immutability: Primitive types are immutable, meaning their values cannot be changed after they are assigned, while wrapper classes are mutable, meaning their values can be changed by invoking methods on them.

Nullability: Primitive types cannot be null, while wrapper classes can be null.

Methods: Wrapper classes provide methods that can be used to perform various operations on their values, such as converting between types, parsing strings, performing arithmetic, and comparing values.

Autoboxing: Java provides automatic conversion between primitive types and their corresponding wrapper classes, called autoboxing and unboxing. This allows primitive types to be used in contexts where objects are expected, and vice versa, without the need for explicit conversions.
```

___
---

### Basic types

:question: **25. What are some of the built-in types in Java that you know?**

:black_nib: Examples of build-in types:
```
* Primitive types:
byte: 8-bit signed integer
short: 16-bit signed integer
int: 32-bit signed integer
long: 64-bit signed integer
float: 32-bit floating-point number
double: 64-bit floating-point number
boolean: true or false
char: 16-bit Unicode character

* Reference types:
Object: the root of the class hierarchy
String: a sequence of characters
Array: a collection of elements of the same type
List: an ordered collection of elements that can contain duplicates
Set: a collection of unique elements, without any particular order
Map: a collection of key-value pairs, where each key maps to a value
StringBuilder: a mutable sequence of characters
BigDecimal: an arbitrary-precision decimal number
BigInteger: an arbitrary-precision integer
Date: a representation of a date and time
Calendar: a calendar-based representation of a date and time
TimeZone: a representation of a time zone
```

---

:question: **26. Can you mention some useful Java Core types?**

:black_nib: Examples of Java Core types:

* BigDecimal: represents an arbitrary-precision decimal number
* BigInteger: represents an arbitrary-precision integer
* Character: represents a Unicode character
* Date: represents a point in time, with millisecond precision
* Calendar: represents a calendar-based date and time
* TimeZone: represents a time zone
* SimpleDateFormat: a class for formatting and parsing dates
* Math: a class that provides various math-related methods, such as sqrt(), sin(), cos(), etc.
* Arrays: a class that provides methods for working with arrays, such as sort(), binarySearch(), etc.
* Collections: a class that provides methods for working with collections, such as sort(), binarySearch(), max(), min(), etc.
* Random: a class that provides methods for generating random numbers
* Scanner: a class that provides methods for reading input from various sources, such as the keyboard or a file
* System: a class that provides methods for interacting with the system, such as currentTimeMillis(), exit(), gc(), etc.

___
---

### Parsing strings

:question: **27. What is the primary way to convert a string to a number?**

* To convert a String to an int, you can use Integer.parseInt(String s).
* To convert a String to a long, you can use Long.parseLong(String s).
* To convert a String to a float, you can use Float.parseFloat(String s).
* To convert a String to a double, you can use Double.parseDouble(String s).

:black_nib: Example:
```
String str = "123";
int num = Integer.parseInt(str);
```

---

:question: **28. What is the class that is used to parse user input from the console into different types?**

* The class used to parse (convert) user input from console (`System.in`) into different types is `Scanner`.

:black_nib: Example from Codecool:

```
package com.codecool.hellomaven;
import java.util.Scanner;

public class Application {
    public static void main(String[] args){
        int i = getInt();
        System.out.println("The square of the number:");
        System.out.prinln(square(i));
    }

    private static int getInt(){
        Scanner scanner = new Scanner(System.in); // Create a new Scanner object with System.in as its source
        System.out.prinln("Please enter a number:");
        return scanner.nextInt(); // Ask the scanner to parse the input as integer
    }

    private static int square (int i){
        return i * i;
    }
}
```

:black_nib: Another example from Codecool:

```
package com.codecool.hellomaven;
import java.util.Scanner;

public class Application {
    public static void main(String[] args){
        int i = getInt();
        System.out.println("The square of the number:");
        System.out.println(square(i));
    }

    private static getInt(){
        Scanner scanner = new Scanner(System.in);
        System.out.prinln("Please enter a number:");
        String input = scanner.nextLine();
        return convertString(input);
    }

    private static int convertString(String s){
        return Integer.parseInt(s);
    }

    private static int square(int i){
        return i * i;
    }
}

```

---

:question: **29. What is an exception?**

* Exceptions are events that disrupt the normal flow of the program and can occur because of incorrect input:
- attempting to access an invalid index in an array
- dividing by zero
- opening a file that does not exist
- trying to access a null object reference
- running out of memory

---

:question: **30. How can you handle exceptions in Java?**

* To handle any exceptions, we can use the try-catch block or we can throw an exception.

---
___
