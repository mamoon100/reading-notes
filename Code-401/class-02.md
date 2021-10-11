# Package ,Arrays, Loops, Imports

Package is a collection of related classes. Java uses package to group related classes, interfaces and sub-packages in any Java project.

- **Types Of Java Package**

Package can be built-in and user-defined, Java provides rich set of built-in packages in form of API that stores related classes and sub-packages.

- Built-in Package: math, util, lang, i/o etc are the example of built-in packages.
- User-defined-package: Java package created by user to categorize their project's classes and interface are known as user-defined packages.

To import java package into a class, we need to use java import keyword which is used to access package and its classes into the java program.

Use import to access built-in and user-defined packages into your java source file so that your class can refer to a class that is in another package by directly using its name.

There are 3 different ways to refer to any class that is present in a different package:

1. without import the package

we don't have the import keyword.

2. import package with specified class

Package can have many classes but sometimes we want to access only specific class in our program in that case, Java allows us to specify class name along with package name. If we use import **packagename.classname** statement then only the class with name classname in the package will be available for use.

3. import package with all classes

If we use **packagename.\*** statement, then all the classes and interfaces of this package will be accessible but the classes and interface inside the sub-packages will not be available for use.

The import keyword is used to make the classes of another package accessible to the current package.

## Loops in Java

The Java for loop is used to iterate a part of the program several times. If the number of iteration is fixed, it is recommended to use for loop.

There are four types of for loops in Java.

![java loop](https://static.javatpoint.com/images/java-loops.png)

1. Simple for Loop
2. For-each or Enhanced for Loop
3. While Loop
4. Do-while Loop

- Java Simple for Loop

1. Initialization: It is the initial condition which is executed once when the loop starts. Here, we can initialize the variable, or we can use an already initialized variable. It is an optional condition.
2. Condition: It is the second condition which is executed each time to test the condition of the loop. It continues execution until the condition is false. It must return boolean value either true or false. It is an optional condition.
3. Increment/Decrement: It increments or decrements the variable value. It is an optional condition.
4. Statement: The statement of the loop is executed each time until the second condition is false.

_syntax:_

```java
for(initialization; condition; increment/decrement){
//statement or code to be executed
}
```

- Java For-each Loop

The for-each loop is used to traverse array or collection in Java. It is easier to use than simple for loop because we don't need to increment value and use subscript notation.

It works on the basis of elements and not the index. It returns element one by one in the defined variable.

_syntax:_

```java
for(data_type variable : array_name){
//code to be executed
}
```

- Java While Loop

The while loop is Java's most fundamental loop statement. It repeats a statement or a block of statements while its controlling Boolean-expression is true.

_syntax:_

```java
while(condition){
//code to be executed
}
```

The loop's **Boolean-expression is evaluated before the first iteration of the loop** – which means that if the condition is evaluated to false, the loop might not run even once.

- Java Do-while Loop

The do-while loop is similar to the while loop, except that the loop will execute at least once.

_syntax:_

```java
do{
//code to be executed
}while(condition);
```
