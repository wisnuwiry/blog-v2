+++
date = 2021-11-09T17:00:00Z
series = []
tags = ["tips", "snippet"]
title = "Car Fix Flutter Error Http Request CERTIFICATE_VERIFY_FAILED "
toc = false

+++
Terkadang User ketika memakai aplikasi kita yang dibuat dengan Flutter mendapatkan error `CERTIFICATE_VERIFY_FAILED` ketika melakukan HIT API Request terutama ketika `POST` method. Permasalahan ini sering terjadi di Android versi 6 atau kebawah, tapi tidak semuanya atau random saja user yang mendapatkan error tersebut.

Untuk issue ini pada saat saya membuat artikel ini issue masalah `CERTIFICATE_VERIFY_FAILED` masih belum terpecahkan di Dart/Flutter, yang Anda bisa lihat di [github](https://github.com/flutter/flutter/issues/50699)

Pada kali ini Saya membagikan pengalaman ketika memperbaiki masalah ini pada kasus saya sebelumnya. Kasus saya sebelumnya padahal `SSL`(Secure Socket Layer) masih aktif tapi issue `CERTIFICATE_VERIFY_FAILED` ini malah muncul di sebagian Android. Berikut solusi-solusi yang Saya dapatkan:

## 1. Mengizin Semua Certificate (SSL)

Langkah pertama Anda perlu membuat `HttpOverrides` sendiri, untuk handle certificate. Berikut contohnya:

```dart
import 'dart:io';

class MyHttpOverrides extends HttpOverrides {
  @override
  HttpClient createHttpClient(SecurityContext? context) {
    return super.createHttpClient(context)
      ..badCertificateCallback =
          (X509Certificate cert, String host, int port) => true;
  }
}
```

Jangan lupa import `dart:io` ketika memanggil `HttpOverrides`.

Kemudian di function `main()` di file `main.dart` set `HttpOverrides.global` dengan HttpOverrides yang barusan dibuat. Taruh code ini di dalam function main dan letakkan di paling atas, contoh:

```dart
void main() {
	HttpOverrides.global = MyHttpOverrides();
    // ...
}
```

## 2. Ketika Menggunakan Dio Http Client

Jika Anda menggunakan [Dio](https://pub.dev/packages/dio) sebagai Http Client di aplikasi Anda, Anda cukup letakkan kode ini sebelum menjalankan fungsi apapun, contoh:

```dart
void main() {
  final dio = Dio();
  (dio.httpClientAdapter as DefaultHttpClientAdapter).onHttpClientCreate =
      (HttpClient client) {
    client.badCertificateCallback =
        (X509Certificate cert, String host, int port) => true;
    return client;
  };
}
```

Berikut penjelasan singkat untuk mengatasi masalah `CERTIFICATE_VERIFY_FAILED` di Flutter semoga dengan adanya ini bisa membantu Anda, Terima Kasih :)