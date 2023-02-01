---
title: "Karakteristik Dart"
date: 2023-02-01T19:48:23+07:00
draft: false
weight: 2
tags: ["dart", "basic"]
images: [
    "/series/dart-dasar/featured_full.webp"
]
---

Dart adalah salah satu bahasa pemrograman yang modern karena release pertama kalinya kurang lebih 10 tahun an. Dart memiliki banyak kemiripan dari sisi kode seperti bahasa pemrograman yang lain seperti Java, Kotlin, Swift, dan Typescript. Dart dibangun untuk mempermudah para developer yang ingin menggunkan Dart jadi lebih familiar bagi developer yang telah memahami bahasa pemrograman sebelumnya. Namun bagi yang baru pertama kali belajar Dart juga bisa lebih mudah dan nyaman karena banyak fitur untuk membantu proses belajarnya.

Bisa cek materi tentang [Pengenalan Dart](/series/dart-dasar/1-pengenalan/).

Ini adalah contoh kode Dart:

{{<file "dart" "main.dart" >}}
```dart
void main() {
    var name = 'Wisnu';
    int age = 20;

    print("Hello my name is $name and i'm $age years old");

    final total = 12 + 30;
    print(total);
}
```

Pada contoh kode dart diatas, jika sebelumnya sudah menguasai beberapa bahasa pastinya akan lebih familiar karena sintaks-sintaksnya hampir mirip dengan bahasa modern yang lain saat ini.

Kemudian untuk karakteristik-karakteristik Dart sendiri berikut ini:

## 1. Open Source

![Open Source Icon](https://opensource.org/sites/default/files/public/osi_keyhole_300X300_90ppi_0.png)

Dart merupakan projek dari Google yang open source, yang dimana siapapun dapat melakukan kontribusi ke projek tersebut. Dart sendiri sekarang projeknya berlisensi BSD license, yang berarti semua codenya dapat Anda gunakan bebas tanpa adanya perizinan dari pemilik dan bebas juga melakukan kontribusi didalamnya.

Banyak project yang besar saat ini berasal dari open source seperti Linux, Git, Android, beberapa bahasa pemrograman dan masih banyak lagi, karena dengan adanya *open source* projek dapat berkembang secara pesat, biaya pengembangan murah dan juga mudah untuk dikenal orang lain/komunitas.

## 2. Object-Oriented Programming

Dart itu bahasa pemrograman yang bersifat *object-oriented programming*(OOP) dan mendukung semua konsep yang ada di OOP seperti `class`, `inheritence`, `interface`, dan optional typing. Dan mendukung juga OOP tingkat lanjut seperti `mixin`, `abstract`, `generic`, dan juga type system yang kuat.

Banyak bahasa pemrograman modern sekarang yang memakai paradigma OOP, disamping berbagai macam manfaat/kelebihan yang dimiliki OOP seperti kode yang lebih optmial, lebih bersih (*clean code*) dan juga mudah untuk dikembangan.

## 3. Concurrency

![Concurrency Dart](/series/dart-dasar/karakteristik/paraller.png)

`Concurrency` yaitu dimana suatu sistem yang dapat bekerja dan menjalankan beberapa tugas/instruksi secara bersama dalam waktu yang sama. `Concurrency` sangat populer semenjak adanya perkembangan prosessor yang sekarang memiliki lebih dari 1 core atau `thread` yang mampu berjalan secara paraller. Sekarang banyak sekali bahasa pemrograman yang telah menerapkan fitur concurrency terutama bahasa yang modern tidak terkecuali Dart ini.

Di dart concurrent memakai `async` dan `await` yang ditaruh di class `Future` atau `Stream`.

## 4. Type Safe

Dart itu `type safe` yang artinya pada bahasa Dart semua tipe data dicek oleh compiler dart secara statik maupun secara *runtime* ketika program sedang berjalan, seperti pengecekan type data variable yang telah didefinisikan tidak dapat berubah type datanya baik secara statik maupun runtime.

Pada Dart, pada setiap variable itu pasti memiliki type data dan harus didefiniskan pada saat pertama kali. Akan tetapi dart sendiri sudah canggih ada beberapa kasus optional untuk mendifiniskan type data pada sebuah variable seperti keyword `var`. 

Dengan adanya type safe ini developer jadi lebih mudah proses development karena semua tipe dapat dilihat secara jelas tanpa variable yang bias. Dan bebebrapa kesalahan manusia dapat diminilasir dengan bantuan analyzer untuk menganalisa kode kita baik secara statik maupun runtime.

## 5. Null Safety

![Null Safety](/series/dart-dasar/karakteristik/null-safe.png)

`Null Safety` yaitu sebuah keamanan dari bahasa pemrograman untuk mengatasi permasalahan variable/type data yang `null`, dengan membatasi semua operasi yang jelas tidak akan null dan juga `nullable`(kemungkinan dapat null) supaya lebih mudah dalam pengecekan.

Sebenarnya null-safety ini masih ada kaitanya dengan `type-safe` karena dengan adanya type-safe dapat menerapkan fitur null-safety ini, semua type data dapat terlihat jelas.

**References:**

- https://dart.dev/guides/language/language-tour
- https://www.javatpoint.com/dart-features
- https://dart.dev/guides/language/concurrency

Sekian materi ini, bisa lanjutin ke materi selanjutnya ya :)
