# Intent Filters

Imagine You want to create an app that can be open from another app to preform a specific task, So there is a need to create a filter to filter the intent.

For example, if you build a social app that can share messages or photos with the user's friends, you should support the ACTION_SEND intent. Then, when users initiate a "share" action from another app, your app appears as an option in the chooser dialog (also known as the "disambiguation dialog").

To allow this action to happen in your app, you need to create an intent filter that matches the action and data type.

How to create an intent filter?

In order to properly define which intents your activity can handle, each intent filter you add should be as specific as possible in terms of the type of action and data the activity accepts.
The system may send a given Intent to an activity if that activity has an intent filter fulfills the following criteria of the Intent object:

**Action**: The Intent action must match the action specified in the Intent filter.

**Data**: The Intent data type must match the data type specified in the Intent filter.

**Category**: The Intent category must match the category specified in the Intent filter.

For example, here's an activity with an intent filter that handles the ACTION_SEND intent when the data type is either text or an image:

```xml
<activity android:name="ShareActivity">
    <intent-filter>
        <action android:name="android.intent.action.SEND"/>
        <category android:name="android.intent.category.DEFAULT"/>
        <data android:mimeType="text/plain"/>
        <data android:mimeType="image/*"/>
    </intent-filter>
</activity>
```

Now after the user selects the ShareActivity from the chooser dialog, the system will send the Intent to the ShareActivity, So now let's see how to handle the activity.

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);

    setContentView(R.layout.main);

    // Get the intent that started this activity
    Intent intent = getIntent();
    Uri data = intent.getData();

    // Figure out what to do based on the intent type
    if (intent.getType().indexOf("image/") != -1) {
        // Handle intents with image data ...
    } else if (intent.getType().equals("text/plain")) {
        // Handle intents with text ...
    }
}
```

and thats how you create and handle intent filter.
