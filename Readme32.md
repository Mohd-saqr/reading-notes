# Allowing Other Apps to Start Your Activity 
To allow other apps to start your activity in this way, you need to add an <intent-filter> element in your manifest file for the corresponding <activity> element.

When your app is installed on a device, the system identifies your intent filters and adds the information to an internal catalog of intents supported by all installed apps. When an app calls startActivity() or startActivityForResult(), with an implicit intent, the system finds which activity (or activities) can respond to the intent.



## Add an Intent Filter 

In order to properly define which intents your activity can handle, each intent filter you add should be as specific as possible in terms of the type of action and data the activity accepts.

The system may send a given Intent to an activity if that activity has an intent filter fulfills the following criteria of the Intent object:

Action
A string naming the action to perform. Usually one of the platform-defined values such as ACTION_SEND or ACTION_VIEW.
Specify this in your intent filter with the <action> element. The value you specify in this element must be the full string name for the action, instead of the API constant (see the examples below).

Data
A description of the data associated with the intent.
Specify this in your intent filter with the <data> element. Using one or more attributes in this element, you can specify just the MIME type, just a URI prefix, just a URI scheme, or a combination of these and others that indicate the data type accepted.



## Handle the Intent in Your Activity

In order to decide what action to take in your activity, you can read the Intent that was used to start it.

As your activity starts, call getIntent() to retrieve the Intent that started the activity. You can do so at any time during the lifecycle of the activity, but you should generally do so during early callbacks such as onCreate() or onStart().


## Return a Result
If you want to return a result to the activity that invoked yours, simply call setResult() to specify the result code and result Intent. When your operation is done and the user should return to the original activity, call finish() to close (and destroy) your activity.

## Intent types 

here are two types of intents:

- Explicit intents specify which application will satisfy the intent, by supplying either the target app's package name or a fully-qualified component class name. You'll typically use an explicit intent to start a component in your own app, because you know the class name of the activity or service you want to start. For example, you might start a new activity within your app in response to a user action, or start a service to download a file in the background.
- Implicit intents do not name a specific component, but instead declare a general action to perform, which allows a component from another app to handle it. For example, if you want to show the user a location on a map, you can use an implicit intent to request that another capable app show a specified location on a map.


![](./screenShot/intent-filters_2x.png)



# Resources
 [Intent Filters](https://developer.android.com/training/basics/intents/filters)
  [Implicit vs. Explicit Intents](https://developer.android.com/guide/components/intents-filters#Types)