# Location :

### Declare dependencies for Google Play services:

1. Open the build.gradle file inside your app's module directory.

2. add dependencies to your gradle file :

```groovy
 apply plugin: 'com.android.application'

 ...

 dependencies {
    implementation 'com.google.android.gms:play-services-location:18.0.0'
}
```

3. Save the changes and sync your project.

### Specify app permissions :

- To protect user privacy, apps that use location services must request location permissions.

#### Types of location access:

### \* Category: we add this code in the manifest file :

```xml
<!-- Recommended for Android 9 (API level 28) and lower. -->
<!-- Required for Android 10 (API level 29) and higher. -->
<service
    android:name="MyNavigationService"
    android:foregroundServiceType="location" ... >
    <!-- Any inner elements would go here. -->
</service>
```

```xml

<manifest ... >
  <!-- Always include this permission -->
  <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />

  <!-- Include only if your app benefits from precise location access. -->
  <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
</manifest>

```

### \* Accuracy : when you sent a location try to keep it in range 50 m.

### Request location access at runtime :

```java
ActivityResultLauncher<String[]> locationPermissionRequest =
    registerForActivityResult(new ActivityResultContracts
        .RequestMultiplePermissions(), result -> {
            Boolean fineLocationGranted = result.getOrDefault(
                    Manifest.permission.ACCESS_FINE_LOCATION, false);
            Boolean coarseLocationGranted = result.getOrDefault(
                    Manifest.permission.ACCESS_COARSE_LOCATION,false);
            if (fineLocationGranted != null && fineLocationGranted) {
                // Precise location access granted.
            } else if (coarseLocationGranted != null && coarseLocationGranted) {
                // Only approximate location access granted.
            } else {
                // No location access granted.
            }
        }
    );

// ...

// Before you perform the actual permission request, check whether your app
// already has the permissions, and whether your app needs to show a permission
// rationale dialog. For more details, see Request permissions.
locationPermissionRequest.launch(new String[] {
    Manifest.permission.ACCESS_FINE_LOCATION,
    Manifest.permission.ACCESS_COARSE_LOCATION
});

```

### Create location services client :

- In your activity's onCreate() method, create an instance of the Fused Location Provider Client as the following code snippet shows.

```java
private FusedLocationProviderClient fusedLocationClient;

// ..

@Override
protected void onCreate(Bundle savedInstanceState) {
    // ...

    fusedLocationClient = LocationServices.getFusedLocationProviderClient(this);
}
```

### Get the last known location :

```java
fusedLocationClient.getLastLocation()
        .addOnSuccessListener(this, new OnSuccessListener<Location>() {
            @Override
            public void onSuccess(Location location) {
                // Got last known location. In some rare situations this can be null.
                if (location != null) {
                    // Logic to handle location object
                }
            }
        });

```
