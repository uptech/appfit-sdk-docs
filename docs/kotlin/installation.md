# AppFit for Kotlin

The Kotlin SDK allows you to drop-in analytic tracking, direct to your AppFit project.

# Requirements

In order to use the AppFit SDK, your minimum SDK Target must be 26. We require API's that require version 26 to be the lowest target we can support.

# Installing

Installing the SDK is as simple as adding an `implementation` call into your projects dependencies inside of your `build.gradle` file.

```kotlin
implementation("io.appfit:appfit:1.0.0")
```

or if you use the toml configuration, this would look something like this:

```toml
[versions]
appfit = "1.0.0"
...

[libraries]
appfit = { module = "io.appfit:appfit", version.ref = "appfit" }
...
```

```kotlin
implementation(libs.appfit)
```

Once you have your gradle file configures, dont forget to enable internet access in your Android Manifest file

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

---

The AppFit SDK is open source. Find it on [GitHub here](https://github.com/uptech/appfit-kotlin-sdk).
