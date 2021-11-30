# Notifications

Sometimes you want to send a message to a user, but you don't want to send the message to all users. For example, you want to send a message to a user when they make a new post, but you don't want to send the message to all users.

And here where the notifications come in.

First we need to enter this command in the terminal:

`amplify add notifications`

Choose **FCM** for the notification service.

Add the following to the app/build.gradle file:

```groovy
dependencies {
    // Overrides an auth dependency to ensure correct behavior
    implementation 'com.google.android.gms:play-services-auth:19.2.0'

    // Import the BoM for the Firebase platform
    implementation platform('com.google.firebase:firebase-bom:28.2.1')
    implementation 'com.google.firebase:firebase-messaging'

    implementation 'com.amazonaws:aws-android-sdk-pinpoint:2.36.0'
    implementation 'com.amazonaws:aws-android-sdk-mobile-client:2.36.0'
}

apply plugin: 'com.google.gms.google-services'
```

and the following to the build.gradle file:

```groovy
buildscript {
    dependencies {
        classpath 'com.google.gms:google-services:4.0.1'
    }
}

allprojects {
    repositories {
        google()
    }
}
```

and add the following to the AndroidManifest.xml file:

```xml
<service
    android:name=".PushListenerService">
    <intent-filter>
        <action android:name="com.google.firebase.MESSAGING_EVENT"/>
    </intent-filter>
</service>
```

create amazon pinpoint client in the location of the app

```java
public class MainActivity extends AppCompatActivity {
    public static final String TAG = MainActivity.class.getSimpleName();

    private static PinpointManager pinpointManager;

    public static PinpointManager getPinpointManager(final Context applicationContext) {
        if (pinpointManager == null) {
            final AWSConfiguration awsConfig = new AWSConfiguration(applicationContext);
            AWSMobileClient.getInstance().initialize(applicationContext, awsConfig, new Callback<UserStateDetails>() {
                @Override
                public void onResult(UserStateDetails userStateDetails) {
                    Log.i("INIT", userStateDetails.getUserState());
                }

                @Override
                public void onError(Exception e) {
                    Log.e("INIT", "Initialization error.", e);
                }
            });

            PinpointConfiguration pinpointConfig = new PinpointConfiguration(
                    applicationContext,
                    AWSMobileClient.getInstance(),
                    awsConfig);

            pinpointManager = new PinpointManager(pinpointConfig);

            FirebaseMessaging.getInstance().getToken()
                    .addOnCompleteListener(new OnCompleteListener<String>() {
                        @Override
                        public void onComplete(@NonNull Task<String> task) {
                            if (!task.isSuccessful()) {
                                Log.w(TAG, "Fetching FCM registration token failed", task.getException());
                                return;
                            }
                            final String token = task.getResult();
                            Log.d(TAG, "Registering push notifications token: " + token);
                            pinpointManager.getNotificationClient().registerDeviceToken(token);
                        }
                    });
        }
        return pinpointManager;
    }

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Initialize PinpointManager
        getPinpointManager(getApplicationContext());
    }
}
```

And there it is simple notification setup.
