---
title: "Instalasi Dart SDK"
date: 2023-02-01T23:31:23+07:00
draft: false
weight: 3
tags: ["dart", "install"]
chapter_start: "🔥 Instalasi"
images: [
    "/series/dart-dasar/install/featured.png"
]
---

Ingin membuat aplikasi dari bahasa pemrograman Dart, tapi belum tahu mulai dari mana? Yang pasti langsung pertama yaitu perlu menginstall semua kebutuhan baik SDK maupun tool sebagai alat bantu. Sebelumnya jika belum mengetahui Dart bisa baca [Pengenalan Dart](/series/dart-dasar/1-pengenalan/).

## Install SDK

**SDK** singkatan dari *Software Development Kit* yang berarti seperangkat alat pengembangan aplikasi/software dalam satu paket yang dapat diinstall. Kemudian untuk Dart SDK yaitu sekumpulan alat pengembangan yang dipakai dalam proses pengembangan aplikasi dari bahasa Dart. 

Tanpa adanya SDK semua kode yang telah dibuat tidak akan dapat diproses dan dijalankan di komputer, maka dari itu wajib untuk menginstall SDK sebelum menjalankan kode dartnya. 

Adapun untuk mengetahui spesifikasi minimum komputer yang diperlukan untuk menginstall Dart SDK bisa lihat [di sini](https://dart.dev/get-dart#system-requirements). Untuk langkah-langkah penginstalan bisa ikutin sesuai dengan sistem operasi Anda seperti dibawah ini:

### Windows

Untuk proses penginstallan Dart SDK pada sistem operasi windows, memerlukan beberapa step yaitu:

1. Download SDK dari website resminya https://dart.dev/get-dart/archive
1. Pilih OS windows kemudian pilih x64 jika komputer Anda 64 bit dan pilih IA32 jika 32 bit.
    
    ![Download Dart SDK from Dart.dev](/series/dart-dasar/install/download_sdk.png)
1. Tunggu sampai proses download selesai.
1. Setelah selesai download, kemudian extract file yang Dart SDK tadi ke folder `C:\Dev`, jika belum ada folder `Dev` bisa buat terlebih dahulu
1. Jadi posisi SDK nya yaitu di `C:\Dev\dart-sdk\`
1. Kemudian setelah mengextraks filenya, langkah selanjutnya yaitu menambahkan environment variable pada windows
1. Untuk menambah environment variable di windows, tekan logo windows kemudian ketikkan `env` *Edit on the system variables*
1. Setelah itu akan masuk ke screen Screen properties, kemudian klik button `Environment Variables` lanjut pilih path dan tekan button edit.

    ![Edit Environment Variable Dart on Windows](/series/dart-dasar/install/env1.jpeg)
1. Langkah selanjutnya tambahkan path sesuai dengan lokasi folder Dart SDK tadi, pada contoh ini lokasinya berada di `C:\Dev\dart-sdk\bin`

    ![Set Environment Variable Path Dart](/series/dart-dasar/install/env2.jpeg)
    
### Linux

Untuk proses penginstall Dart SDK ada beberapa langkah yang perlu diperhatikan diantaranya berikut ini:

1. Yang pertama buka aplikasi terminal yang ada di linux anda
1. Kemudian ikutin perintah ini pada terminal dan jalankan secara satu-persatu:

    {{<file "terminal" >}}
    ```bash
    $ sudo apt-get update
    $ sudo apt-get install apt-transport-https
    $ wget -qO- https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo gpg --dearmor -o /usr/share/keyrings/dart.gpg
    $ echo 'deb [signed-by=/usr/share/keyrings/dart.gpg arch=amd64] https://storage.googleapis.com/download.dartlang.org/linux/debian stable main' | sudo tee /etc/apt/sources.list.d/dart_stable.list
    ```

1. Setelah itu baru install Dart SDK lewat perintah ini

    {{<file "terminal" >}}
    ```bash
    $ sudo apt-get update
    $ sudo apt-get install dart
    ```
1. Proses install Dart SDK sudah selesai, langkah selanjutnya yaitu menambah environment variable untuk Dart SDK, supaya dapat diakses
1. Untuk menambah environment variable gunakan perintah seperti ini:

    {{<file "terminal" >}}
    ```bash
    $ echo 'export PATH="$PATH:/usr/lib/dart/bin"' >> ~/.profile
    ```

### Mac OS

Unutuk proses instalasi Dart SDK di mac os cukup mudah dibanding di OS(Operating System) yang lain. Adapun untuk langkah-langkahnya seperti ini:

1. Buka aplikasi terminal di Mac OS
1. Gunakan perintah seperti dibawah ini untuk menginstall
    
    {{<file "terminal" >}}
    ```bash
    $ brew tap dart-lang/dart
    $ brew install dart
    ```

> **Berlaku untuk semua OS:** Setelah proses penginstalan SDK, untuk validasi apakah sudah terinstall dengan benar dan tidaknya bisa mengecek versi dartnya lewat CMD atau terminal.

{{<file "terminal" >}}
```bash
$ dart --version
Dart SDK version: 2.18.6 (stable) (Tue Dec 13 21:15:14 2022 +0000) on "macos_arm64"
```

Kalau outputnya kurang lebih seperti itu, maka selamat Anda berhasil menginstall dart SDK.

## Setup Code Editor

Setelah menginstall SDK, kita pastinya memerlukan Code Editor. Apa sih itu Code Editor? Code Editor yaitu sebuah aplikasi yang dipakai untuk menulis skrip kode-kode yang nantinya akan dijalankan. Tanpa adanya kode editor kita tidak bisa membuat program aplikasi. Jadi kita perlu setup/menyiapkan code editor untuk memulai pemrograman dengan bahasa Dart.

Ada banyak sekali code editor yang dapat digunakan untuk menulis dan membuat aplikasi berbasis bahasa pemrograman Dart diantaranya:

1. [Visual Studio Code](https://code.visualstudio.com)
1. [Intellij IDEA](https://www.jetbrains.com/idea/)
1. [Android Studio](https://developer.android.com/studio)
1. [ViM](https://www.vim.org)
1. [Emacs](https://www.gnu.org/software/emacs/)
1. Dan masih banyak lagi

Akan tetapi pada kasus ini, saya rekomendasikan menggunakan [Visual Studio Code](https://code.visualstudio.com) sebagai code editor utama untuk menulis kode Dart. Karena di [Visual Studio Code](https://code.visualstudio.com) selain ringan code editor ini sangat friendly bagi pemula.

### Install Code Editor

> Jika sebelumnya sudah menginstall Visual Studio Code ini dihiraukan tidak masalah

Untuk download dan install Code Editor Visual Studio Code cukup mudah ikut langkah-langkah ini:

1. Pergi ke website resmi Visuak Studio Code https://code.visualstudio.com
1. Download sesuai sistem operasi Anda
1. Setelah selesai download, install Visual Studio Code seperti aplikasi biasa
1. Yeay... aplikasi terinstall

### Install Plugin

Setelah semua proses sudah selesai dilakukan Install SDK dan juga Code Editor. Hal yang perlu diperhatikan yaitu menginstall plugin yang diperlukan sesuai dengan kebutuhan pada aplikasi kode editor. Untuk install plugin yang wajib diinstall pada kasus ini untuk dart yaitu plugin dart untuk Visual Studio Code seperti ini. Untuk langkah-langkah install plugin seperti ini:

1. Buka aplikasi Visual Studio Code
1. Klik menu disamping kiri `Extensions` yang gambarnya seperti kubus
1. Ketika keyword dart pada daftar extensions
1. Klik install di extensi `dart`
1. Semua proses install sudah selesa... horay

![How to Install Plugin Dart on VS Code](/series/dart-dasar/install/install_plugin.png)

Untuk beberapa plugin yang saya rekomendasikan install, bisa lihat artikel lain yaitu [Rekomendasi Extension VS Code](/post/rekomendasi-extension-theme-font-vscode/).

**Refences:**

- https://dart.dev/get-dart

Setelah selesai menginstall dart di setup semua kebutuhan yang diperlukan, jangan lupa paneting semua perkembangan materi-materinya ya supaya tambah jago, hehe...
