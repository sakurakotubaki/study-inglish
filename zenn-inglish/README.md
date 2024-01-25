## 英語のドキュメントを作ってみた

Execute a simple program in Dart. The main function is the entry point to run the app.
```dart
void main() {
    print('Hi');
}
```

`initState ` is the method that is first executed when the page is called.
```dart
@override
void initState() {
  super.initState();
}
```

When the page is closed, `dispose` is executed and the state is destroyed.

```dart
@override
void dispose() {
  myObject.removeListener(_handleObjectChange);
  myObject.dispose();
  super.dispose();
}
```

`setState` manages the application's state and updates the screen.
```dart
void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
```

Default sample code of a Flutter project:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(title: 'Flutter Demo', home: CounterWidget());
  }
}

class CounterWidget extends StatefulWidget {
  const CounterWidget({super.key});

  @override
  _CounterWidgetState createState() => _CounterWidgetState();
}

class _CounterWidgetState extends State<CounterWidget> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child: Text('Count: $_counter'),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: const Icon(Icons.add),
      ),
    );
  }
}
```
