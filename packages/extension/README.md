<img src="https://raw.githubusercontent.com/rbcprolabs/dart_plugins/master/packages/extension/media/hero.png" alt="Logo" width="100%" />

<p align="center">Package including lot helpers for easy developing on <a href="https://www.dartlang.org/" target="_blank">dart</a> language.</p>

<p align="center">
  <a href="https://pub.dartlang.org/packages/extension">
    <img src="https://img.shields.io/pub/v/extension.svg"
         alt="Pub">
  </a>
</p>

<p align="center">
  <a href="#key-features">Key Features</a> •
  <a href="#getting-started">Getting Started</a>
</p>

## Key Features

* Small weight
* Simple usage

## Getting Started

Import
```dart
import 'package:extension/extension.dart';

// Or by entity. Available: date, enum, string
import 'package:extension/<ENTITY NAME>.dart';
``` 

### String

```dart
// Capitalize first letter
'test'.capitalizeFirstLetter(); // return Test

// Check is email
'user@example.com'.isEmail; // return true
'qwerty'.isEmail; // return false

// Plural forms for russian words
plural(1, 'дом', 'дома', 'домов'); // returns дом
plural(2, 'дом', 'дома', 'домов'); // returns дома
plural(5, 'дом', 'дома', 'домов'); // returns домов
```

### Date

```dart
// Is today
DateTime.now().isToday; // return bool

// Is yesterday
DateTime.now().isYesterday; // return bool

// First day of month
DateTime(2018, 9, 30).firstDayOfMonth; // returns DateTime(2018, 9, 1)

// Last day of month
DateTime(2017, 3).lastDayOfMonth; // DateTime(2017, 3, 31)

// All days in month, DateTime array
DateTime(2017, 3).daysInMonth; // [DateTime(2017, 3, 1), DateTime(2017, 3, 2), ...]


assert(DateUtils.isSameWeek(DateTime(2017, 3, 5), DateTime(2017, 3, 6)));

// and more see api docs
```

### Enum

```dart
import 'package:extension/enum.dart';

// Enum value by string
enum AnyEnum {
  one,
  two,
  three,
}

final AnyEnum one = enumValueByString(AnyEnum.values, 'one'); // Returns AnyEnum.one
final AnyEnum one = enumValueByString(AnyEnum.values, 'qwerty', orElse: () => AnyEnum.two); // Returns AnyEnum.two

// Enum with value 
// assert(Meter.HIGH == 100);
// assert(Meter.HIGH is Meter);
class Meter<int> extends Enum<int> {
  const Meter(int val) : super (val);

  static const Meter HIGH = const Meter(100);
  static const Meter MIDDLE = const Meter(50);
  static const Meter LOW = const Meter(10);
}
``` 

And... all api reference [available here](https://pub.dev/documentation/extension/latest/)

