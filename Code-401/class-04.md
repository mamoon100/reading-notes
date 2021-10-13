# OOP

- What is an object?

  the object will have a state and behavior for example dog have (name, age, breed, color, etc) and behavior of (bark, run, eat, sleep, etc) ,bicycle have (brand, size, color, etc) and behavior of (ride, brake, etc) so we can see that everything we see is an object now software object are the same concept as real world objects and we can use them in our code the state which we call it attributes and behavior which we call it methods

- The benefits of objects:

  1. Modularity : we can split our code into different files and we can reuse them in different projects.

  2. Information-hiding: we can hide the state and behavior of an object from the user.

  3. Code re-use: we can reuse the code of an object in different projects.

  4. Pluggability and debugging ease: we can add new functionality to an object without modifying the code of the object.

---

- What is a class?

  A class is a blueprint for creating objects for example you will see in real world some object share the same state and behavior so we can use the same class to create new objects for example we can create a dog class and create new objects from this class and give every dog different name and age and breed and color and etc while almost the behavior will remain the same and we can add new behavior as will.

- How to create a class in java?

  1. Create a class with the keyword class.

  2. Give the class a name.

  3. Create the constructor of the class.

  4. Create the methods of the class.

```java
class Bicycle {

    int cadence = 0;
    int speed = 0;
    int gear = 1;

    void changeCadence(int newValue) {
         cadence = newValue;
    }

    void changeGear(int newValue) {
         gear = newValue;
    }

    void speedUp(int increment) {
         speed = speed + increment;
    }

    void applyBrakes(int decrement) {
         speed = speed - decrement;
    }

    void printStates() {
         System.out.println("cadence:" +
             cadence + " speed:" +
             speed + " gear:" + gear);
    }
}
```

---

## Binary, Decimal and Hexadecimal Numbers

- What is a binary number?

  Binary numbers are numbers that are made up of only 0 and 1 and we count them by going from 0 to 1 and when we reach number of 1 we start from 0 again and adding 1 to the left 0,1,10,11,100,101,110,111,1000,1001......

- What is a decimal number?

  Decimal numbers are numbers that are made up of 0,2,3,4,5,6,7,8,9 and we count by going from 0 to 9 and when we reach number after 9 we start from 0 again and add 1 to the left 10,11,12,13,14,15,16,17,18,19,20,21,22,23........

- What is a hexadecimal number?

  Hexadecimal numbers are numbers that are made up of 0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F and we can count them by going from 0 to F and when we reach number after F we start from 0 again and add 1 to the left 0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F,10,11,12,13,14,15,16,17,18,19,1A, 1B, 1C, 1D, 1E, 1F,.......
