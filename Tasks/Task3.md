
# Create button that changes color

```dart
import 'package:flutter/material.dart';  
  
void main() {  
  runApp(const MyApp());  
}  
  
class MyApp extends StatelessWidget {  
  const MyApp({super.key});  
  
  // This widget is the root of your application.  
  @override  
  Widget build(BuildContext context) {  
    return MaterialApp(  
      title: 'Flutter Demo',  
      theme: ThemeData(  
        primarySwatch: Colors.blue,  
      ),  
      home: const Home(),  
      debugShowCheckedModeBanner: false,  
    );  
  }  
}  
  
class Home extends StatefulWidget {  
  const Home({super.key});  
  
  @override  
  State<Home> createState() => _HomeState();  
}  
  
class _HomeState extends State<Home> {  
  bool isPressed = false;  
  @override  
  Widget build(BuildContext context) {  
    return Scaffold(  
      body: Center(  
        child: ElevatedButton(  
          style: ElevatedButton.styleFrom(  
              backgroundColor: isPressed ? Colors.black : Colors.blue),  
          onPressed: () {  
            setState(() {  
              isPressed = !isPressed;  
            });  
          },  
          child: Text('Press Here'),  
        ),  
      ),  
    );  
  }  
}
```

# Create Two Buttons that change color of Scaffold

```dart
import 'package:flutter/material.dart';  
  
void main() {  
  runApp(MyApp());  
}  
  
class MyApp extends StatelessWidget {  
  @override  
  Widget build(BuildContext context) {  
    return MaterialApp(  
      home: ColorChanger(),  
    );  
  }  
}  
  
class ColorChanger extends StatefulWidget {  
  @override  
  _ColorChangerState createState() => _ColorChangerState();  
}  
  
class _ColorChangerState extends State<ColorChanger> {  
  Color _backgroundColor = Colors.white; // Initial background color  
  
  void _changeColorToBlue() {  
    setState(() {  
      // Change the background color when button is pressed  
      _backgroundColor = Colors.blue;  
    });  
  }  
  
  void _changeColorToGreen() {  
    setState(() {  
      // Change the background color when button is pressed  
      _backgroundColor = Colors.green;  
    });  
  }  
  
  @override  
  Widget build(BuildContext context) {  
    return Scaffold(  
      backgroundColor: _backgroundColor,  
      appBar: AppBar(  
        title: Text('Change Background Color'),  
        centerTitle: true,  
      ),  
      body: Center(  
        child: Column(mainAxisAlignment: MainAxisAlignment.center, children: [  
          ElevatedButton(  
            onPressed: _changeColorToBlue,  
            child: Text('Change to blue'),  
          ),  
          SizedBox(height: 10),  
          ElevatedButton(  
            onPressed: _changeColorToGreen,  
            child: Text('Change to Green'),  
          ),  
        ]),  
      ),  
    );  
  }  
}
```

