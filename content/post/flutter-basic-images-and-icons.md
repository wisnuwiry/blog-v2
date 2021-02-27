+++
date = 2021-02-27T15:07:00Z
featured = false
images = ["https://i.ibb.co/kXbcKbV/Poster-Blog.png"]
series = ["Flutter Basic"]
tags = ["flutter", "basic"]
title = "Flutter Basic Images and Icons"

+++
Membuat design User Interface yang bagus dang menarik pada aplikasi Flutter Anda dengan menampilkan beragam gambar dan icon? Anda tidak perlu masalah dengan implementasinya, di **Flutter** semuat tersebut di dukung secara penuh oleh **Flutter SDK**.

Pada artikel kali ini Saya akan bahas beberapa tentang Images(Gambar) dan Icons yang secara default sudah di sediakan oleh Flutter SDK.  Berikut beberapa penjelasan-penjelasnya:

## Images

{{<youtube 7oIAs-0G4mw>}}

Ketika membuat App/aplikasi pasti ada kalanya kita perlu menampilkan sebuah gambar dari berbagai sumber yang ingin kita tampilkan kepada user aplikasi kita. Pada **Flutter** untuk menampilkan gambar kita dapat menampilkan dari berbagai sumber: `assets`, `network`, `file`, dan `memory`.

