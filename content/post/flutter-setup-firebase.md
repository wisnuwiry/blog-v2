+++
date = 2020-12-22T04:00:00Z
images = ["https://i.ibb.co/r4dGQC6/flutter-setup-firebase-banner.webp"]
series = ["Flutter Firebase Tutorial"]
tags = ["firebase", "flutter"]
title = "Flutter Tutorial Setup Firebase dan Implementasi Firebase Analytics"

+++
Halo semua kali ini aku mau bahas **Implementasi Firebase pada Flutter**, sebelumnya saya sudah membahas tentang Firebase bisa dilihat dulu [di sini](https://wisnuwiry.space/post/pengenalan-kelebihan-dan-kekurangan-firebase/ "Pengenalan, Kelebihan, Kekurangan dan Fitur-Fitur Tentang Firebase"). Pada tutorial ini adalah bagian atau series yang saya buat bernama [Flutter Firebase Tutorial](https://wisnuwiry.space/series/flutter-firebase-tutorial).

Sebelum memulai apa saja yang harus dipersiapkan?

Untuk yang saya bahas kali ini kan tentang Implementasi dan setup Firebase pada Flutter, Jadi Anda sebelum memulai implemtasi harus dipersiapkan beberapa hal ini diantaranya:

1. Flutter SDK
2. Text Editor / IDE (Visual Studio Code/ Android Studio)
3. Akun Google (untuk daftar firebase)

## Buat Project Firebase

Sebelum memulai pertama kali perlu kita buat project Firebase terlebih dahulu sebelum mulai membuat kode pada **Flutter**, bila Anda belum mempunyai akun Google silahkan buat akun terlebih dahulu, anggap saja sudah buat akun google semua ya :).

