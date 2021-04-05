+++
date = 2021-04-05T06:00:00Z
series = []
tags = ["snippet", "library"]
title = "Flutter Caching Image dengan CachedNetworkImage"
toc = false

+++
Flutter dapat menyimpan cache gambar yang pernah di muat sebelumnya dan disimpan ke dalam storage dengan bantuan library [cached_network_image](https://pub.dev/packages/cached_network_image "cached_network_image"). Sebenarnya ketika kita menggunakan Widget Image pada Flutter gambar yang dimuat tersebut otomatis disimpan tapi hanya sementara/ penyimpanan di memory(RAM).

Pada library/dependency `cached_network_image` kita dapat menyimpan data gambar kita sebelumnya yang pernah kita muat, jadi pada proses selanjutnya akan tidak muat ulang dari awal lagi, sehingga ini bisa menghemat resource ketika muat selanjutnya. Dependency ini cocok sekali jika Anda menargetkan aplikasi Anda bisa berjalan dengan Internet maupun tidak. Berikut contoh dan penjelasanya:

```dart {hl_lines=[0],linenostart=1}
CachedNetworkImage(
        imageUrl: "http://via.placeholder.com/350x150",
        placeholder: (context, url) => CircularProgressIndicator(),
        errorWidget: (context, url, error) => Icon(Icons.error),
  ),
```

Pada contoh diatas, pada dependency ini kita dapat handle ketika gambar tersebut dalam keadaan/proses memuat dari internet. Dan juga bisa kita handle ketika gagal memuat gambar tersebut.

* Untuk handle placeholder/loading ketika sedang memuat gambar Anda dapat menggunakan param `placeholder` pada Widget `CacheNetworkImage` dimana pada params tersebut harus return / mengembalikan value bertipe WIdget.
* Dan handle ketika error, misal terjadi suatu kesalahan internet/salah url bisa kita handle dengan menampilkan sebuah widget yang kita inginkan. Dan untuk handle nya kita taruh pada param `errorWidget`.

Tidak hanya itu saja kita bisa juga `CachedNetworkImage` ini ditaruh sebagai Provider image pada default Widget Image. Misal kita pakai `Image` ataupun juga bisa di taruh di `FadeInImage`. Berikut contoh kodenya:

```dart {hl_lines=[0],linenostart=1}
// Widget Image
Image(image: CachedNetworkImageProvider('http://via.placeholder.com/350x150')),

// Widget FadeInImage
FadeInImage(
   image: CachedNetworkImageProvider('http://via.placeholder.com/350x150'),
   placeholder: AssetImage('path_your_file.png'),
 ),
```

**More Info**: https://pub.dev/packages/cached_network_image "cached_network_image