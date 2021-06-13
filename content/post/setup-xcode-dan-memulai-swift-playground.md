+++
date = 2021-06-13T16:00:00Z
featured = false
images = ["https://i.ibb.co/R3QpW6S/ezgif-2-7c91b59b702c.webp"]
series = []
tags = ["swift", "xcode"]
title = "Setup Xcode dan Memulai Swift Playground "

+++
Jika Anda ingin memulai belajar membuat aplikasi IOS Anda perlu menggunakan IDE yang bernama **Xcode**.

**Apa itu Xcode?**

**Xcode** yaitu sebuah **IDE**(_Integrated Development Environment_) khusus yang dibuat oleh Apple, yang berfungsi untuk membuat/membanguan sebuah app untuk Iphone, Mac, Apple TV, dan Apple Watch.

## Getting Started

Sebelum kita memulai penginstalan Xcode perlu diperhatikan apa syarat yang perlu Anda penuhi(_requirement_) yang bisa Anda lihat di situs [apple developer](https://developer.apple.com/support/xcode/ "XCode Requirement"), pastikan syarat untuk install xcode terbaru terpenuhi, baru kita akan lanjut ke proses selanjutnya.

![](https://i.ibb.co/vvqyQz9/Screen-Shot-2021-06-13-at-22-12-39.png)

### Download & Install

Cara install dan download termudah yaitu lewat app nya Apple yaitu **App Store** disitu Anda dapat install secara mudah dan gratis bisa coba klik [link berikut](https://apps.apple.com/ca/app/xcode/id497799835?mt=12 "Link Xcode Download").

Dan Anda juga dapat install secara manual dengan mendownload app dari [Apple Developer Page](http://developer.apple.com/xcode/ "Link Download XCode Manually") jika Anda tidak memiliki Mac App Store, cara tersebut adalah sebagai alternatif.

Atau jika Anda ingin install Xcode dengan spesifik versi yang Anda inginkan bisa kunjungi [tautan berikut](https://developer.apple.com/download/more/). Anda bisa mendownload versi-versi Xcode yang sebelumnya pernah di release oleh Apple. Cara berikut memungkinkan terjadi bila device Anda tidak mendukung versi terbaru saat ini.

## Memulai Swift Playground

Setelah selesai proses penginstalan app Xcode. Anda perlu membuka aplikasi Xcode yang terinstal pada Mac Device Anda. Dan ketika buka pertama kali akan muncul welcome screen seperti ini:

![](https://i.ibb.co/hZrM2CD/10-Xcode-Welcome-Screen.png)

Jika Anda tidak menemukan dialog Welcome Screen seperti ini, Anda dapat juga membuat swift playground dengan klik menu `File` kemudian pilih menu `New` terus pilih `Playground`.

![](https://i.ibb.co/CJfQw9m/11-File-Menu.png)

Kemudian setelah klik new Playground, akan muncul Pop Up lagi untuk template playground apa yang ingin Anda gunakan, misal pada kasus ini Saya menggunakan template blank saja pada platform Ios.

![](https://i.ibb.co/NSkd7dh/12-Blank-Playground.png)

Anda dapat menyimpan playground tersebut misal suatu saat Anda membutuhkan contoh kode yang pernah Anda buat sebelumnya di playground, Saya biasa menyimpan file playground di lokal(penyimpanan Mac).

### Element di Xcode Playground

Pada bagian ini sangat penting bagi pemula yang perlu Anda focus untuk mempelajarinya sekarang.

![](https://i.ibb.co/ZVBRP0Z/better-image.png)

1. **Kode Editor:** Dimana Anda dapat menuliskan kode-kode yang ingin Anda tuangkan.
2. **Line Number**: Sebuah angka urutan dari sebuah baris-baris kode yang Anda tuliskan.

   > Jika Anda tidak menemukan Line Number pada Xcode Anda, Anda dapat menyettingnya supaya muncul dengan klik menu `XCode >Preferences > Text Editing > Line Numbers` Kemudian enable pada checkbok `Line Numbers`
3. **Status Bar**: Memberitahukan info apa saja yang terjadi pada playground. Jika status bar memberitahukan bahwa **Ready** berarti Xcode Playground tersebut dapat Anda jalankan/running.
4. **Show/Hide Debug**: Menu yang dapat memunkinkan Anda memperlihatkan ataupun menyembunyikan console pada proses debugging. Pada area tersebut tempat untuk mengetes sebuah kode Swift yang ditulis.

   ![](https://i.ibb.co/xYgDqws/17-Tabs.png)
5. **Execute Playground**: Menjalankan keseluruhan kode pada playground yang kita buat.

   Pada bagian ini Anda dapat menyettingnya apakah kita ingin otomatis run ketika ada perubahan atau manual menjalankan kode ketika diinginkan.

   ![](https://i.ibb.co/z4bVxMq/18-Automatic-Manual.jpg)

   a. **Automatically Run**: Xcode akan secara otomatis menjalankan kode kita kapanpun ketika ada perubahan di kode playground Anda.

   b. **Manually Run**: Anda perlu mengklik button `play` untuk menjalankan sebuah playground yang Anda buat.

Sekian yang dapat saya bagikan semoga bermanfaat.