+++
date = 2022-05-12T01:00:00Z
featured = true
images = ["https://i.ibb.co/Vx67K0j/whats-new-flutter-v3-banner.webp"]
series = []
tags = ["flutter", "new-version", "flutter3"]
title = "Apa Yang Baru di Flutter Versi 3?"

+++
Horay...., akhirnya Flutter release major version lagi nih yaitu bukan siapa lagi versi 3 yang dikenalkan pada dini hari pada event [Google I/O](https://io.google/2022/ "Google I/O Event"). Di versi ini tentang macOS dan Linux Stable, Improve Performa, dan masih banyak lagi.

![Flutter Version 3](https://miro.medium.com/max/1400/1*K1Ru7PVkH74N56hgjBTjjQ.png)

Di sini saya akan membagikan informasi apa saja yang baru pada Flutter versi 3. Flutter versi terbaru yaitu versi 3 ini direlease pada tanggal 11 Mei 2022 pada event Google I/O. Jika ingin melihat eventnya bisa cek di youtube [Google I/O 2022](https://www.youtube.com/watch?v=nP-nMZpLM1A) untuk melihat tayangan ulangnya dan untuk introduction Flutter versi 3 resminya bisa lihat di [Medium](https://medium.com/flutter/introducing-flutter-3-5eb69151622f).

Langsung kita cuzz... cek apa saja yang baru pada release kali ini. Sebelumnya bisa cek juga catatan-catatan tiap release fitur barunya di website resmi [Flutter What's new](https://docs.flutter.dev/whats-new).

## Fitur Baru

Siapa bukan lagi yang kita harapkan ketika adanya major release di setiap versi yaitu fitur baru atau hal yang baru dan menarik untuk kita pelajari. Berikut dibawah ini daftar yang baru di versi ini yang sudah saya rangkum, semoga mudah dapat dipahami, hehe

### 1. Flutter macOS dan Linux sudah stable

Akhirnya flutter dapat merelease semua platform desktop sudah stable(stabil), yang sebelumnya Windows telah duluan menjadi versi stable di Flutter versi 2.10. Dan kali ini kita dapat membangun semua aplikasi desktop dalam versi stabilnya dengan Flutter.

#### a. Versi macOS sudah support Platform Menu

![](https://miro.medium.com/max/1400/1*kS32jfapJAvSyspT3aOH5A.gif "Flutter macOS Version PlatformMenu")

Seperti yang kita lihat di gambar tersebut di versi macOS dapat integrasi platform menu pada aplikasi Flutter, yang sebelumnya hal tersebut sangat sulit dilakukan kecuali membangun aplikasi menggunakan platform native macOS. Untuk cek contoh penggunaan bisa lihat di github [Example PlatformMenuBar](https://github.com/flutter/flutter/blob/master/examples/api/lib/material/platform_menu_bar/platform_menu_bar.0.dart "Example PlatformMenuBar Github").

#### b. Aksebilitas di Semua Desktop sudah adaptive

Sama seperti Android dan iOS ketika navigasi, widget, color, akan menyesuaikan platformnya. Begitu juga untuk yang versi desktop ini sudah dibekali adaptive/aksebilitas di navigasi, invert color, dan lainya

#### c. Support Apple Silicon atau M1

![](https://i.ibb.co/qNb9hpW/flutter-mac-os-apple-silicon-m1.png)Sebelumnya untuk versi mac flutter SDK sudah stabil tapi masih versi universal. Jadi jika memakai perangkan mac dengan prosessor M series( M1 ) belum dioptimalkan. Sekarang sudah terdapat versi SDK baru untuk versi Arm/M1nya.

### 2. Support Foldable Phone

Tidak asing lagi zaman sekarang, perangkat smartphone sudah berkembang semakin cepat dengan banyaknya inovasi, terutama foldable phone. Sudah banyak sekali vendor smartphone sekarang yang sudah mengimplementasikan teknologi foldable seperti Samsung, Microsoft, Realme, dll.

![Foldable Device Support Flutter](https://miro.medium.com/max/1400/0*z8pzEtJOPFv-xzw2)

Pada [MediaQuery](https://api.flutter.dev/flutter/widgets/MediaQuery-class.html) sekarang ditambahkan [DisplayFeature](https://api.flutter.dev/flutter/dart-ui/DisplayFeature-class.html) yang dapat memungkinkan kita mengetahui state screen/layar, dan juga tiap-tiap element engsel, lipatan dan potongan screen tersebut.

### 3. Image Decoding Web

Nih update ini sangat berpengaruh ketika sebelumnya sudah pernah membangun aplikasi web dengan flutter dengan banyaknya gambar yang dimuat. Pasti terasa sekali performa aplikasi tersebut sangat lemot dan jank. Di update kali ini ada improvement otomatis decode gambar pada kebanyakan browser modern sekarang. Bahkan performanya 2x lebih cepat dari sebelumnya.

#### a. Lifecycle pada Web App

Pada update ini ada lifecycle baru yang ditambahkan pada Web App Flutter yang dapat menambah fleksibilitas controll halaman dan juga membantu [lighthouse](https://developers.google.com/web/tools/lighthouse?hl=id) untuk mengalisa Performa aplikasi kita. Seperti case-case skenario Splash Screen, Loading Indicator dan juga Landing Page.

### 4. Flutter Casual Game Toolkit

![Flutter Casual Game Toolkit](https://storage.googleapis.com/cms-storage-bucket/675a58f90edf458780d5.png)

Flutter Casual Game Toolkit yaitu sebuah template dan resources dalam pembuatan Game yang dibangun dengan Flutter.
Dimana pada Flutter Casual Game Toolkit membantu sekali para developer game yang ingin migrasi ke Flutter atau bahkan developer yang belum pernah berpengalaman membuat game dapat mendapatkan resource yang lebih baik.

Di Flutter Casual Game Toolkit ini sudah include di templatenya:

1. Main menu
1. Sound & music
1. Ads
1. In-app purchases
1. Achievements and leader boards
1. Crashlytics support

### 5. Update Lainya

Pada update flutter v3 masih banyak lagi yang diberbarui maupun di tambahkan pada SDK Flutter. Dan juga setiap release fitur baru sering sekali flutter update performa SDK. Berikut ada beberapa update lainya:

- Update Dart SDK
- Improvement Material 3
- ThemeExtension
- Add
- Dan masih banyak lagi..

## Breaking Changes

Ketika sebuah software release dengan major version, sering kali berjumpa dengan **Breaking Changes**. Apa itu Breaking Changes? Breaking Changes adalah sebuah perubahan yang memungkinkan kode kita terjadi error dan perlu perlu migrasi dikodenya. Tapi jangan khawatir di dokumentasinya sudah terdapat dokumentasi untuk migrasi jika terjadi error setelah melakukan update SDK, bisa cek [Migration Guide](https://docs.flutter.dev/release/breaking-changes). Berikut adalah breaking changes yang ada pada update version 3:

- [Deprecated API dihapus setelah v2.10](https://docs.flutter.dev/release/breaking-changes/2-10-deprecations)
- [Page transitions diganti dengan ZoomPageTransitionsBuilder](https://docs.flutter.dev/release/breaking-changes/page-transition-replaced-by-ZoomPageTransitionBuilder)
- [Migrasi useDeleteButtonTooltip le deleteButtonTooltipMessage pada widget Chips](https://docs.flutter.dev/release/breaking-changes/chip-usedeletebuttontooltip-migration)
- [property toggleableActiveColor pada ThemeData dijadikan deprecated](https://docs.flutter.dev/release/breaking-changes/toggleable-active-color)
 

**Credits**:

* [https://medium.com/flutter/whats-new-in-flutter-3-8c74a5bc32d0](https://medium.com/flutter/whats-new-in-flutter-3-8c74a5bc32d0 "https://medium.com/flutter/whats-new-in-flutter-3-8c74a5bc32d0")
* [https://medium.com/flutter/introducing-flutter-3-5eb69151622f](https://medium.com/flutter/introducing-flutter-3-5eb69151622f "https://medium.com/flutter/introducing-flutter-3-5eb69151622f")
