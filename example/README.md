# story swiper example

Story swiper example application

## Using
```dart
import 'package:flutter/material.dart';
import 'package:storyswiper/storyswiper.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'StorySwiper Example',
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatefulWidget {
  MyHomePage({Key key}) : super(key: key);

  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  final List<Color> colors = [
    Colors.red,
    Colors.orange,
    Colors.yellow,
    Colors.green,
    Colors.blue,
    Colors.indigo,
    Colors.purple,
  ];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("StorySwiper Example"),
      ),
      body: Container(
        height: 340,
        child: StorySwiper.builder(
          itemCount: colors.length,
          aspectRatio: 2 / 3,
          depthFactor: 0.2,
          dx: 60,
          dy: 20,
          paddingStart: 32,
          verticalPadding: 32,
          visiblePageCount: 3,
          widgetBuilder: (index) {
            return Container(
              decoration: BoxDecoration(
                color: colors[index],
                borderRadius: BorderRadius.all(
                  Radius.circular(16),
                ),
              ),
            );
          },
        ),
      ),
    );
  }
}

```