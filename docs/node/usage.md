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
} from '@uptechworks/appfit-server-sdk';

// Create the AppFitServerConfiguration
const config = new AppFitServerConfiguration("API_KEY");

// Create the AppFit Client
const appFitClient = new AppFit(config);

// Use the client to track events
await appFitClient.trackEvent("event_name", { example: 'property' }, { userId: 'exampleId' });
```

## Identifying Users

The Node AppFit SDK requires a user identifier for each tracked event. One may send a user id, an anonymous id, or both.

This method supports any String-based identifier.

User ID:
```javascript
await appFitClient.trackEvent("event_name", { example: 'property' }, { userId: 'exampleId' });
```

Anonymous ID:
```javascript
await appFitClient.trackEvent("event_name", { example: 'property' }, { anonymousId: 'example-anonymous-Id' });
```

Both:
```javascript
await appFitClient.trackEvent("event_name", { example: 'property' }, { userId: 'exampleId', anonymousId: 'example-anonymous-Id' });
```
