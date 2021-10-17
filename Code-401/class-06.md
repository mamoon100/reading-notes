# Inheritance and Interfaces

What Is Inheritance?

Let's talk back about our object of dog and bicycle and the way we say it could be done in OOP by creating class for each object, now imagine i want to say yes there is type and kind of bicycle but i want to set the normal bicycle other than for example race bicycle, the OOP allow us to make something called inheritance, it allow us to create class extend the original class.

![example for inheritance](http://www.btechsmartclass.com/java/java_images/OOP-Concept-Inheritance.png)

```java
class MountainBike extends Bicycle {

    // new fields and methods defining
    // a mountain bike would go here

}
```

---

What Is an Interface?

After learning objects, classes and inheritance now we can learn the interface which is a way of putting all the methods in one place, so we can use the methods in our class, but we can't use the methods in our class, we can only use the methods in our interface.

And we can implement the interface in our class, but we can't use the methods in our class, we can only use the methods in our interface.

i.e

- the interface

```java
public interface OperateCar {

   // constant declarations, if any

   // method signatures

   // An enum with values RIGHT, LEFT
   int turn(Direction direction,
            double radius,
            double startSpeed,
            double endSpeed);
   int changeLanes(Direction direction,
                   double startSpeed,
                   double endSpeed);
   int signalTurn(Direction direction,
                  boolean signalOn);
   int getRadarFront(double distanceToCar,
                     double speedOfCar);
   int getRadarRear(double distanceToCar,
                    double speedOfCar);
         ......
   // more method signatures
}
```

- implementing the interface

```java
public class OperateBMW760i implements OperateCar {

    // the OperateCar method signatures, with implementation --
    // for example:
    public int signalTurn(Direction direction, boolean signalOn) {
       // code to turn BMW's LEFT turn indicator lights on
       // code to turn BMW's LEFT turn indicator lights off
       // code to turn BMW's RIGHT turn indicator lights on
       // code to turn BMW's RIGHT turn indicator lights off
    }

    // other members, as needed -- for example, helper classes not
    // visible to clients of the interface
}

```
