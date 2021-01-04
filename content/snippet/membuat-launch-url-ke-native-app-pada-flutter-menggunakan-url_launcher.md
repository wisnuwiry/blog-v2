+++
date = 2020-12-22T17:00:00Z
series = []
tags = ["tips", " snippet", " plugin"]
title = "Membuat Launch URL ke native app pada flutter menggunakan url_launcher"

+++
## Pengenalan

Ketika membuat app kadang kala kita perlu navigasi ke berbagai aplikasi, misal jika ingin pindah ke aplikasi SMS, Telephon, E-Mail, Maupun langsung ke browser dengan mengirimkan data yang kita inginkan. Terus gimana cara implementasi navigasi ke berbagai aplikasi di flutter?

Pada Flutter sudah menyediakan package/library open source yang dapat kita gunakan, yang bernama `url_launcher` untuk info selengkapnya bisa Anda lihat di situs resminya di [https://pub.dev/packages/url_launcher](https://pub.dev/packages/url_launcher "https://pub.dev/packages/url_launcher"). Untuk plugin ini sudah di support oleh beberapa platform diantaranya yaitu: Android, IOS, Web. Jadi jika ingin membuat aplikasi multiplatform lebih gampang.

## Support Schema

Pada library `url_launcher` saat ini terdapat beberapa fitur-fitur launch url/scheme yang dapat kita gunakan yaitu:

| Skema | Aksi |
| --- | --- |
| `http://<URL>` atau `https://<URL>` | Akan pindah navigasi ke aplikasi browser, dan jika terdapat app/aplikasi yang di support(didukung) schema domain tersebut, akan langsung ke app yang dituju. |
| `mailto:<email address>?subject=<subject>&body=<body>` | Akan navigasi ke aplikasi email yang tersedia pada aplikasi Anda |
| `sms:<phone number>` | Akan navigasi ke aplikasi SMS yang tersedia pada aplikasi Anda |
| `tel:<phone number>` | Akan navigasi ke panggilan telephone pada aplikasi Anda |
| `<app_scheme>://` cth. `whatsapp://15551234567` | Pada schema ini Anda dapat menjalankan beberapa aplikasi pihak ketiga yang sudah Anda install pada device Anda (Android/IOS)|

## Example Use
Dan untuk contoh implementasinya cukup mudah dengan cara-cara ini:

1. Pertama perlu install dulu dependency `url_launcher`.

Pada file `pubspec.yaml` tambahkan dependency sesuai dengan versi yang ada pada [pub.dev](https://pub.dev/packages/url_launcher). Sebagai contoh pada saat ini versinya gini:

```yaml {hl_lines=[2]}
dependencies:
  url_launcher: ^5.7.10
```

Jangan lupa jalankan `flutter pub get`

2. Buat method/fungsi launch

Banyak sekali yang bisa kita lakukan dengan `url_launcher` untuk menjalankan/pindah aplikasi dari aplikasi Flutter kita ke berbagai aplikasi yang terinstall pada device kita. Untuk plugin ini kan sifatnya menjalankan berdasarkan dari url, jadi jika aplikasi tersebut mempunyai schema yang di support. Maka plugin ini bisa menjalankan segala aplikasi tersebut.
  
Sebagai contoh `url_launcher` ini bisa menjalankan aplikasi WhatsApp, Telegram, Twitter, Instagram, dll masih banyak sekali.
  
Untuk contoh kode implementasinya seperti ini:

Pertama import library ke file dart Anda pada project flutter.

```dart
import 'package:url_launcher/url_launcher.dart';
```

Contoh launch url dengan http/https:

```dart
//...
RaisedButton(
  child: Text('Launch URL'),
  onPressed: () {
    _launchURL('https://flutter.dev');
  }
),
//...

_launchURL(String url) async {
  if (await canLaunch(url)) {
    await launch(url);
  } else {
    throw 'Could not launch $url';
  }
}
```

Contoh launch dengan aplikasi pihak ketiga:

```dart
import 'dart:core';

//...
RaisedButton(
  child: Text('Launch App'),
  onPressed: () {
    _launchWhatsapp(12345678, 'Hello My Name is .., How are you?');
  }
),
//...

void _launchWhatsapp(String phone, String message){
 final url = 'https://wa.me/$phone?text=${Uri.parse(message)';
 if (await canLaunch(url)) {
    await launch(url);
  } else {
    throw 'Could not launch $url';
  }
}
```

Cukup sekian tutorial kali ini semoga bermanfaat.