result 
![](https://i.imgur.com/2wIu3hS.png)

---
# Coffee Dashboard

```dart
import 'package:flutter/material.dart';  
  
void main() {  
  runApp(MyApp());  
}  
  
class MyApp extends StatelessWidget {  
  @override  
  Widget build(BuildContext context) {  
    return MaterialApp(  
        home: Scaffold(  
            appBar: AppBar(  
              title: Text('Main Title'),  
            ),  
            body: Column(children: [  
              RichText(  
                text: TextSpan(  
                    text: 'HOT DRINKS',  
                    style: TextStyle(  
                      fontSize: 22,  
                      color: Colors.red,  
                      fontWeight: FontWeight.bold,  
                    ),  
                    children: <TextSpan>[  
                      TextSpan(  
                        text: ' Partition',  
                        style: TextStyle(  
                            fontSize: 24,  
                            fontWeight: FontWeight.normal,  
                            color: Colors.black),  
                      ),  
                    ]),  
              ),  
              SizedBox(height: 10),  
              Container(  
                width: 250,  
                height: 100,  
                decoration: BoxDecoration(  
                  color: Colors.white,  
                  border: Border.all(  
                    color: Colors.black, // Border color  
                    width: 1,  
                    // Border thickness  
                  ),  
                  borderRadius: BorderRadius.circular(10),  
                ),  
                child: Row(  
                  mainAxisAlignment: MainAxisAlignment.center,  
                  children: [  
                    Image(  
                      image: NetworkImage(  
                          'https://static.vecteezy.com/system/resources/previews/027/308/934/original/cappuccino-with-ai-generated-free-png.png'),  
                      width: 100,  
                      height: 100,  
                      alignment: AlignmentDirectional(10, 0),  
                    ),  
                    SizedBox(  
                      width: 30,  
                    ),  
                    Column(  
                      mainAxisAlignment: MainAxisAlignment.center,  
                      children: [  
                        Text('cappuccino'),  
                        SizedBox(  
                          height: 30,  
                        ),  
                        Row(  
                          mainAxisAlignment: MainAxisAlignment.center,  
                          children: [  
                            Text('410 LE'),  
                            SizedBox(  
                              width: 10,  
                            ),  
                            Icon(Icons.favorite, size: 40, color: Colors.red),  
                          ],  
                        ),  
                      ],  
                    )  
                  ],  
                ),  
                margin: EdgeInsets.all(10),  
              ),  
              Container(  
                width: 250,  
                height: 100,  
                decoration: BoxDecoration(  
                  color: Colors.white,  
                  border: Border.all(  
                    color: Colors.black, // Border color  
                    width: 1,  
                    // Border thickness  
                  ),  
                  borderRadius: BorderRadius.circular(10),  
                ),  
                child: Row(  
                  mainAxisAlignment: MainAxisAlignment.center,  
                  children: [  
                    Image(  
                      image: NetworkImage(  
                          'https://static.vecteezy.com/system/resources/previews/027/308/934/original/cappuccino-with-ai-generated-free-png.png'),  
                      width: 100,  
                      height: 100,  
                      alignment: AlignmentDirectional(10, 0),  
                    ),  
                    SizedBox(  
                      width: 30,  
                    ),  
                    Column(  
                      mainAxisAlignment: MainAxisAlignment.center,  
                      children: [  
                        Text('cappuccino'),  
                        SizedBox(  
                          height: 30,  
                        ),  
                        Row(  
                          mainAxisAlignment: MainAxisAlignment.center,  
                          children: [  
                            Text('410 LE'),  
                            SizedBox(  
                              width: 10,  
                            ),  
                            Icon(Icons.favorite, size: 40, color: Colors.red),  
                          ],  
                        ),  
                      ],  
                    )  
                  ],  
                ),  
                margin: EdgeInsets.all(10),  
              ),  
              Container(  
                width: 250,  
                height: 100,  
                decoration: BoxDecoration(  
                  color: Colors.white,  
                  border: Border.all(  
                    color: Colors.black, // Border color  
                    width: 1,  
                    // Border thickness  
                  ),  
                  borderRadius: BorderRadius.circular(10),  
                ),  
                child: Row(  
                  mainAxisAlignment: MainAxisAlignment.center,  
                  children: [  
                    Image(  
                      image: NetworkImage(  
                          'https://static.vecteezy.com/system/resources/previews/027/308/934/original/cappuccino-with-ai-generated-free-png.png'),  
                      width: 100,  
                      height: 100,  
                      alignment: AlignmentDirectional(10, 0),  
                    ),  
                    SizedBox(  
                      width: 30,  
                    ),  
                    Column(  
                      mainAxisAlignment: MainAxisAlignment.center,  
                      children: [  
                        Text('cappuccino'),  
                        SizedBox(  
                          height: 30,  
                        ),  
                        Row(  
                          mainAxisAlignment: MainAxisAlignment.center,  
                          children: [  
                            Text('410 LE'),  
                            SizedBox(  
                              width: 10,  
                            ),  
                            Icon(Icons.favorite, size: 40, color: Colors.red),  
                          ],  
                        ),  
                      ],  
                    )  
                  ],  
                ),  
                margin: EdgeInsets.all(10),  
              ),  
            ])));  
  }  
}
```

result 

![](https://i.imgur.com/LJJz2Fw.png)


# Task 1

```Dart 
import 'package:flutter/material.dart';  
  
void main() {  
  runApp(MyApp());  
}  
  
class MyApp extends StatelessWidget {  
  @override  
  Widget build(BuildContext context) {  
    return MaterialApp(  
        home: Scaffold(  
            appBar: AppBar(  
              leading: Row(  
                mainAxisSize: MainAxisSize.min,  
                children: [  
                  IconButton(  
                    icon: Icon(Icons.more_vert), // Dash icon  
                    onPressed: () {  
                      // Action for the first icon  
                    },  
                  ),  
                ],  
              ),  
              title: Text(  
                'Task 1',  
                style: TextStyle(color: Colors.white),  
              ),  
              centerTitle: true,  
              backgroundColor: Colors.indigo,  
            ),  
            body: Row(  
              children: [  
                Padding(  
                  padding: const EdgeInsets.all(8.0),  
                  child: Column(  
                    children: [  
                      Container(  
                          padding: EdgeInsets.all(20.0),  
                          width: 100,  
                          height: 100,  
                          decoration: BoxDecoration(  
                            color: Colors.red,  
                          )),  
                      SizedBox(  
                        height: 200,  
                      ),  
                      Container(  
                          padding: EdgeInsets.all(20.0),  
                          width: 100,  
                          height: 100,  
                          decoration: BoxDecoration(  
                            color: Colors.red,  
                          )),  
                    ],  
                  ),  
                ),  
                SizedBox(width: 100,),  
                Padding(  
                  padding: const EdgeInsets.all(8.0),  
                  child: Column(  
                    children: [  
                      Container(  
                          padding: EdgeInsets.all(20.0),  
                          width: 100,  
                          height: 100,  
                          decoration: BoxDecoration(  
                            color: Colors.yellow,  
                          )),  
                      SizedBox(  
                        height: 200,  
                      ),  
                      Container(  
                          padding: EdgeInsets.all(20.0),  
                          width: 100,  
                          height: 100,  
                          decoration: BoxDecoration(  
                            color: Colors.deepOrange,  
                          )),  
                    ],  
                  ),  
                )  
              ],  
            ) // Add a body to see something under the AppBar  
            ));  
  }  
}
```
result

![](https://i.imgur.com/Y16bv6k.png)


