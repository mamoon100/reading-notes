# Cognito

What is cognito?
Cognito lets you add user sign-up, sign-in, and access control to your web and mobile apps quickly and easily

Why use cognito?
Cognito is a service that lets you add user sign-up, sign-in, and access control to your web and mobile apps quickly and easily so you can focus on your business logic and not on the complexities of managing users.

Setup Cognito.

Open the Terminal and navigate to the directory where you have your code.
Type the following command:

`amplify add auth`

```bash
? Do you want to use the default authentication and security configuration?
    `Default configuration`
? How do you want users to be able to sign in?
    `Username`
? Do you want to configure advanced settings?
    `No, I am done.
```

`amplify push`

and in the gradle build file add the following dependencies:

`implementation 'com.amplifyframework:aws-auth-cognito:1.30.0'`

Add the auth plugin

```java
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.configure(getApplicationContext());
```

And there you have it basic Cognito setup.