Pada Flutter sudah tersedia **Widget** yang dapat/bisa menampilkan gambar dari berbagai sumber yaitu bernama `Image` , widget `Image` perlu [ImageProvider](https://api.flutter.dev/flutter/painting/ImageProvider-class.html "Flutter ImageProvider") sebagai object yang menentukan gambar tersebut berasal dari mana ex: asset, network.

Di flutter SDK ekstensi gambar yang sudah didukung tanpa library tambahan yaitu: **JPG**, **PNG**, **WEBP**, **JPEG**, **GIF**, **BMP**, dan **WBMP**.

Berikut contoh dan penjelasan dari beberapa sumber render image di flutter:

### Image Assets

Dimana pada sumber ini kita dapat menampilkan data gambar yang ada pada aplikasi kita yang sebelumnya kita sudah dafatarkan terlebih dahulu pada `pubspec.yaml`. Pada Image asset ini cocok sekali jika Anda ingin menampilkan data secara private(hanya di bisa ditampilkan di aplikasi Anda). Misal jika ingin menampilkan gambar logo pada aplikasi Anda, tapi inginnya aplikasi tersebut bisa berjalan secara offline.

Image assets ini menggunakan class [AssetImage](https://api.flutter.dev/flutter/painting/AssetImage-class.html) sebagai provider image yang berasal/dari turunan class `ImageProvider`. Pada Flutter jika implementasi Image yang berasal dari assets, Anda perlu gunakan widget `Image` dengan factory `assets`.  Secara default pada Flutter jika menampilkan gambar dari assets akan otomatis di atur oleh Flutter tentang pixel density untuk resolusi gambar.

Terus gimana cara implementasinya?

1. Pertama Anda wajib daftarkan lokasi `assets` gambar Anda di `pubspec.yaml`

   Daftarkan lokasi asset pada pubspec.yaml dengan posisi yang tepat, lokasi `assets` property berada dalam child `flutter` property di pubspec, [more info](). Berikut contohnya:

   ```dart
    flutter:
      assets:
      - assets/my_icon.png
      - assets/background.png   
   ```
2. Implement code

   ```dart
   Image.asset('assets/my_icon.png');
   
   // Or
   
   Image(
      image: AssetImage('assets/my_icon.png'),
    );
   ```

   Dimana `assets/my_icon.png` tersebut adalah posisi/lokasi file assets gambar pada project Anda.

### Image Network

Jika Anda mempunyai aplikasi yang ingin menampilkan data gambar yang dynamic, Anda cocok sekali gunakan metode ini, selain lebih scalable `ImageNetwork` ini bisa lebih hemat resource yang membuat ukuran aplikasi kita jadi lebih besar.

Dan di Flutter ketika render widget gambar yang berasal dari network/jaringan secara default disimpan di cache, untuk meningkatkan performa rendering berikutnya. Widget image network ini menggunakan class [NetworkImage](https://api.flutter.dev/flutter/painting/NetworkImage-class.html) sebagai provider image yang berasal/dari turunan class `ImageProvider`. Anda dapat menampilkan gambar dari internet dengan widget `Image` saja, ataupun dari fatory nya `Image` yaitu `Image.network` supaya lebih simple. Untuk menampilkan gambar dari internet kita perlu/butuh url gambar yang valid. Berikut contohnya:

```dart
Image.network('https://flutter.github.io/assets-for-api-docs/assets/widgets/owl-2.jpg');

// OR

Image(
  image: NetworkImage('https://flutter.github.io/assets-for-api-docs/assets/widgets/owl-2.jpg'),
);
```

### Image File

Pada metode ini Anda dapat menampilkan gambar dari storage/penyimpanan di device, Misal jika user ingin menampilkan foto dari galeri, maupun external storage.

Jika Anda menggunakan/menampilkan gambar di internal/external storage yang status lokasi gambarnya tersebut di luar posisi instalasi aplikasi, maka pada Android Anda perlu menambahkan permission/izin untuk akses file tersebut. Untuk permissionnya yaitu: `android.permission.READ_EXTERNAL_STORAGE`.

Widget image network ini menggunakan class [FileImage](https://api.flutter.dev/flutter/painting/FileImage-class.html) sebagai provider image yang berasal/dari turunan class `ImageProvider`. Anda dapat menampilkan gambar dari file dengan widget `Image` saja, ataupun dari fatory nya `Image` yaitu `Image.file` supaya lebih simple. Berikut contoh implementnya:

```dart
Image.file(File('/paht/your/file/image.png'));

// OR

Image(
   image: FileImage(File('/paht/your/file/image.png')),
);
```

### Image Memory

Pada metode ini memungkinkan Anda menampilkan gambar dari byte. Untuk bisa menampilkan gambar dari memory Anda perlu mengubah type data Anda ke dalam [Unit8List](https://api.flutter.dev/flutter/dart-typed_data/Uint8List-class.html) sebagai parameter data image.

> **Note:** saat ini Flutter untuk menampilkan gambar dari byte (binary) hanya dari compress dengan format PNG saja.

Contoh:

```dart
Image.memory(YOUR_BYTE_IMAGE);
```

### Image Properties

Terdapat beberapa parameter properties yang dapat Anda mengkustom Widget gambar Anda. Berikut penjelasnya:

| Params | Description |
| --- | --- |
| width | Untuk mengatur ukuran lebar pada gambar |
| height | Untuk mengatur ukuran tinggi pada gambar |
| color | Jika tidak kosong maka akan memaksa/blend gambar tersebut menjadi satu warna param tersebut |
| fit | Untuk mengatur fit pada gambar tersebut misal cover, contain, fill, dll |
| alignment | Untuk mengatur alignment/posisi rata-rata pada gambar tersebut |
| filterQuality | Untuk mengatur qualitas gambar pada saat rendering widget |

## Icons

**Icons** pada Flutter berbasis font, mirip seperti beberapa font icon yang terdapat pada Web misalnya: FontAwesome, MaterialIcons, dll. Pada Flutter icon di render dengan glyph dari class [IconData](https://api.flutter.dev/flutter/widgets/IconData-class.html). Pada Flutter sudah terdapat beberapa font icon yang sudah diterapkan ketika kita membuat project starter dari flutter. Untuk menampilkan icon di Flutter kita dapat menggunakan Widget `Icon` dengan parameter `IconData` sebagai resource font iconnya. Font icon tersebut yaitu `MaterialIcons` dan `CupertinoIcons`. Tapi memungkinkan juga Anda bisa custom icon sendiri. Berikut penjelasnya:

### Material Icons

Pada Flutter ketika kita membuat project sudah tersedia icon Material yang di taruh dalam Flutter SDK. Untuk melihat daftar-daftar icon yang ada di Flutter(Material Icons) bisa lihat website resminya [Material Design Icon](https://material.io/resources/icons/). Pada Flutter untuk icon Material di simpan di class bernama `Icons` class `Icons` berasal dari package material di **Flutter SDK**. Berikut contoh implementasinya:

```dart
import 'package:flutter/material.dart';

Row(
  mainAxisAlignment: MainAxisAlignment.spaceAround,
  children: const <Widget>[
    Icon(
      Icons.favorite,
      color: Colors.pink,
      size: 24.0,
      semanticLabel: 'Text to announce in accessibility modes',
    ),
    Icon(
      Icons.audiotrack,
      color: Colors.green,
      size: 30.0,
    ),
    Icon(
      Icons.beach_access,
      color: Colors.blue,
      size: 36.0,
    ),
  ],
)

```

**Result:** ![](https://flutter.github.io/assets-for-api-docs/assets/widgets/icon.png)

### Cupertino Icons

**Cupertino Icons** ini yaitu sebuah icon yang sebelumnya tersedia hanya untuk platform nya IOS/MacOS. Karena Flutter ini adalah framework yang support multi platform, yang mampu menyesuaikan sesuai platform tersebut. Untuk mendapatkan `IconData` di Flutter Anda perlu import `flutter/cupertino` karena `CupertinoIcons` bagian dari itu. Untuk melihat daftar icon yang tersedia bisa lihat di https://flutter.github.io/cupertino_icons/. Dan untuk implementnya seperti ini:

```dart
import 'package:flutter/cupertino.dart';

Row(
  children: [
    Icon(
      CupertinoIcons.ant_fill,
      size: 20,
      color: Colors.amber,
    ),
    Icon(
      CupertinoIcons.airplane,
      size: 20,
      color: Colors.pink,
    ),
    Icon(
      CupertinoIcons.home,
      size: 20,
      color: Colors.cyan,
    ),
  ],
)
```


### Custom Icon

Di Flutter ini Anda dapat membuat sendiri icon sesuai dengan keinginan, misal jika Anda ingin membuat icon Home yang lebih unik, dan tidak ada di `MaterialIcons` maupun `CupertinoIcon` Anda dapat buat sendiri icon tersebut dari SVG ke font icon dengan bantuan tool https://www.fluttericon.com/. 