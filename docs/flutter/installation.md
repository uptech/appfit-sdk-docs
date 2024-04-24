# Installing

There are two ways to install the SDK. The first is to use the latest version from pub.dev, but you can always specify the direct git url in your pubspec.yaml file.

## Pub.dev

To install from pub.dev, simply fun the command

```shell
flutter pub add appfit
```

This will add a line like this to your package's pubspec.yaml

```yaml
dependencies:
  appfit: ^1.0.0
```

## Git

To reference directly from git, you can add this to your pubspec.yaml file

```yaml
appfit:
  git:
    url: https://github.com/uptech/appfit-flutter-sdk.git
    ref: main
```

---

The AppFit SDK is Open Source. Find it on [GitHub here](https://github.com/uptech/appfit-flutter-sdk)
