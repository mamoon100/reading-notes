# Android Fundamentals

The android app can be written using the android SDK, and in three different languages Kotlin, Java, and C++, then the SDK can be used to build the app into an android package apk file or an android application bundle aap file.

the aap is not a binary file, it is a zip file that contains the source code, the resources, and the manifest file, and it will not run if you try to install it on your device, the only way it works if you upload it to the google play store, the google play store will install it on your device.

Any android app has 4 components:

1. Activities
2. Services
3. Broadcast receivers
4. Content providers

#### Activities

is the entry point to the app, it is the first activity that is called when the app is started.

#### Services

A service is a general-purpose entry point for keeping an app running in the background for all kinds of reasons.

#### Broadcast receivers

A broadcast receiver is a component that enables the system to deliver events to the app outside of a regular user flow, allowing the app to respond to system-wide broadcast announcements

#### Content providers

A content provider manages a shared set of app data that you can store in the file system, in a SQLite database, on the web, or on any other persistent storage location that your app can access

## The manifest file

Before the Android system can start an app component, the system must know that the component exists by reading the app's manifest file, AndroidManifest.xml. Your app must declare all its components in this file, which must be at the root of the app project directory.

The manifest does a number of things in addition to declaring the app's components, such as the following:

- Identifies any user permissions the app requires, such as Internet access or read-access to the user's contacts.
- Declares the minimum API Level required by the app, based on which APIs the app uses.
- Declares hardware and software features used or required by the app, such as a camera, bluetooth services, or a multitouch screen.
- Declares API libraries the app needs to be linked against (other than the Android framework APIs), such as the Google Maps library.
