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
