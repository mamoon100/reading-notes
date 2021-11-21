# Espresso

We took in previous week to test the code using unit tests but now in android if we want to test th UI we need to use espresso.

**Espresso** is a testing framework for Android. It is a framework that allows us to test the UI of an Android app, it's simple light framework, easy to use and very powerful.

e.g.

```java
@Test
public void greeterSaysHello() {
    onView(withId(R.id.name_field)).perform(typeText("Steve"));
    onView(withId(R.id.greet_button)).perform(click());
    onView(withText("Hello Steve!")).check(matches(isDisplayed()));
}
```

Here we are using espresso to test the UI of the app.

We can also use Espresso test recorder to record the test and then we can use the recorded test to test the app, without writing single code line.

to do that we need to follow the steps below:

1. Turn off animations on your test device
2. Install Espresso test recorder
3. Run the test
4. Open the recorded test and check the test result

and here you have it your first espresso test.
