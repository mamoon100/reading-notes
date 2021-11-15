# Intents, Activities, and SharedPreferences

- What is a task?
  A task is a activity that is started by an intent and arranged in a task stack with order of FILO - First In Last Out, and when the user presses the back button, the task is removed from the stack.

- Lifecycle of a task and its back stack:
  The Home page for the device is the starting point where the user can start the app by clicking on the icon in the launcher .
  When the current activity starts another, the new activity is pushed on the top of the stack and takes focus. The previous activity remains in the stack, but is stopped. When an activity stops, the system retains the current state of its user interface. When the user performs the back action, the current activity is popped from the top of the stack (the activity is destroyed) and the previous activity resumes (the previous state of its UI is restored). Activities in the stack are never rearranged, only pushed and popped from the stack—pushed onto the stack when started by the current activity and popped off when the user leaves it using the Back button or gesture. As such, the back stack operates as a last in, first out object structure. Figure 1 visualizes this behavior with a timeline showing the progress between activities along with the current back stack at each point in time.

- The back button behavior:
  The back button is a hardware button that is located on the top left corner of the screen. When the user presses the back button, the current activity is popped from the top of the stack and the previous activity resumes. The back button is not used to navigate between activities in the same task. Instead, the back button is used to navigate between activities in different tasks.

## Save key-value data

If you have small collection of key value pairs, you can use SharedPreferences to save them and retrieve them later.

Get a handle to shared preferences:

1. getSharedPreferences() — Use this if you need multiple shared preference files identified by name, which you specify with the first parameter. You can call this from any Context in your app.

2. getPreferences() — Use this from an Activity if you need to use only one shared preference file for the activity. Because this retrieves a default shared preference file that belongs to the activity, you don't need to supply a name.

```java
Context context = getActivity();
SharedPreferences sharedPref = context.getSharedPreferences(
        getString(R.string.preference_file_key), Context.MODE_PRIVATE);

```

when naming the shared preference file, use name that is unique to your app.

Alternatively, if you need just one shared preference file for your activity, you can use the getPreferences() method:

```java
SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);

```

- how to write to shared preferences:

```java

SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
SharedPreferences.Editor editor = sharedPref.edit();
editor.putInt(getString(R.string.saved_high_score_key), newHighScore);
editor.apply();
```

- read from shared preferences:

```java
SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
int defaultValue = getResources().getInteger(R.integer.saved_high_score_default_key);
int highScore = sharedPref.getInt(getString(R.string.saved_high_score_key), defaultValue);
```
