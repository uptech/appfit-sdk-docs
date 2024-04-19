# Usage

## Configuration & Tracking

To configure the AppFit SDK, simply construct an `AppFitServerConfiguration` class and insert your API Key.

Your API Key can be obtained from your AppFit Dashboard.

```javascript
const appFitConfig = new AppFitServerConfiguration('API_KEY');
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
  AppFitServerConfiguration,
} from '@uptechworks/appfit-node-sdk';

// Create the AppFitServerConfiguration
const config = new AppFitServerConfiguration("API_KEY");

// Create the AppFit Client
const appFitClient = new AppFit(config);

// Use the client to track events
await appFitClient.trackEvent("event_name", { example: 'property' });
```

## Identifying Users

The AppFit SDK includes an identify call that you can use to identify users in your analytic events.
This method supports any String-based identifier.

```javascript
appFitClient.identifyUser("USER_ID");
```

Leaving out the user ID will remove all future events from including the id.

```javascript
appFitClient.identifyUser();
```
