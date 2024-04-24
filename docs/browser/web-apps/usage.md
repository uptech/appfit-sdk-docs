# Usage

## Configuration & Tracking

To configure the AppFit SDK, simply construct an `AppFitBrowserConfiguration` class and insert your API Key.

Your API Key can be obtained from your AppFit Dashboard.

```javascript
const appFitConfig = new AppFitBrowserConfiguration("API_KEY");
```

This configuration should be passed to a new `AppFit` client:

```javascript
const appFitClient = new AppFit(appFitConfig);
```

Once you have the client constructed, tracking an event is as simple as calling `trackEvent`.

A full example can be found below.

```javascript
import {
  AppFit,
  AppFitBrowserConfiguration,
} from "@uptechworks/appfit-browser-sdk";

// Create the AppFitBrowserConfiguration
const config = new AppFitBrowserConfiguration("API_KEY");

// Create the AppFit Client
const appFit = new AppFit(config);

// Use the client to track events
await appFit.trackEvent("event_name", { example: "property" });
```

## Identifying Users

The AppFit SDK includes an identify call that you can use to identify users in your analytic events.
This method supports any String-based identifier.

```javascript
appFit.identifyUser("USER_ID");
```

Setting this identifier to null will remove user tracking from all events going forward.

```javascript
appFit.identifyUser();
```

## Cached Events

We cache all event locally in the SDK, allowing us to retry failed events. If a device is experiencing network issues, we will retry events once the device is back online to help avoid event data loss.
