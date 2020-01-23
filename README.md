# My-Awesome-Flutter

## Flutter
![图1-1](https://cdn.jsdelivr.net/gh/flutterchina/flutter-in-action/docs/imgs/1-1.png)

## Dart / Flutter Exception Capture
### Dart: Single Thread
![图2-12](https://cdn.jsdelivr.net/gh/flutterchina/flutter-in-action/docs/imgs/2-12.png)
### Flutter:
- `FlutterError.reportError`
```dart
void main() {
  FlutterError.onError = (FlutterErrorDetails details) {
    reportError(details);
  };
}
```
  - Sync: `try/catch`
  ```dart
  try {
    // Execute build method  
    built = build();
  } catch (e, stack) {
    // Alert when exception is captured 
    built = ErrorWidget.builder(_debugReportException('building $this', e, stack));
  } 
```
  - Async: `runZoned`
  ```dart
try{
    Future.delayed(Duration(seconds: 1)).then((e) => Future.error("xxx"));
}catch (e){
    print(e)
}
```

## Development Experiences
- Setup
- Debug / Inspection 
- Hot-reload (state is maintained due to JIT)

## Package Management

The file explorer is accessible using the button in left corner of the navigation bar. You can create a new file by clicking the **New file** button in the file explorer. You can also create folders by clicking the **New folder** button.

## Internationalisation
- flutter_localizations ([https://flutter.dev/docs/development/accessibility-and-localization/internationalization](https://flutter.dev/docs/development/accessibility-and-localization/internationalization))

## CI/CD and Distribution
- Distribution of alpha, beta testing
	- Microsoft App Centre
- CI/CD 
	- Fastlane

## Network / IO and API Client
- Dio package ([https://github.com/flutterchina/dio](https://github.com/flutterchina/dio))
	- Axios equivalent 
- WebSocket
- JSON serialisation / deserilization <-> Dart Model 

## State Management
- RxDart (binding and streams)
	- Verified in iOS development and Web development
	- Too many side-effects if relationship between UI and models are complex
- Redux ([https://github.com/brianegan/flutter_redux]
- (https://github.com/brianegan/flutter_redux))
- Bloc ([https://pub.dev/packages/bloc](https://pub.dev/packages/bloc))
![Bloc Architecture](https://raw.githubusercontent.com/felangel/bloc/master/docs/assets/bloc_architecture.png)
 - Official documents about State Management
	 - [https://flutter.dev/docs/development/data-and-backend/state-mgmt](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
	 - No strong opinions yet

## Layout
- Row
- Column
- Flex
- Wrap / Flow
- Stack / Positioned
- Align

## Forms
- Form and Field concepts are natively implemented
	- Think about Formik
		- Context
		- Field
		- FormState

## Widgets
- Think about Component in React - declarative
- Life Cycles
### State
- `StatefulWidget`
- `State`
### Button
### Images / Icon
- From assets,  `pubspec.yaml`
```
  assets:
    - images/avatar.png
```
- From Network
```
Image(
  image: NetworkImage(
      "https://xxx"),
  width: 100.0,
)
```
### Font / TypoGraphy
- Custom Font
```
 flutter:
   fonts:
     - family: Raleway
       fonts:
         - asset: assets/fonts/Raleway-Regular.ttf
         - asset: packages/my_package/fonts/Raleway-Medium.ttf
           weight: 500
```


## Container
- Padding
- Constraints
- DecoratedBox
- Tranform
- Scaffold / TabBar / BottomNavigation
- Clip

## Scrollable
- SingleChildScrollView
- ListView
- GridView
- CustomScrollView
- ScrollController

## Styling
- WillPopScope
- Provider / Theme
- FutureBuilder / StreamBuilder

## Charts / SVG
- Flutter SVG
	- [https://pub.dev/packages/flutter_svg](https://pub.dev/packages/flutter_svg)
- Charts Flutter (Google)
	- [https://google.github.io/charts/flutter/gallery.html](https://google.github.io/charts/flutter/gallery.html)
- Syncfusion Flutter Chart
	- [https://help.syncfusion.com/flutter/chart/overview](https://help.syncfusion.com/flutter/chart/overview)
	- Requires license but looks powerful and flexible on the demo app

## WebView
- Official WebView (experimental)
	- [https://pub.dev/packages/webview_flutter](https://pub.dev/packages/webview_flutter)
- Community WebView
	- [https://pub.dev/packages/flutter_webview_plugin](https://pub.dev/packages/flutter_webview_plugin)

## Animation (To be added)

## File Organisation practices
1. One common way
```
flutter_app
├── android
├── fonts
├── i10n-arb
├── imgs
├── ios
├── jsons
├── lib
└── test

lib
├── common
├── i10n
├── models
├── states
├── routes
└── widgets
```
