# Configuration & Tracking

To configure the AppFit SDK, simply construct an `AppFitConfiguration` class and insert your API Key.

Your API Key can be obtained from your AppFit Dashboard.

```dart
final configuration = AppFitConfiguration(apiKey: 'API_KEY');
final appFit = AppFit(configuration: configuration);
```

Once you have the client constructed, tracking an event is as simple as calling `trackEvent`.

A full example can be found below.

```dart
import 'package:appfit/appfit.dart';

void main() {
    // Create the AppFitConfiguration
    final configuration = AppFitConfiguration(apiKey: 'API_KEY');

    // Create the AppFit Client
    final appFit = AppFit(configuration: configuration);

    // Use the client to track events
    appFit.trackEvent('event_name', properties: {'key': 'value'});
}
```

# Identifying Users

The AppFit SDK includes an `identify` call, that you can use to identify users in your analytic events.
This method supports any String-based identifier.

```dart
appfit.identifyUser("USER_ID");
```

Setting this identifier to null will remove user tracking from all events going forward.

```dart
appfit.identifyUser(null);
```

# Cached Events

We cache all event locally in the SDK, allowing us to retry failed events. If a device is experiencing network issues, we will retry events once the device is back online to help avoid event data loss.

# Shared Instances

Alternativly, we support using shared instances. This can be achieved by calling two methods.

`createInstance` and `getInstance`

## Creating a Shared Instance

To create a shared instance that can be shared is as simple as using the static method on the `AppFit` class.

```dart
// Create the configuration
final configuration = AppFitConfiguration(apiKey: 'API_KEY');

// Create the shared instance
AppFit.createInstance(configuration)
```

This will create an instance called `default`. Alternativly you can pass in a parameter `instanceName` if you are running multiple instances.

Note: The `createInstance` will return the newly created instance if you need access to it right away for tracking purposes.

### Access a Shared Instance

When you need to access the shared instance to perform a tracking event, you can call the `getInstance` method.

```dart
// Return an instance
AppFit.getInstance()
```

This will return an instance called `default`. Alternativly you can pass in a parameter `instanceName` if you are running multiple instances.

Note: If you call this method before creating an instance, an exception will be thrown.
