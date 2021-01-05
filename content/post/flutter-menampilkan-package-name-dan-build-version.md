---
date: 2021-01-04T17:00:00+00:00
images:
- https://i.ibb.co/Km6h5Ym/Flutter-Package-Info-Poster-Blog.png
series: []
tags:
- library
- flutter
title: Flutter Menampilkan Package Name dan Build Version

---
Ketika membuat sebuah aplikasi Flutter kadang perlu juga kita mengetahui informasi dari native platform misal untuk mengetahui beberapa informasi tentang versi build sekarang dan package name.

Misal jika Anda ingin implementasi cek versi terbaru aplikasi Anda yang digunakan oleh user, sudah pasti Anda perlu cek terlebih dahulu versi aplikasi yang digunakan user sekarang itu berapa, dan aplikasi terbaru itu berapa.

Untuk implementasi ambil data package name dan version dari Flutter kita tidak perlu manual intregrasikan per item plaform misal dalam kasus ini Android dan IOS. Sekarang pada https://pub.dev telah menyediakan library untuk mengetahui informasi app dari native platform yang bernama **package_info**. Untuk mengetahui beberapa informasi mengenai packageinfo bisa lihat di [offical documentasinya](https://pub.dev/packages/package_info). Pada saat ini (ketika saya tulis artikel ini) library ini hanya support pada platform Android & IOS saja.

## Fitur Package Info

Ada beberapa fitur yang tersedia pada library ini yang dapat mempermudah Anda dalam pengerjaan. Berikut fitur-fiturnya:

### 1. Get App Name

Fitur ini memungkinkan Anda panggil nama aplikasi/app pada native platform. Misal jika nama aplikasi Anda adalah **My Portfolio**, dimana ketika di Android biasanya ditaruh pada bagian **Manifest.xml** di label property. Dan pada IOS `CFBundleDisplayName`.

### 2. Get Package Name

Fitur ini memungkinkan untuk ambil package name / App Id dari native plaform Android/IOS. Pada package name bisanya berbentuk seperti nama domain. Contoh sample package name: `com.domain.app`. Pada IOS disebut dengan `bundleIdentifier`.

### 3. Get Version Name

Version name atau disebut juga nama versi, ini nilainya berbentuk `String` bukan `int` version name ini biasanya penamaannya dipisah dengan `.` Contoh: `2.1.5`. Pada IOS disebut juga dengan `CFBundleShortVersionString`.

Pada flutter version name configurasi berada di file `pubspec.yaml`.

```yaml
version: 1.2.0+1
```

Pada contoh tersebut yang nilainya: `1.2.0` itu adalah version name, Jadi jika Anda ingin mengubah version name tinggal ubah aja nilai tersebut. Dan nilai setelah version name dan tanda (`+`) itu adalah version code. Pada contoh tersebut version codenya nilainya `1`.

### 4. Get Version Code

Fitur ini memungkinkan Anda memanggil angka versi aplikasi Anda saat ini. Berbeda dengan version Name, version code ini sifatnya/tipe datanya berbentuk int/integer. Pada version code ini version code wajib / selalu bertambah jika Anda mengupdate ke Play Store maupun App Store. Contoh version code: `100`. Pada IOS disebut dengan `CFBundleVersion`.

## Setup

Wajib perlu install/pasang library package_info ini, terlebih dahulu sebelum menggunakan fiturnya. Untuk install library pada `pubspec.yaml` tambahkan kode seperti ini:

```dart {hl_lines=[10]}
...
dependencies:
  flutter:
    sdk: flutter


  # The following adds the Cupertino Icons font to your application.
  # Use with the CupertinoIcons class for iOS style icons.
  cupertino_icons: ^1.0.0
  package_info: ">=0.4.3+2 <2.0.0"
```

Untuk version sesuaikan apa yang direkomendasikan oleh pemilik library tersebut, bisa cek di https://pub.dev/packages/package_info.

> Pada saat menulis artikel ini versi library belum sampai ke versi `1.0.0`, maka rekomendasi dari pemilik library menggunakan versi constraint seperti ini: `package_info: '>=0.4.3+2 <2.0.0'`

## Penggunaan dan Implementasi

Untuk implementasi import terlebih dahulu library `package_info` pada file dart yang Anda gunakan untuk ambil data dari native. Berikut contohnya:

```dart
import 'package:package_info/package_info.dart';
```

Dan untuk ambil data perlu panggil class `PackageInfo` terlebih dahulu, dan implementasikan ke user interface.

```dart
void _init() async {
    final _packageInfo = await PackageInfo.fromPlatform();

    setState(() {
      _appName = _packageInfo.appName; // Ambil Data Nama Aplikasi

      _versionName = _packageInfo.version; // Ambil Data Nama Versi

      _versionCode = _packageInfo.buildNumber; // Ambil Data Kode Versi

      _packageName = _packageInfo.packageName; // Ambil Data Package Name
    });
  }
```

Karena untuk ambil data ke native/plaform perlu method asynchronous maka perlu menggunakan `async` dan `await`.

Berikut contoh full kodenya:

```dart
import 'package:flutter/material.dart';
import 'package:package_info/package_info.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        visualDensity: VisualDensity.adaptivePlatformDensity,
      ),
      home: MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  MyHomePage({Key key, this.title}) : super(key: key);

  final String title;

  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  String _appName;
  String _versionName;
  String _versionCode;
  String _packageName;

  @override
  void initState() {
    _init();
    super.initState();
  }

  void _init() async {
    final _packageInfo = await PackageInfo.fromPlatform();

    setState(() {
      _appName = _packageInfo.appName; // Ambil Data Nama Aplikasi

      _versionName = _packageInfo.version; // Ambil Data Nama Versi

      _versionCode = _packageInfo.buildNumber; // Ambil Data Kode Versi

      _packageName = _packageInfo.packageName; // Ambil Data Package Name
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title),
      ),
      body: Column(
        children: [
          _buildItemTile('App Name', _appName),
          Divider(),
          _buildItemTile('Version Name', _versionName),
          Divider(),
          _buildItemTile('Version Code', _versionCode),
          Divider(),
          _buildItemTile('Package Name', _packageName),
          Divider(),
        ],
      ),
    );
  }

  Widget _buildItemTile(String key, String value) {
    return ListTile(
      title: Row(
        children: [
          Expanded(child: Text('$key : ')),
          Text(value ?? ''),
        ],
      ),
    );
  }
}
```

#### Result:

![Flutter Package Info](https://i.ibb.co/P4HJyHG/Flutter-package-info.png)

Untuk info detail lagi mengenai implementasinya bisa Anda lihat repo saya untuk contoh implementasinya di:

{{<button url="https://github.com/wisnuwiry/flutter-tutorial/tree/main/01.native_info"  text="Github">}}