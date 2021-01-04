+++
date = 2020-11-28T17:00:00Z
tags = ["snippet", "flutter", "tips"]
title = "Cara Build APK dan AppBundle Release di Flutter"

+++
Ketika ingin membuild kode dari kode **dart**, dan dari Project **Flutter**, ada beberapa command untuk membuild jadi apk maupun appbundle.

## Build APK

Untuk membuild jadi APK terdapat dua metode yaitu dengan Bundle (semua versi processor ARM) maupun secara split per type processor.

## 1. Build APK Bundle

Untuk membuild APK bundle atau universal APK, yang dapat di install untuk berbagai tipe processor Android. Pada metode ini ukuran APK jadi lebih besar dan tidak direkomendasikan jika ingin di publish ke Play Store. Untuk membuild APK jadi APK universal caranya cukup ketikkan command berikut pada folder project Flutter Anda:

a. Build APK Release

```bash
flutter build apk
```

Secara default  ketika build APK Flutter di mode release.

b. Build APK Debug

Kalaupun ingin di mode debug bisa juga tambahin prefix `--debug`. Contoh:

```bash
flutter build apk --debug
```

c. Build APK dengan Flavor

Jika Anda menggunakan flavor bisa tambahin prefix `--flavor` berikut contohnya:

```bash
flutter build apk --flavor flavor_name
```

Untuk `flavor_name` itu diisi dengan nama flavor App Anda.

d. Build Apk dengan target main file

Secara default ketika kita build main file adalah di `lib/main.dart`. Tapi tidak menutup kemungkinan jika Anda mempunyai main file yang ditempat lain, misal jika pakai flavor bisa berbagai type file main. Berikut contoh command nya:

```bash
flutter build apk -t lib/main-dev.dart
```

Untuk prefix `-t` itu artinya path file main file Flutter Anda.

## 2. Build APK split per ABI

Untuk build apk dengan split per abi ataupun build apk secara terpisah ini bisa mengurangi ukuran APK ketika install, tapi pada metode ini tidak direkomendasikan jika ingin di publish ke **Play Store**, dan Juga ketika Anda tidak tahu apa tipe processor HP Anda mending pakai build universal APK saja. 

Untuk build apk split per abi kita cukup tambahkan prefix `--split-per-abi` pada build command. Berikut contohnya:

```bash
flutter build apk --split-per-abi
```

Atau jika ingin memilih beberapa saja tipe processor yang ingin di build gunakan command berikut ini:

```bash
flutter build apk --target-platform android-arm,android-arm64,android-x64 --split-per-abi
```

Untuk target apa saja yang ingin di build pisahkan dengan tanda koma `,` .

Selebihnya custom tentang Flavor, main file path, dll sama persis dengan Build APK universal.

## Build AppBundle

Build jadi AppBundle atau app dengan extensions `.aab` , build kode Flutter jadi semua type jadikan satu, dan pada build ini, tidak bisa diinstall langsung ke device HP, melainkan harus di publish terlebih dahulu ke play store. Pada metode ini yang paling direkomendasikan ketika ingin mempublish app ke Play Store.

Untuk membuild app jadi appBundle cukup ketikkan command berikut:

```bash
flutter build appbundle
```

Selebihnya prefix, dan custom sama seperti build APK biasa.