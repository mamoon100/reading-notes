# Maps, primitives, File I/O

## Java Type System

Java has a two-fold type system consisting of primitives such as int, boolean and reference types such as Integer, Boolean. Every primitive type corresponds to a reference type.

Every object contains a single value of the corresponding primitive type. The wrapper classes are immutable (so that their state can't change once the object is constructed) and are final (so that we can't inherit from them).

Under the hood, Java performs a conversion between the primitive and reference types if an actual type is different from the declared one:

```java
Integer j = 1;          // auto boxing
int i = new Integer(1); // unboxing
```

The process of converting a primitive type to a reference one is called auto boxing, the opposite process is called unboxing.

A wrapper class is an object that encapsulates a primitive type. Each primitive type has a corresponding wrapper:

- byte, short, int, long, float, double, boolean, char
- Byte, Short, Integer, Long, Float, Double, Boolean, Character

![data wrapper](https://miro.medium.com/max/681/1*AQzGbqmrJfVMJeJ7UVQctw.png)

Each wrapper class has Object as a superclass. Byte, Short, Integer, Long Float and Double have Number as their direct superclass. This means that each wrapper class can implement the methods of the Object class such as hashCode(), equals(Object obj), clone(), and toString().

and here we can see the difference in memory and time complexity of the two methods:

![memory](https://www.baeldung.com/wp-content/uploads/2018/08/plot-memory-bits.gif)
![time](https://www.baeldung.com/wp-content/uploads/2018/08/plot-benchmark-primitive-wrapper-3.gif)

in the end we can see that objects in Java are slower and have a bigger memory impact than their primitive analogs.

- What is Exception in Java?

**Dictionary Meaning:** Exception is an abnormal condition.

**In Java**, an exception is an event that disrupts the normal flow of the program. It is an object which is thrown at runtime.

- Why we use Exception in Java?

Suppose there are 10 statements in a Java program and an exception occurs at statement 5; the rest of the code will not be executed, i.e., statements 6 to 10 will not be executed. However, when we perform exception handling, the rest of the statements will be executed. That is why we use exception handling in Java.

The java.lang.Throwable class is the root class of Java Exception hierarchy inherited by two subclasses: Exception and Error. The hierarchy of Java Exception classes is given below:

![Exception map](https://static.javatpoint.com/core/images/hierarchy-of-exception-handling.png)

- How to Throw Exception in Java?

```java
public Object pop() {
    Object obj;

    if (size == 0) {
        throw new EmptyStackException();
    }

    obj = objectAt(size - 1);
    setObjectAt(size - 1, null);
    size--;
    return obj;
}
```

## Reading file in java

Objects of type Scanner are useful for breaking down formatted input into tokens and translating individual tokens according to their data type.

> The scanner provides methods like hasNextLine() and readNextLine() which can be used to read file line by line. It's advised to check for next line before reading next the line to avoid NoSuchElementException in Java.

```java

import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;


public class ScannerExample {

    public static void main(String args[]) throws FileNotFoundException {

        //creating File instance to reference text file in Java
        File text = new File("C:/temp/test.txt");

        //Creating Scanner instance to read File in Java
        Scanner scnr = new Scanner(text);

        //Reading each line of the file using Scanner class
        int lineNumber = 1;
        while(scnr.hasNextLine()){
            String line = scnr.nextLine();
            System.out.println("line " + lineNumber + " :" + line);
            lineNumber++;
        }

    }

}


Output:
line 1 :--------------------- START----------------------------
line 2 :Java provides several way to read files.
line 3 :You can read file using Scanner, FileReader,FileInputStream and BufferedReader.
line 4 :This Java program shows How to read file using java.util.Scanner class.
line 5 :--------------------- END-------------------------------
```
