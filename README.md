# flutter_safe_phone_direct_caller

A simple plugin to call number directly from app, without going to phone dialer. Permission request is handled by plugin.

A fork of [yanisalfian/flutter-phone-direct-caller](https://github.com/yanisalfian/flutter-phone-direct-caller).

## Usage

Add dependency to pubspec.yaml file
```
flutter_safe_phone_direct_caller: ^0.1.0
```

### Android
No need any additional configuration.

### iOS
Add this to your ```info.plist``` under ```dict``` 
```
<key>LSApplicationQueriesSchemes</key>
<array>
  <string>tel</string>
</array>
```

## Example

```dart
import 'package:flutter/material.dart';
import 'package:flutter_safe_phone_direct_caller/flutter_safe_phone_direct_caller.dart';

void main() {
  runApp(Scaffold(
    body: Center(
      child: RaisedButton(
        onPressed: _callNumber,
        child: Text('Call Number'),
      ),
    ),
  ));
}

_callNumber() async{
  const number = '08592119XXXX'; //set the number here
  bool res = await FlutterSafePhoneDirectCaller.callNumber(number);
}
```