Untuk buat project firebase pertama kali buka website official firebase nya terlebih dahulu di [https://firebase.google.com/](https://firebase.google.com/ "https://firebase.google.com/"). Pada menu pilih **Go to Console**, dan buat project baru.

![Create Project Firebase](https://i.ibb.co/jMh4f7M/create-project-firebase.webp "Create Project Firebase")  
Kemudia setelah itu pilih atau input nama project sesuai dengan keinginan teman-teman.  
![Firebase Create Project name](https://i.ibb.co/7rRFYbH/create-project-name-firebase.webp)  
Setelah proses ini tinggal ikutin beberapa langkah-langkah yang Anda harus ikuti.

![Firebase Enable Analytics](https://i.ibb.co/n6t3sK8/firebase-enable-analytics.webp)

Jangan lupa, jika ingin mengaktifkan analisis penggunaan app kita nanti switch on **Aktifkan Google Analytics untuk project ini**. Sampai saat ini proses pembuatan project firebase telah berhasil. Langkah selanjutnya yaitu menambahkan aplikasi ke project kita.

## Buat Project Flutter

Setelah membuat project Firebase selesai langkah selanjutnya yaitu kita perlu membuat project Flutter yang akan kita daftarkan ke Firebase nanti. Untuk membuat project pada Flutter cukup mudah jika kita menggunakan cli untuk create project. Berikut contoh jika Anda membuat project menggunakan cli.

Buat project tanpa custom package name:

```bash
flutter create myapp
```

Atau jika anda ingin membuat project dengan custom package name, gunakan command ini:

```bash
flutter create --org com.wisnuwiry myapp
```

Ketika command tersebut dijalankan akan menghasilkan package name: `com.wisnuwiry.myapp` , jadi pada param `com.wisnuwiry` ini buatlah sesuai dengan kebutuhan Anda.

Tapi pada kali aku buat project dengan command tersebut.

## Menambahkan Aplikasi Android ke Firebase

Ketika ingin menambahkan project aplikasi Anda, pastikan buat project Flutter terlebih dahulu secara sukses.

### Tambahkan Flutter Android ke Firebase

Untuk menambahkan project Anda ke firebase buka terlebih dahulu console firebase anda, di https://console.firebase.google.com/ Kemudian pada dashboard overview klik Tambahkan App kemudian pilih app apa yang ingin Anda tambahkan pada kali ini aku bahas untuk bagian Android. Jika ingin menambahkan Aplikasi Android ke Firebase pilih ikon Android atau robot.

![](https://i.ibb.co/FDHj1rG/add-app-android-firebase.webp)

Kemudian ketika Anda pilih menu Android tadi akan diarahkan ke halaman ini, untuk mengisi beberapa data yang wajib Anda isi.

![](https://i.ibb.co/CzvLFq6/form-create-project-firebase.webp)

Seperti pada form tersebut untuk Nama App dan dan nama Package Name wajib di isi, sedangkan untuk SHA-1 bersifat optional, biasanya berfungsi untuk authentication, FCM, dll.

Untuk mengetahui nama package name pada project kita kita perlu check pada `AndroidManifest.xml` yang letaknya pada `android/app/src/main/AndroidManifest.xml`. Ketika udah buka file `AndroidManifest` cek package name Anda seperti ini:

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.wisnuwiry.myapp">
    ...
   
</manifest>
```

Seperti pada contoh ini, nama package namenya adalah `com.wisnuwiry.myapp`, package name tersebut masukkan pada firebase Anda.

### Download Config Android Firebase

Dan untuk mengisi sha-1 bisa anda baca selengkapnya di dokumentasi resminya https://developers.google.com/android/guides/client-auth.

Proses selanjutkan download file configuration firebase, dengan cara `next` button dari proses sebelumnya.

![](https://i.ibb.co/8sCCJKd/flutter-download-config-firebase.webp)

Kemudian download file tersebut, lalu taruh pada folder `android/app/` . Kemudian next sampai selesai proses setup firebase.

### Add Dependency di Flutter

Sebelum lanjut ke proses selanjutkan alangkah baiknya install terlebih dahulu dependency/plugin/library firebase yang diperlukan pada project flutter kita. Untuk langkah saat ini kita perlu install dependency **flutter_analytics** dan **flutter core**. Sebagai contoh berikut config pada `pubspec.yaml`:

```yaml {hl_lines=[11,12]}
name: myapp
description: A new Flutter project.
version: 1.0.0+1

environment:
  sdk: ">=2.7.0 <3.0.0"

dependencies:
  flutter:
    sdk: flutter
  firebase_analytics: ^6.3.0 # add this
  firebase_core: ^0.5.3 # add this

dev_dependencies:
  flutter_test:
    sdk: flutter

flutter:
  uses-material-design: true
```

> Jika terdapat dependency terbaru saran saya pakai lah yang paling baru, karena ketika saya buat artikel ini versi dependencynya seperti itu.

Setelah itu jalankan `flutter pub get` untuk mendownload dependencies yang kita install.

### Install Dependency Android Firebase

Untuk proses ini kita perlu setting secara manual pada android folder pada project Flutter kita.

Langkah pertama kita pasang pada file `android/build.gradle`. Perlu tambahkan kode ini:

```gradle {hl_lines=[4]}
buildscript {
  dependencies {
    // ... other dependencies
    classpath 'com.google.gms:google-services:4.3.3'
  }
}
```

Kemudian pasang kode ini di file `android/app/build.gradle`, pada akhir kode/baris dari kode pada file tersebut.

```gradle {hl_lines=[2]}
// ...
apply plugin: 'com.google.gms.google-services'
```

### Update minSDKVersion Android

Jangan lupa update terlebih dahulu minSDK version api android ke 21 atau yang lebih tinggi, karena untuk versi dibawah 21, belum ada multidex secara otomatis. Berikut contoh confignya:

```gradle {hl_lines=[4]}
android {
    defaultConfig {
        // ...
        minSdkVersion 21 // update this
        targetSdkVersion 28
        multiDexEnabled true
    }
}
```

## Initialize Firebase Flutter

Untuk menginisialisasikan project kita ke flutter supaya bisa dikenali oleh spesifik platform/native perlu kita initialize terlebih dahulu. Untuk menginisialisasi flutter firebase perlu menambahkan beberap kode pada file `lib/main.dart` ini:

```dart {hl_lines=[2, 4, 5, 7]}
import 'package:flutter/material.dart';
import 'package:firebase_core/firebase_core.dart';

void main() async {
  WidgetsFlutterBinding.ensureInitialized();

  await Firebase.initializeApp();

  runApp(MyApp());
}
```

Setelah proses tadi selesai coba jalankan project flutter Anda dengan command `flutter run` jika menggunakan cli.

Untuk check apakah setup sudah berhasil atau tidak cek kembali di console firebase, dan tunggu beberapa saat sampai data di dashboard tersedia.

Untuk hasil kode belajar kali ini udah tersedia di github bisa Anda cek

{{<button url="//github.com/wisnuwiry/myfirebase-app/tree/setup-firebase"  text="Github">}}

Cukup sekian tutorial kali ini, semoga bermanfaat :)