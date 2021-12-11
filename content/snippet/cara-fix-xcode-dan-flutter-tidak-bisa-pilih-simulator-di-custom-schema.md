+++
date = 2021-12-11T10:00:00Z
series = []
tags = ["tips", "xcode", "flutter"]
title = "Cara Fix Xcode dan Flutter Tidak Bisa Pilih Simulator di Custom Schema"
toc = false

+++
Pada saat saya develop aplikasi yang saya bangun dengan Flutter yang menerapkan flavor/schema untuk iOS, tidak tahu entah kenapa/sebabnya ketika saya jalankan mendapatkan error kurang lebih seperti ini:

```dart
Launching lib/main.dart on iPhone 13 Pro in debug mode...
lib/main.dart:1
Xcode build done.                                           43.6s
Failed to build iOS app
Error output from Xcode build:
↳
    --- xcodebuild: WARNING: Using the first of multiple matching destinations:
    { platform:iOS Simulator, id:dvtdevice-DVTiOSDeviceSimulatorPlaceholder-iphonesimulator:placeholder, name:Any iOS Simulator Device }
    { platform:iOS Simulator, id:320795B7-1385-4044-B442-87A9808936D9, OS:15.0, name:iPhone 13 Pro }
    { platform:iOS, id:dvtdevice-DVTiPhonePlaceholder-iphoneos:placeholder, name:Any iOS Device }
    { platform:iOS, id:00008101-000825EC3AE1001E, name:leobidoous iPhone, error:Device is busy (Making leobidoous iPhone ready for development, Processing cache files from device, Making the device ready for development) }
    ** BUILD FAILED **
Xcode's output:
↳
    Command PhaseScriptExecution failed with a nonzero exit code
    note: Using new build system
    note: Planning
    note: Build preparation complete
    note: Building targets in parallel
```

Kemudian saya coba delete schema yang tidak bisa pilih simulatornya dan saya buat ulang schema tersebut dan akhirnya bisa berjalan secara normal dan bisa pilih simulatornya.

Ini contoh gambar schema yang tidak bisa pilih simulator.
![Image Xcode Cannot Select Simulator Schema](https://i.ibb.co/t8vw7fG/IMAGE-2021-12-11-16-59-08.jpg)

Berikut langkah-langkah yang saya lakukan untuk menyelesaikan masalah saya diatas:

1. Pertama hapus schema/flavor apa saja yang tidak bisa di build/debug dengan alasan tidak bisa pilih simulator
2. Kilk icon app Anda yang ada di paling atas(Navigation bar) Xcode

   ![Image Xcode Manage Schema](https://i.ibb.co/LQ6zfCV/IMAGE-2021-12-11-17-17-15.jpg)
3. Cek semua schema yang tidak bisa pilih simulator kecuali `Runner` yangn nantinya akan kita hapus dan buat ulang.
4. Kemudian untuk menghapus schemanya klik menu `Manage Schema`
5. Kemudian hapus semua schema tadi yang tidak bisa memilih Simulator

   ![Image Xcode Delete Schema](https://i.ibb.co/WPSzgy7/IMAGE-2021-12-11-17-10-03.jpg)Dengan cara klik salah satu schema kemudian klik button minus(`-`) untuk menghapusnya
6. Kemudian buat ulang schema yang barusan dihapus, dan pastikan penamaannya sama persis yang dihapus tadi.

   ![Image Xcode Add Schema](https://i.ibb.co/fS1xnTm/IMAGE-2021-12-11-17-10-04.jpg)Untuk membuat schema baru klik icon plus(`+`) kemudian pilih targetnya `Runner` dan namanya sesuaikan denga yang sudaht terhapus.

Berikut hasil penyelesaian masalah Saya dan akhirnya bisa berjalan dengan normal dan dapat memilih simulator kembali di Xcode.

![Image Xcode Select Target Simulator](https://i.ibb.co/1TL47Zc/IMAGE-2021-12-11-17-10-00.jpg)