+++
date = 2020-11-28T17:00:00Z
images = ["https://i.ibb.co/Tv8mRcK/flutter-localization.webp"]
series = []
tags = ["tips", "localization", "flutter"]
title = "Membuat Localization Flutter dengan Extensions Flutter_Intl"

+++
_Bismillahirrahmannirrahiim,_ Pada kali ini aku akan membagikan pengalamanku membuat **Localization dan Translations di Flutter** dengan mudah pakai extensions. Sebelumnya saya telah membuat artikel lainya yang membahas tentang localization juga di Flutter, bisa lihat di [https://wisnuwiry.space/post/flutter-localization/](https://wisnuwiry.space/post/flutter-localization/ "https://wisnuwiry.space/post/flutter-localization/").

## Pengenalan

Pada kali yang aku bahas yaitu tentang Flutter_Intl sebagai extensions yang digunakan untuk auto generate localization. Pada extension bekerja dari format file `.arb` ke bahasa `dart`, supaya bisa dibaca oleh dart itu sendiri. Extension ini sangat cepat sekali untuk proses development, tanpa harus melakukan langkah yang banyak.

## Instalasi Extension

Untuk artikel kali aku akan buat/mencoba membuat localization di Flutter lebih mudah dan simple dengan menggunakan extensions. Untuk extensions yang saya maksud yaitu bernama **Flutter_Intl**, extension ini bisa dijalankan di **VS Code** maupun di **Android Studio**.

Untuk lihat selengkapnya tentang extensions berikut ini:

* [Android Studio]()
* [Visual Studio Code]()

Untuk info lebih mengenai install extensions/plugin bisa lihat selengkapnya untuk [VS Code]() untuk [Android Studio]().

## Buat Projek Baru

Sebelum memulai mencoba praktik, buat terlebih dahulu project baru Flutter, atau jika sudah tersedia project flutter, lewati langkap ini. Jika belum untuk membuat project baru gunakkan command berikut:

```bash
flutter create flutter_multi_bahasa
```

Untuk **flutter_multi_bahasa** tersebut adalah contoh nama projectnya, bisa juga jika Anda ingin membuat sesuai dengan keinginan.

Untuk info selengkapnya mengenai pembuatan project pada flutter bia lihat dokumentasi resminya di [https://flutter.dev/](https://flutter.dev/ "https://flutter.dev/").

## Configurasi Intl

Setelah buat projek langkah selanjutnya yaitu configurasi dan install dependency yang dibutuhkan. Untuk konfigurasinya seperti berikut ini:

**1. Install Dependency**

Dependency yang perlu di install yaitu `flutter_localizations`, dari flutter sdk, sebagai contohnya seperti ini:

```yaml {hl_lines=["11-12"]}
name: flutter_multi_bahasa
description: A new Flutter project.
version: 1.0.0+1

environment:
  sdk: ">=2.7.0 <3.0.0"

dependencies:
  flutter:
    sdk: flutter
  flutter_localizations:
    sdk: flutter
  cupertino_icons: ^1.0.0

dev_dependencies:
  flutter_test:
    sdk: flutter
flutter:
  uses-material-design: true
```

Jangan lupa setelah install dependency `pub get` terlebih dahulu, atau bisa dengan jalankan command:

```bash
flutter pub get
```

**2. Configurasi Material App**

Langkah selanjutnya yaitu perlu konfigurasi di Widget atau di MaterialApp kita terlebih dahulu. Untuk konfigurasi MaterialApp, secara default berada di file lib/main.dart, atau jika Anda sudah menggantinya bisa disesuaikan posisinya. Sebagai contoh berikut ini:

```dart {hl_lines=["1-4","14-20"]}
import 'package:flutter/material.dart';
import 'package:flutter_localizations/flutter_localizations.dart';

import 'generated/l10n.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return new MaterialApp(
      localizationsDelegates: [
        S.delegate,
        GlobalMaterialLocalizations.delegate,
        GlobalWidgetsLocalizations.delegate,
        GlobalCupertinoLocalizations.delegate,
      ],
      supportedLocales: S.delegate.supportedLocales,
      title: 'Flutter Demo',
      home: new MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}
```

Tambahkan beberapa line kode, seperti yang saya contohkan. Mungkin setelah menambahkan beberapa kode tersebut terdapat error, saat ini error tersebut biarkan saja dulu.

**3. Konfigurasi Localization**

Untuk konfigurasinya terdapat dalam file `pubspec.yaml`. Berikut beberapa contoh konfigurasinya:

```yaml {linenostart=21}
flutter_intl:
  enabled: true # Required. Must be set to true to activate the plugin. Default: false
  class_name: S # Optional. Sets the name for the generated localization class. Default: S
  main_locale: en # Optional. Sets the main locale used for generating localization files. Provided value should consist of language code and optional script and country codes separated with underscore (e.g. 'en', 'en_GB', 'zh_Hans', 'zh_Hans_CN'). Default: en
  arb_dir: lib/l10n # Optional. Sets the directory of your ARB resource files. Provided value should be a valid path on your system. Default: lib/l10n
  output_dir: lib/generated # Optional. Sets the directory of generated localization files. Provided value should be a valid path on your system. Default: lib/generated
  use_deferred_loading: false # Optional. Must be set to true to generate localization code that is loaded with deferred loading. Default: false
```

## Inisialisasi Flutter Intl

Supaya Extensions **Flultter Intl**, ini bekerja pada project Anda, perlu menginisialisasi project terlebih dahulu. Pada langkah ini pastikan dengan benar extension Flutter_Intl sudah terinstall dengan benar. Untuk **Android Studio** sama **Vs Code** ada sedikit perbedaan, berikut penjelasanya:

## VS Code

Untuk di VS Code cukup mudah, dengan klik tombol menu bar diatas, `View >> Command Pallete` atau cukup dengan ketikkan shortcut `Ctrl + Shift + P` untuk Windows dan Linux, dan Jika Mac Os `Commad + P`. Dan kemudian cari menu `Flutter Intl: Initialize`. Maka akan dengan otomatis di inisialisasi di project Anda.

## Android Studio

Untuk di Android Sudio ini untuk initialisasi project dengan extension/plugin Flutter_Intl ini, cukup pilih menu di Atas `Tools >> Flutter Intl >> Initialize for the project` . Tunggu sampai selesai. :)

Setelah selesai proses initialisasinya, secara default akan digenerate kan folder. `lib/l10n`, sebagai wadah menampung data localization degnan format `.arb` dan `lib/generated/` sebagai hasil generate kode dan file `.arb` ke dart. Semua hasil generate tersebut berasal dari config di `pubspec.yaml` yang telah dibuat.

***

## Menambahkan Dukungan Bahasa

Untuk menambahkan beberapa bahasa yang ingin kita tambahkan pada aplikasi anda, cukup gunakan menu `Flutter Intl: Add Locale`.

Untuk VS Code:

`View >> Command Pallete >> Flutter Intl: Add Locale`

Untuk Android Studio:

`Tools >> Flutter Intl >> Add Locale`

Isi sesuai dengan country / locale yang anda inginkan.

> **Note:**  Untuk konfigurasi di IOS perlu menambahkan sedikit konfigurasi lagi bisa Anda menambahkan bahasa lain. Berikut contohnya:

Untuk configurasi IOS berada pada file `ios/Runner/Info.plist`, dan sesuaikan code nya di folder `l10n`.

```xml
<key>CFBundleLocalizations</key>
<array>
    <string>en</string>
    <string>id</string>
    ...
</array>
```

## Buat Translasi

Untuk buat translasi kita buat dari format `.arb` yang berada pada folder, `l10n` sesuai konfigurasi anda sebelumnya. Pada format arb ini mirip sekali dengan format `json` jadi lebih familiar ketika menggunakanya. Sama seperti `json` `arb` juga mempunyai `key` dan `value`. Dimana key ini sebagai kata kunci yang akan kita gunakan nanti dan yang generatekan oleh extensions, sebagai nama `variable`, `key` pada semua bahasa yang di arb harus sama persis. Dan `value` nya ini sebagai output value pada masing-masing bahasa yang digunakan. Berikut contoh-contoh implementasinya.

1. Tanpa Plural  
   Yang dimaksud tanpa plural ini yaitu ketika kita panggil translation tidak perlu memerlukan parameter apapun. contoh:

   ```json
   {
   	"hello_world": "Hello World"
   }
   ```
2. Dengan Plural

   Untuk penggunaan plural pada `arb` file, cuma gunakan tanda kurang kurawal `{}` sebagai tanda tata letak parameter tersebut akan ditaruh. Dan parameter tersebut dynamic baik penamaan maupun valuenya, boleh terserah  kita.

   ```json
   {
   	"my_name": "My Name is {name}",
       "my_age": "My Age is {age} years old"
   }
   ```

   Ketika kita membuat sebuah translasi akan otomatis di generate kan oleh extension secara asynchronous, jadi tidak perlu repot-repot generate sendiri.

## Pemanggilan Translasi

Untuk pemanggilan translasi itu disesuikan dengan key dari `arb` file yang kita buat. Sebagai contoh jika saya buat key translasi itu: `"hello_world"` maka ketika panggil bisa kayak gini:

Ada dua cara ketika panggil translasi yaitu:

1. Panggil menggunakan context

   Contoh:

   ```json
   S.of(context).hello_world
   ```
2. Panggil tanpa context

   ```json
   S.current.hello_world
   ```

Dan jika anda menggunakan plural cara panggilnya seperti ini:

1. Ketika plural cuma satu param

   ```json
   S.current.my_name('Wisnu')
   ```
2. Ketika plural lebih dari satu param

   ```json
   S.current.profile('Wisnu', '17')
   ```

   Untuk contoh lengkapnya bisa lihat di github saya:

   {{<button url="//github.com/wisnuwiry/flutter_multi_language"  text="Source Code">}}

## Langkah Selanjutnya

Untuk langkah selanjutnya Anda bisa terapkan state management untuk menyimpan state, ketika ada perubahan bahasa, dan juga bisa diterapkan caching data setting bahasa menggunakan state management.

Sekian pembahasanku kali ini semoga bermanfaat :) 