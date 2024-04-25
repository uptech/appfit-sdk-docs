# AppFit for JavaScript

The JavaScript SDK allows you to drop-in analytic tracking, direct to your AppFit project.

## How to install

1. Install AppFit by pasting the following `<script>` tag into your webpage between the `<head>` tags.

   ```html
   <script>
    window.AppFit={cache:{},trackEvent:(e,t)=>(window.AppFit.cache||(window.AppFit.cache={}),window.AppFit.cache.events||(window.AppFit.cache.events=[]),window.AppFit.cache.events.push({eventName:e,payload:t}),Promise.resolve()),identifyUser(e){window.AppFit.cache||(window.AppFit.cache={}),window.AppFit.cache.identity=e}},window.startAppFit=e=>{window.AppFit.apiKey=e;var t=document.createElement("script");t.type="module",t.src="https://d1433kipn7zjh1.cloudfront.net/browser-sdk/appfit.js";var p=document.createElement("script");p.noModule=!0,p.src="https://d1433kipn7zjh1.cloudfront.net/browser-sdk/appfit-legacy.js";var i=document.getElementsByTagName("script")[0];i.parentNode.insertBefore(t,i),i.parentNode.insertBefore(p,i)},
    
    window.startAppFit("YOUR_WRITE_KEY");
    </script>
   ```

2. Be sure to **replace `API_KEY` with your API secret**, leaving in the quotation marks. Your API Key can be obtained from your AppFit Dashboard.

3. Put any other AppFit `<script>` tags for tracking (e.g. tracking a screen view) _after_ the tag above.

### Example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>My Website</title>

    <!---------------->
    <!-- Pasted tag -->
    <!---------------->
    <script>
    window.AppFit={cache:{},trackEvent:(e,t)=>(window.AppFit.cache||(window.AppFit.cache={}),window.AppFit.cache.events||(window.AppFit.cache.events=[]),window.AppFit.cache.events.push({eventName:e,payload:t}),Promise.resolve()),identifyUser(e){window.AppFit.cache||(window.AppFit.cache={}),window.AppFit.cache.identity=e}},window.startAppFit=e=>{window.AppFit.apiKey=e;var t=document.createElement("script");t.type="module",t.src="https://d1433kipn7zjh1.cloudfront.net/browser-sdk/appfit.js";var p=document.createElement("script");p.noModule=!0,p.src="https://d1433kipn7zjh1.cloudfront.net/browser-sdk/appfit-legacy.js";var i=document.getElementsByTagName("script")[0];i.parentNode.insertBefore(t,i),i.parentNode.insertBefore(p,i)},
    
    window.startAppFit("API_KEY");
    </script>

    <!------------------->
    <!-- Example usage -->
    <!------------------->
    <script>
      window.AppFit.trackEvent("screen_viewed", {
        screen: window.location.pathname,
      });
    </script>
  </head>

  <body>
    <main>
      <h1>Welcome to My Website</h1>
    </main>
  </body>
</html>
```

### How does it work?

A `<script>` tag above tells a web browser that the text inside is JavaScript.

The code in the above `<script>` is a small script that loads the full AppFit code from a CDN, or Content Delivery Network, which is a network of servers that store data close to a user for quick delivery.

Once the full AppFit code is loaded, it is available to other `<script>` tags. In the example above, the `window.AppFit.trackEvent()` tracking code is ready to use after the full code is loaded.

---

The AppFit SDK is open source. Find it on [GitHub here](https://github.com/uptech/appfit-javascript-sdk).
