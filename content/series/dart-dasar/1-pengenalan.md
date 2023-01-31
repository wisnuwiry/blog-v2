---
title: "Pengenalan Dart"
date: 2023-01-31T19:03:23+07:00
draft: false
weight: 1
chapter_start: "🚨 Pengenalan"
tags: ["dart", "introduction"]
images: [
    "/series/dart-dasar/featured_full.webp"
]
---

Pernahkan Anda mendengar tentang Dart programming language? Jika benar memang Dart sudah sangat populer untuk sekarang ini. Dart saat ini salah-satu bahasa pemrograman yang sedang populer/hype saat-saat ini. Jadi sangat worth it jika Anda mempelajari bahasa pemrograman Dart, So tetap ikutin series ini untuk mempelajari Dart secara keseluruhan.

## Apa itu Dart?

![Dart Logo](https://dart.dev/assets/img/logo_lockup_dart_horizontal.png)

**Dart** adalah salah satu bahasa pemrograman *Open Source* yang dibuat oleh Google team, dengan berbasis *Object Oriented Programming* (OOP). Dart dibuat untuk membangun aplikasi yang optimal dan mudah dan mampu berjalan di berbagai macam platform. Karena salah satu tujuan utama dari dart dibangun yaitu supaya mampu menunjang produktifitas dalam proses pengembangan project yang mampu berjalan di multi platform dengan kode yang sama.

Salah satu alasan utama banyak orang mempelajari bahasa Dart yaitu untuk mempelajari atau menggunakan [Flutter](https://flutter.dev), dimana di Flutter kita dapat membangun aplikasi ke berbagai macam platform seperti android, ios, web, dan desktop hanya dengan satu basis kode.

Bahasa pemrograman Dart pertama kali diperkenalkan di publik (release) dengan versi 1.0 pada tahun 14 November 2013. Jadi sampai sampai saat dart sudah berusia 5 tahun lebih sejak release pertama kalinya. 

## Alasan belajar Dart

Ada banyak sekali alasan kenapa perlu belajar Dart setidaknya mulai sekarang, ini adalah beberapa alasan-alasan bisa di perhitungkan:

### 1. Komunitas yang Besar

Seperti yang kita ketahui saat ini, [Dart](https://dart.dev) dan [Flutter](https://flutter.dev) dibuat oleh Google, kebanyakan software yang telah di buat google tersebut terbukti dukungan komunitas yang sangat bagus baik dari google maupun dari komunitas yang lain. Biasanya google/Flutter sering membagikan update dan sharing di beberapa sosial medianya dan juga beberapa orang GDE(*Google Developer Expert*) sebagai penjembatan antara teknologi yang dibuat oleh google untuk diedukasikan/disebarkan ke pihak yang lebih banyak. Dengan begitu otomatis komunitas di Dart/Flutter sendiri banyak peminatnya.

Kemudian jika kemunitas sudah besar, ketika kita belajar pastinya akan jauh lebih mudah dibanding yang komunitasnya kurang. Seperti contoh jika Anda kesulitan dalam memecahkan masalah Anda bisa dengan muadh mencari kata kunci di google atau di tempat komunitas online lainya akan mudah menemuka solusinya.

### 2. Multi Platform

Salah satu tujuan dibuatnya bahasa pemrograman Dart ini adalah dengan tujuan supaya kode-kode kita dapat berjalan diberbagai paltform / perangkat. Dalam satu basis kode(*code base*) dapat berjalan diberbagai system seperti (android, ios, web, desktop, dan masih banyak lagi). Karena hal itu Flutter sendiri sekarang memakai bahasa pemrograman utamanya yaitu Dart, karena fokus utamanya Flutter yaitu keevektifitasanya dalam mengembangkan aplikasi tanpa membuat satu-satu pada system/platformnya.

### 3. Dipakai oleh Flutter

Seperti yang telah saya mention diatas, Dart adalah bahasa pemrograman utama yang dipakai untuk membangun dan membuat aplikasi menggunakan Flutter. Sejak adanya Flutter dart menjadi salah satu bahasa pemrograman yang sangat naik daun dan perlu dipertimbangkan untuk menggunakannya. Dengan memakai Dart, Flutter mampu membuat UI yang sangat menarik dan beberapa kelebihan yang dimiliki oleh Flutter seperti Multi Platform, Hot Reload, dan Cepat.

Jika Anda ingin belajar Flutter tapi belum memahami Dart, Anda sangat dianjurkan sekali mempelajari dan memahami Dart terlebih dahulu sebagai fondasinya. Karena memang di Flutter bahasa utamanya yaitu Dart.

### 4. Hot Reload

Apa itu **Hot Reload** sih? sebelumnya sudah pernah aku mention tapi jika mungkin belum mengetahui, **Hot Reload** yaitu dimana, ketika kita sedang melakukan development/membuat aplikasi menggunakan Dart kita dalam langsung melihat update perubahan ketika kita menyimpan kode yang telah diubah tadi, tanpa melakukan build ulang. Hal ini sangat menarik pada Dart, dimana kita dapat menghemat banyak waktu dengan adanya hot reload tanpa melakukan build ulang secara terus-menerus. Kebanyakan bahasa pemrograman lain saat ini masih belum mendukung fitur ini.

### 5. Mudah Memahami dan Adaptasi

Dart dibuat untuk mendukung aplikasi yang dapat berlajan di multiple platform, dengan begitu ada banyak **developer**(pengembang) yang berasal dari background yang berbeda-beda jika ingin mencoba Dart ini. Jadi di Dart syntaks semanya sebisa mungkin dimiripkan dengan beberapa common(sering) yang digunakan oleh beberapa bahasa pemrograman. Di dart syntaksnya mirip seperti bahasa pemrograman Kotlin, Swift, TypeScript, dan lainya. Jadi banyak developer yang cukup familiar dengan kode-kode yang mirip seperti yang dipelajari sebelumnya.

## Platform Dart

Dart mempu berjalan di berbagai platform diataranya yaitu:

### 1. Flutter (Mobile, Web, Desktop)

![Flutter Logo](https://storage.googleapis.com/cms-storage-bucket/6a07d8a62f4308d2b854.svg)

Yang pertama yaitu Flutter, seperti yang sudah dipelajari sebelumnya Flutter dibangun dengan bahasa Dart. Sedangkan di Flutter memungkinkan Anda membuat aplikasi di berbagai platform baik di Mobile(Android, iOS), Web, dan Desktop. Bahkan untuk sekarang sudah mendukung perankat embeded seperti IoT. 

More info: https://flutter.dev/multi-platform

### 2. Server

![Serverpod Logo](https://serverpod.dev/assets/img/serverpod-logo-inverted.svg)

Yah, benar sekarang banyak library dan developer yang sedang mengembangkan Dart untuk berjalan di Server sebagai API atau layanan lainya. Walaupun memang untuk sekarang peruntukannya masih belum semasih beberapa framework/bahasa pemrograman lain yang difokuskan untuk berjalan di server. Tapi tidak ada salahnya jika membuat aplikasi antara client dan server sama-sama menggunakan Dart, jadi secara development lebih efektif tidak perlu mempelajari teknologi yang lain.

Banyak library yang anda dapat gunakan untuk membangun aplikasi server/REST-API menggunakan Dart:

1. [Dart Frog](https://dartfrog.vgv.dev)
1. [Serverpod](https://serverpod.dev)

### 3. CLI

Selain Flutter dan Server dalam penggunaanya, Dart juga dapat kita fungsikan sebagai alat/*tools* yang berupa CLI yang berjalan di terminal/CMD. Tools seperti ini sangat bermanfaat sekali sebagai developer untuk menunjang produktifitas seperti membuat tool utuk generate kode atau mempermudah kalkulasi. Ada beberapa contoh penggunaan berikut ini:

- [Mason CLI](https://pub.dev/packages/mason_cli) sebagai tool untuk generate code
- [FVM](https://fvm.app) sebagai tool untuk management version Flutter SDK
- [Very Good CLI](https://cli.vgv.dev) sebagai tool untuk membut starter dart project 

### Hello World Dart

Tidak afdol kalau sudah mempelajari apa itu dart, tadi tidak tahu program pertama hello world (Halo Dunia). Ini adalah contoh program sederhana yang dibuat dari code Dart untuk menampilkan `Hello World`

{{< file "dart" "main.dart" >}}
```dart
void main() {
    print('Hello World');
}
```

Eits, selalu ingat titik koma ya :) karena di dart untuk mengakhiri expression masih tetap memakai `semi-colon` (titik koma).

Kode diatas dapat Anda coba jalankan secara online, tanpa harus menginstall SDK hanya menggunakan [Dartpad](http://dartpad.dev/), sebagai official dart code playground dari Dart team.

**References**:

- https://dart.dev/overview
- https://en.wikipedia.org/wiki/Dart_(programming_language)