---
title: "Dartpad Dart Playground"
date: 2023-02-04T23:18:23+07:00
draft: false
weight: 4
tags: ["dart", "dartpad"]
images: [
    "/series/dart-dasar/dartpad/featured.png"
]
---

Kadang ketika kita ingin mencoba teknologi software terutama bahasa pemrograman sering kita mengharuskan untuk menginstall terlebih dahulu, bahkan sekedar untuk mencoba membuat Hello World. Dengan masalah tersebut banyak bahasa pemrograman modern sekarang menyediakan platform untuk mencoba dan mengcompile code supaya dapat langsung dijalankan di dalam browser. 

Di bahasa Dart juga memiliki platform untuk mencoba dan membuat kode-kode secara instan tanpa memerlukan penginstalan SDKnya. Sering juga disebut platform tersebut untuk membuat kode secara online dengan platform browser dengan nama **playground** atau online compiler. Adapun untuk di dart namanya Dartpad playground.

Btw, jika ingin install dart SDK bisa lihat materi sebelumnya di [Cara Penginstalan Dart SDK](/series/dart-dasar/2-installation/).

## Apa itu DartPad? 

![Dartpad Overview](/series/dart-dasar/dartpad/dartpad.png)

**DartPad** adalah tool open source official yang dibuat oleh dart team, yang memungkinkan kita menjalankan code-code Dart di dalam browser. Kita dapat memanfaatkan semua fungsi yang ada di bahasa Dart core secara keseluruhan yang didukung pada platform web, karena dart adalah multi platform. Dartpad sendiri Anda dapat kunjungi situsnya ada di [dartpad.dev](https://dartpad.dev). 

Pada dartpad tidak hanya bisa menulis kode yang simple saja tapi bisa juga secara kompleks bahkan bisa juga menulis kode dengan framework [flutter](https://flutter.dev). 

Sebanarnya untuk dapat menjalankan kode Dart secara online tidak hanya ada di dartpad, akan tetapi banyak juga platform online seperti replit, jdoodle dan banyak lagi.

Setelah mengetahui dartpad playground, yuk lanjut ke proses mempelajari dartpad....

## Membuat Projek

Ketika mengunjungi situs [dartpad](https://dartpad.dev), secara otomatis akan disediakan editor yang dapat Anda langsung edit dan jalankan kode dartnya tersebut.

![New Project in Dartpad](/series/dart-dasar/dartpad/dartpad_new_project.png)

Untuk membuat projek baru yang ada di dartpad, cukup mudah dan cepat caranya cukup klik tombol `New Pad` kemudian akan ada pilihan membuat projek baru menggunakan Dart saja atau sekalian disiapkan Flutter. Pada kasus ini Saya akan lebih fokus kepada Dart, jadi pilih opsi Dart saja. Akan tetapi Anda juga boleh mencobanya untuk opsi Flutter.

Ketika sudah membuat projek baru, akan disediakan template menampilkan hello sebanyak 5 kali menggunakan perulangan. 

{{<file "dart" "main.dart">}}
```dart
void main() {
  for (int i = 0; i < 5; i++) {
    print('hello ${i + 1}');
  }
}
```

### Membuat Projek dengan Template

Akan tetapi untuk membuat projek pada dartpad tidak hanya itu saja opsinya, Anda juga dapat menggunakan beberapa template yang sudah disediakan oleh dartpadnya, dengan cara klik tombol yang ada di samping kiri atas `Samples` kemudian pilih salah satu contoh disitu. 

Untuk logo Dart berarti projeknya beruda dart code murni, tapi kalau logonya berupa Flutter maka contoh tersebut adalah projek Flutter.

![Dartpad New Project with Template](/series/dart-dasar/dartpad/dartpad_select_template.png)

Setelah memilih template, maka di editornya akan otomatis terupdate dengan kode template tersebut.

## Menjalankan Kode

Salah satu tujuan dari adanya dartpad atau playground lainya yaitu supaya mempermudah user untuk menggunakan tool tersebut secara instant tanpa bersusah-payah untuk menginstallnya. Sama halnya untuk di dartpad, kita dapat langsung menjalankan kode yang telah kita buat atau dari template dartpatnya tersebut supaya dapat langsung melihat hasilnya secara instant.

![Dartpad Run](/series/dart-dasar/dartpad/dartpad_run.png)

Untuk dapat menjalankan kode di dartpad, terdapat tombol `Run` untuk menjalankan kode yang ada di editornya, dan kemudian di bagian `Console` tersebut adalah hasil preview compile codenya. Atau dapat juga menggunakan shortcut `CMD + Enter` untuk Mac dan `Ctrl + Enter` untuk Windows/Linux.

## Editor

Karena Dartpad itu sendiri adalah code editor, cuma bedanya dia berjalan diatas browser dan secara online. Akan tetapi dartpad juga memiliki perilaku dan bagian-bagian seperti di code editor lainya, bisa lihat detailnya seperti ini:

![Dartpad Editor](/series/dart-dasar/dartpad/dartpad_editor.png)

| Shortcut      | Description |
| ----------- | ----------- |
| `Editor`      | Area utama untuk edit kode-kode dart    |
| `New Pad`   | Button untuk reset/membuat projek baru di dartpad  |
| `Reset`   | Untuk mengembalikan kode ke semula sesuai dengan template yang dipilih   |
| `Format`   | Untuk memformat kode yang kurang rapi menjadi lebih rapi sesuai dengan standar dart   |
| `Install SDK`   | Untuk melihat instruksi untuk menginstall SDK dart  |
| `Run`   | Untuk menjalankan kode dart pada editor  |
| `Console`   | Area yang berguna untuk melihat hasil dari compile dart code  |
| `Select Template`   | Untuk memilih template sebagai initial project di dartpad |
| `Shortcut`   | Untuk melihat daftar shortcut yang ada di dartpad  |
| `Dart Version`   | Untuk memilih versi dart sesuai dengan kebutuhan  |
| `Issues Item`   | Untuk menampilkan masalah-masalah pada kode di editor area berapa banyak  |
| `Documentation`   | Untuk melihat dokumentasi ketika kursor sedang aktif di area kode yang memiliki dokumentasinya  |

## Keyboard Shortcut

Ada beberapa shortcut yang telah disediakan oleh dartpad untuk menunjang produktifitas dalam proses membuat code dart pada dartpad, inilah beberap shortcut yang telah disediakan:

![Dartpad Shortcut](/series/dart-dasar/dartpad/dartpad_shortcut.png)

Untuk melihat shortcut, ada button yang telah disediakan yaitu ada di bagian bawah kanan yang iconnya seperti keybord. Adapun penjelasan mengenai shortcut-shortcutnya berikut ini:

| Shortcut      | Description |
| ----------- | ----------- |
| `F1`      | **Documentation**, untuk melihat dokumentasi pada kode yang sedang ada di kursor tersebut       |
| `Option` + `Enter` (Mac) / `Alt` + `Enter` (Windows)   | **Quick Fix**, cara mudah untuk membenahi kode warning atau info yang tidak sesuai dengan standar dari dart/analyzer tersebut   |
| `Command` + `Space` (Mac) / `Ctrl` + `Space` (Windows)   | **Completion**, untuk memberikan saran kode yang akan dituliskan selanjutnya sesuai dengan kode yang telah ditulis   |
| `Shift` + `Command` + `F` (Mac) / `Shift` + `Ctrl` + `F` (Windows)   | **Format**, untuk memformat kode atau merapikan kode yang telah ditulis di editor   |
| `Command` + `Enter` (Mac) / `Ctrl` + `Enter` (Windows)   | **Run**, untuk menjalankan kode  |

> Bagi yang familiar dengan keybinding vim, bisa juga aktifkan **Vim keyboard mapping** untuk menajadikan dartpad seperti vim yang ada terminal keybindingnya.

Oh ya, dart juga dapat di embed di web lain dengan kode seperti ini:

```html
// id=4ac3f2a77b277deebd6ff76a37e007aa ini adalah id github gist, tapi sifatnya optional
<iframe src="https://dartpad.dev?id=4ac3f2a77b277deebd6ff76a37e007aa&null_safety=true&theme=dark" style="width:100%;height:500px; border: none;"></iframe>
```

Kemudian hasilnya seperti ini:

{{<rawhtml>}}
</br>
<iframe src="https://dartpad.dev?null_safety=true&theme=dark" style="width:100%;height:500px; border: none;"></iframe>
</br>
{{</rawhtml>}}

**References:**

- https://dart.dev/tools/dartpad