+++
date = 2020-11-07T17:00:00Z
description = ""
draft = true
images = []
tags = ["atomic-design", "concept", "flutter"]
title = "Flutter Implement Atomic Design Part 2"

+++
Seringkali ketika kita membuat sebuah komponen/elemen pada sebuah design atau User Interface, kita pasti sering mengulang-ulang pembuatan komponen tersebut yang sama. Atau bisa disebut juga tidak clean-code atau juga tidak reusable kode kita.

Dengan adanya **Atomic Design** ini, kita dituntut membuat kode komponen dengan sangat **bersih**(clean code), **reusable** (bisa digunakan beberapa kali) dan **konsisten**.

Sebelumnya saya telah membahas mengenai **Atomic Design**, yang saya tulis sebelumnya di [Atomic Design Concept Part 1](https://wisnuwiry.space/post/atomic-design-concept/). Tapi masih hanya penjelasan tidak sampai secara teknik nya.

Pada kesempatan kali ini aku mau bahas mengenai **Penggunaan Atomic Design pada Flutter**, Mungkin ada yang beranggapan Atomic Design hanya bisa dilakukan oleh orang design (UI/UX, Front End), tapi tidak hanya sebatas itu saja, bisa kok Konsep Atomic Design di gunakan dibeberapa bidang, contohnya pada kali ini digunakan di **Flutter**, sebagai tool pengembangan mobile app(Aplikasi Seluler).

Sebelumnya di artikel [Atomic Design Concept Part 1](https://wisnuwiry.space/post/atomic-design-concept/) sudah saya bahas module/komponen di **Atomic Design**, terbagi menjadi 4 yaitu **Atom**, **Molecule**, **Organism**, **Template**, **Page**. Mari kita bahas satu-persatu **implementasi Atomic Design pada Flutter**.

Untuk **struktur module komponen Atomic Design Flutter** yang saya pakai seperti ini, JIka teman-teman punya pendapat sendiri boleh kustom aja:

```md
├── component
│   ├── atom
│   │   ├── **/*.dart
│   ├── molecule
│   │   ├── **/*.dart
│   └── organism
│       ├── **/*.dart
|
├── src
│   └── pages
├── ...
```

Berikut masing-masing penjelasan dari struktur tersebut.

## Atom

Atom ini bagian terkecil dari komponen atau di Flutter biasa disebut dengan **Widget**. Pada Module kita hanya membuat sebuah Widget/Komponen yang ada di Flutter yang paling terkecil dan yang paling common(sering digunakan). Misal kalau di **Flutter** terdapat dua base style yaitu [Material Design](https://flutter.dev/docs/development/ui/widgets/material "Material Design in Flutter") dan [Cupertino Design](https://flutter.dev/docs/development/ui/widgets/cupertino "Flutter Cupertino Design"). Dimana dari dua style tersebut jelas sekali berbeda, yang **Material Design** di design oleh **Google**, dan **Cupertino Design**, di design/rancang oleh **Apple**. 