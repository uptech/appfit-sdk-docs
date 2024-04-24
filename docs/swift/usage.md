# Configuration & Tracking

To configure the AppFit SDK, simply construct an `AppFitConfiguration` class and insert your API Key.

Your API Key can be obtained from your AppFit Dashboard.

```swift
let configuration = AppFitConfiguration(apiKey: "API_KEY")
let appFit = AppFit(configuration: configuration)
```

Once you have the client constructed, tracking an event is as simple as calling `trackEvent`.

A full example can be found below.

```swift
import AppFit

// Create the AppFitConfiguration
let configuration = AppFitConfiguration(apiKey: "API_KEY")

// Create the AppFit Client
let appFit = AppFit(configuration: configuration)

// Use the client to track events
appFit.trackEvent(name: "event_name", properties: {"key": "value"})
```

# Identifying Users

The AppFit SDK includes an `identify` call which can be used to identify users in your analytic events.
This method supports any String-based identifier.

```swift
appfit.identifyUser("USER_ID")
```

Setting this identifier to null will remove user tracking from all events going forward.

```swift
appfit.identifyUser(nil)
```

# Cached Events

We cache all event locally in the SDK, allowing us to retry failed events. If a device is experiencing network issues, we will retry events once the device is back online to help avoid event data loss.
