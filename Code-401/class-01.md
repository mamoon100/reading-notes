# Java Basics

## VARIABLES

A Java variable is a piece of memory that can contain a data value. A variable thus has a data type.

The Java programming language defines the following kinds of variables:

- Instance Variables (Non-Static Fields) Technically speaking, objects store their individual states in "non-static fields", that is, fields declared without the static keyword. Non-static fields are also known as instance variables because their values are unique to each instance of a class (to each object, in other words); the currentSpeed of one bicycle is independent from the currentSpeed of another.
- Class Variables (Static Fields) A class variable is any field declared with the static modifier; this tells the compiler that there is exactly one copy of this variable in existence, regardless of how many times the class has been instantiated. A field defining the number of gears for a particular kind of bicycle could be marked as static since conceptually the same number of gears will apply to all instances. The code static int numGears = 6; would create such a static field. Additionally, the keyword final could be added to indicate that the number of gears will never change.
- Local Variables Similar to how an object stores its state in fields, a method will often store its temporary state in local variables. The syntax for declaring a local variable is similar to declaring a field (for example, int count = 0;). There is no special keyword designating a variable as local; that determination comes entirely from the location in which the variable is declared — which is between the opening and closing braces of a method. As such, local variables are only visible to the methods in which they are declared; they are not accessible from the rest of the class.
- Parameters You've already seen examples of parameters, both in the Bicycle class and in the main method of the "Hello World!" application. Recall that the signature for the main method is public static void main(String[] args). Here, the args variable is the parameter to this method. The important thing to remember is that parameters are always classified as "variables" not "fields". This applies to other parameter-accepting constructs as well (such as constructors and exception handlers) that you'll learn about later in the tutorial.

## Naming

Every programming language has its own set of rules and conventions for the kinds of names that you're allowed to use, and the Java programming language is no different. The rules and conventions for naming your variables can be summarized as follows:

- Variable names are case-sensitive. A variable's name can be any legal identifier — an unlimited-length sequence of Unicode letters and digits, beginning with a letter, the dollar sign "\$" , or the underscore character "\_". The convention, however, is to always begin your variable names with a letter, not "$" or "\_". Additionally, the dollar sign character, by convention, is never used at all. You may find some situations where auto-generated names will contain the dollar sign, but your variable names should always avoid using it. A similar convention exists for the underscore character; while it's technically legal to begin your variable's name with "\_", this practice is discouraged. White space is not permitted.
- Subsequent characters may be letters, digits, dollar signs, or underscore characters. Conventions (and common sense) apply to this rule as well. When choosing a name for your variables, use full words instead of cryptic abbreviations. Doing so will make your code easier to read and understand. In many cases it will also make your code self-documenting; fields named cadence, speed, and gear, for example, are much more intuitive than abbreviated versions, such as s, c, and g. Also keep in mind that the name you choose must not be a keyword or reserved word.
- If the name you choose consists of only one word, spell that word in all lowercase letters. If it consists of more than one word, capitalize the first letter of each subsequent word. The names gearRatio and currentGear are prime examples of this convention. If your variable stores a constant value, such as static final int NUM_GEARS = 6, the convention changes slightly, capitalizing every letter and separating subsequent words with the underscore character. By convention, the underscore character is never used elsewhere.

## operator

- Arithmetic Operators: They are used to perform simple arithmetic operations on primitive data types.

```java
- : Multiplication
/ : Division
% : Modulo
* : Addition
– : Subtraction
```

- Unary Operators: Unary operators need only one operand. They are used to increment, decrement or negate a value.

```java
– :Unary minus, used for negating the values.
+ :Unary plus, indicates positive value (numbers are positive without this, however). It performs an automatic conversion to int when the type of its operand is byte, char, or short. This is called unary numeric promotion.

++ :Increment operator, used for incrementing the value by 1. There are two varieties of increment operator.

    Post-Increment : Value is first used for computing the result and then incremented.

    Pre-Increment : Value is incremented first and then result is computed.

-- : Decrement operator, used for decrementing the value by 1. There are two varieties of decrement operator.

    Post-decrement : Value is first used for computing the result and then decremented.

    Pre-Decrement : Value is decremented first and then result is computed.

! : Logical not operator, used for inverting a boolean value.

```

- Assignment Operator : ‘=’ Assignment operator is used to assign a value to any variable. It has a right to left associativity, i.e value given on right hand side of operator is assigned to the variable on the left and therefore right hand side value must be declared before using it or should be a constant.

## Java control flow

Control flow or flow of control is the order in which instructions, statements and function calls being executed or evaluated when a program is running. The control flow statements are also called as Flow Control Statements. In Java, statements inside your code are generally executed sequentially from top to bottom, in the order that they appear. It is not always the case your program statements to be executed straightforward one after another sequentially, you may require to execute or skip certain set of instructions based on condition, jump to another statements, or execute a set of statements repeatedly. In Java, control flow statements are used to alter, redirect, or to control the flow of program execution based on the application logic.

![control flow img java](https://w3adda.com/wp-content/uploads/2018/12/java-control-statements-1024x547.jpg)

## Complied Language

Compiling is the transformation from Source Code (human readable) into machine code (computer executable). A compiler is a program. A compiler takes the recipe (code) for a new program (written in a high level language) and transforms this Code into a new language (Machine Language) that can be understood by the computer itself. This "machine language" is difficult to impossible for humans to read and understand (much less debug and maintain), thus the need for "high level languages" such as JAVA.
