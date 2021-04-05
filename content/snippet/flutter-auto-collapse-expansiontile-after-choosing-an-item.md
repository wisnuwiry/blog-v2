+++
date = 2021-04-05T00:00:00Z
featured = false
images = []
series = []
tags = ["tips", " snippet"]
title = "Flutter Auto Collapse ExpansionTile After Choosing an Item"
toc = false

+++
Membuat beberapa `ExpansionTile` ketika di klik salah satu item maka item yang di klik tersebut akan melihat bagian detail, sebaliknya item yang lain maka akan menciut/menutup bagian detailnya.

Di Flutter ketika Widget tersebut ada perubahan `Key` maka widget tersebut akan rebuild. Ini bisa kita manfaatkan seperti tujuan kita.

Mari langsung ke studi kasus pada kodenya.

```dart
int _selectedCode = 0;
```

Variable tersebut kita gunakan sebagai value/intial item yang item nya tersebut dan mode detail.

Kemudian buat Widget `ListView.builder` sebagai widget yang menampung daftar/list item `ExpansionTile` berikut codenya:

```dart
ListView.builder(
  key: Key('selected $_selectedItem'),
  itemBuilder: (context, index) {
    return ExpansionTile(
      key: Key(index.toString()), //attention
      initiallyExpanded: index == _selectedItem, //attention
      title: Text('Item $index'),
      children: <Widget>[
        Padding(
          padding: EdgeInsets.all(25.0),
          child: Text(
            'DETAİL $index \n' +
            'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
          ))
      ],
      onExpansionChanged: (isOpen) {
        if (isOpen) {
          setState(() {
            _selectedItem = index;
          });
        }
      },
    );
  },
  itemCount: 20,
),
```

`Key` yang ada di Widget `ListView.builder` berfungsi ketika ada perubahan item yang di klik sekarang maka akan rebuild widget. Dan untuk Key di `ExpansionTile` untuk menandakan unik itemnya tersebut.

Dan untuk callback method `onExpansionChanged` berfungsi jika ada perubahan di Widget `ExpansionTile` akan melakukan fungis apa, dalam kasus ini saya menggunakannya untuk merubahan state selectedItem jadi yang di klik sekarang.

Untuk full contoh kodenya bisa lihat di sini:

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      debugShowCheckedModeBanner: false,
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  final String title;
  MyHomePage({Key? key, required this.title}) : super(key: key);

  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _selectedItem = 0;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title),
      ),
      body: 
      ListView.builder(
        key: Key('selected $_selectedItem'),
        itemBuilder: (context, index) {
          return ExpansionTile(
            key: Key(index.toString()), //attention
            initiallyExpanded: index == _selectedItem, //attention
            title: Text('Item $index'),
            children: <Widget>[
              Padding(
                padding: EdgeInsets.all(25.0),
                child: Text(
                  'DETAİL $index \n' +
                  'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                ))
            ],
            onExpansionChanged: (isOpen) {
              if (isOpen) {
                setState(() {
                  _selectedItem = index;
                });
              }
            },
          );
        },
        itemCount: 20,
      ),
    );
  }
}
```

**Demo:**

{{< rawhtml >}} </br> <iframe src="https://dartpad.dev/embed-flutter.html?id=c7fda0c53a705fc48a1e44116c9ffbc1&null_safety=true&theme=dark" style="width:100%;height:500px; border: none;">      </iframe>{{< /rawhtml >}}