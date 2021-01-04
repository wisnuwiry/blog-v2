+++
date = 2020-11-07T17:00:00Z
tags = ["flutter", "snippet", "tips"]
title = "Cara Mudah Menghilangkan Banner Debug di Flutter"

+++
Ketika kita membuat sebuah project **Flutter** secara default ketika di debugging/run akan menampilkan sebuah banner debug yang berada di samping atas seperti ini:

![Flutter Debug Banner](https://i.ibb.co/Jd1ZSwr/debug-banner-flutter.png "Flutter Debug Banner")

Untuk menghilangkan/menghapus banner debug tersebug cukup mudah sekali, dengan kasih param debugShowCheckedModeBanner: false pada Widget **MaterialApp**, berikut contoh lengkapnya:

```dart
return MaterialApp(
  title: 'Flutter Demo',
  theme: ThemeData(
    primarySwatch: Colors.blue,
    visualDensity: VisualDensity.adaptivePlatformDensity,
  ),
  debugShowCheckedModeBanner: false,  // Add this
  home: MyHomePage(title: 'Flutter Demo Home Page'),
);
```

> Secara default ketika kita release mode/build jadi APK debug banner akan otomatis hilang dengan sendirinya.

Berikut hasilnya:

![Flutter Remove Debug Banner](https://i.ibb.co/ssbx2g5/hide-debug-banner-flutter.png "Flutter Remove Debug Banner")