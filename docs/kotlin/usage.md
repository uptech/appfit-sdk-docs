# Configuration & Tracking

To configure the AppFit SDK, simply construct an `AppFitConfiguration` class and insert your API Key.

Your API Key can be obtained from your AppFit Dashboard.

```kotlin
val appFit = AppFit(configuration = configuration)
```

Once you have the client constructed, tracking an event is as simple as calling `trackEvent`

A full example can be found below.

```kotlin
import appfit;

// Create the AppFitConfiguration
val configuration = AppFitConfiguration(apiKey = "API_KEY")

// Create the AppFit Client
val appFit = AppFit(configuration = configuration)

// Use the client to track events
appFit.trackEvent(name = "event_name", properties = mapOf("key" to "value"))
```

# Identifying Users

The AppFit SDK includes an `identify` call, that you can use to identify users in your analytic events.
This method supports any String-based identifier.

```kotlin
appfit.identifyUser("<id>")
```

Setting this to null, will remove all events going forward from including the userId.

```kotlin
appfit.identifyUser(null)
```

# Cached Events

We cache all events locally in the SDK. This allows us to rety failed events. If a device is experiencing network issues, we will retry the saved events later to help avoid losing any metrics.
