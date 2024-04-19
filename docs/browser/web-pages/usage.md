# Usage

Once you have pasted the installation `<script>` tag inside the `<head>` tags of a webpage, you can use AppFit's `trackEvent` function to record user behavior.

See the following for specific use cases.

## Page Views

This event will record a user visiting a webpage.

```html
<script>
window.AppFit.trackEvent("screen_viewed", { screen: window.location.pathname })
</script>
```
