# Kinesis
Using the Google Play services location APIs, your app can request the last known location of the user's device. In most cases, you are interested in the user's current location, which is usually equivalent to the last known location of the device, the getLastLocation() method in the fused location provider.

# Set up Google Play services

To access the fused location provider, your app's development project must include Google Play services. 

The following snippet shows an example build.gradle file that uses the location library:

```
apply plugin: 'com.android.application'

...

dependencies {
    implementation 'com.google.android.gms:play-services-location:19.0.1'
}

```

# Specify app permissions

Apps whose features use location services must request location permissions, depending on the use cases of those features

``
<!-- Recommended for Android 9 (API level 28) and lower. -->
<!-- Required for Android 10 (API level 29) and higher. -->
<service
    android:name="MyNavigationService"
    android:foregroundServiceType="location" ... >
    <!-- Any inner elements would go here. -->
</service>

``

``
<manifest ... >
  <!-- Always include this permission -->
  <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />

  <!-- Include only if your app benefits from precise location access. -->
  <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
</manifest>

``


# Create location services client

In your activity's onCreate() method, create an instance of the Fused Location Provider Client as the following code snippet shows.

```
private lateinit var fusedLocationClient: FusedLocationProviderClient

override fun onCreate(savedInstanceState: Bundle?) {
    // ...

    fusedLocationClient = LocationServices.getFusedLocationProviderClient(this)
}

```

# Get the last known location

o request the last known location, call the getLastLocation() method. The following code snippet illustrates the request and a simple handling of the response:

``
fusedLocationClient.lastLocation
        .addOnSuccessListener { location : Location? ->
            // Got last known location. In some rare situations this can be null.
        }

``

# Resources
 [Kinesis](https://developer.android.com/training/location/retrieve-current)



