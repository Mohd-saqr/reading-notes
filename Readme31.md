# Sign in with web UI
first we add In terminal, navigate to your project, run amplify add auth (or if you've already added it, run amplify update auth).

## Add Response Handler
```
@Override
protected void onActivityResult(int requestCode, int resultCode, Intent data) {
    super.onActivityResult(requestCode, resultCode, data);

    if (requestCode == AWSCognitoAuthPlugin.WEB_UI_SIGN_IN_ACTIVITY_CODE) {
        Amplify.Auth.handleWebUISignInResponse(data);
    }
}
```

## Launch Web UI Sign In
```
Amplify.Auth.signInWithWebUI(
    this,
    result -> Log.i("AuthQuickStart", result.toString()),
    error -> Log.e("AuthQuickStart", error.toString())
);
```

## Sign in
The Auth category can be used to register a user, confirm attributes like email/phone, and sign in with optional multi-factor authentication. It is set up to use Amazon Cognito User Pools which manages the users and their properties. 


## Register a user
```
AuthSignUpOptions options = AuthSignUpOptions.builder()
    .userAttribute(AuthUserAttributeKey.email(), "my@email.com")
    .build();
Amplify.Auth.signUp("username", "Password123", options,
    result -> Log.i("AuthQuickStart", "Result: " + result.toString()),
    error -> Log.e("AuthQuickStart", "Sign up failed", error)
);
```

The next step in the sign up flow is to confirm the user. A confirmation code will be sent to the email id provided during sign up. Enter the confirmation code received via email in the confirmSignUp call.

```
Amplify.Auth.confirmSignUp(
    "username",
    "the code you received via email",
    result -> Log.i("AuthQuickstart", result.isSignUpComplete() ? "Confirm signUp succeeded" : "Confirm sign up not complete"),
    error -> Log.e("AuthQuickstart", error.toString())
);
```


## Sign in a user 
Implement a UI to get the username and password from the user. After the user enters the username and password you can start the sign in flow by calling the following method:
```
Amplify.Auth.signIn(
    "username",
    "password",
    result -> Log.i("AuthQuickstart", result.isSignInComplete() ? "Sign in succeeded" : "Sign in not complete"),
    error -> Log.e("AuthQuickstart", error.toString())
);
```
# Resources
 [Cognito](https://docs.amplify.aws/lib/auth/signin/q/platform/android/#multi-factor-authentication)

