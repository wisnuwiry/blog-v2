+++
date = 2021-11-09T17:00:00Z
draft = true
series = []
tags = ["flutter", " tips"]
title = "Cara Membuat Text Input Di Flutter Dengan Kapital Semua"
toc = false

+++
Cara membuat input di Flutter supaya bisa hurufnya berupa kapital/uppercase semua, walaupun user input huruf tidak kapital.  Di Flutter bisa untuk implementasinya cukup gunakan custom class [`TextInputFormatter`](https://docs.flutter.io/flutter/services/TextInputFormatter-class.html) untuk memfilter dan custom input yang dari user ke dalam widget [`TextField`](https://api.flutter.dev/flutter/material/TextField-class.html)/[`TextFormField`](https://api.flutter.dev/flutter/material/TextFormField-class.html).

Ketika memanggil class `TextInputFormatter` Anda perlu import flutter services terlebih dahulu:

```dart
import 'package:flutter/services.dart';
```

Berikut contoh Implementasi [`TextInputFormatter`](https://docs.flutter.io/flutter/services/TextInputFormatter-class.html) Filter untuk mengubah semua input jadi huruf kapital:

```dart
class UpperCaseTextFormatter extends TextInputFormatter {
  @override
  TextEditingValue formatEditUpdate(TextEditingValue oldValue, TextEditingValue newValue) {
    return TextEditingValue(
      text: newValue.text.toUpperCase(), // fungsi untuk mengkapitalkan carakter/huruf
      selection: newValue.selection,
    );
  }
}
```

Contoh implementasi:

{{< rawhtml >}}
</br>
<iframe src="https://dartpad.dev/embed-flutter.html?id=4ac3f2a77b277deebd6ff76a37e007aa&null_safety=true&theme=dark" style="width:100%;height:500px; border: none;"></iframe>
</br>
{{< /rawhtml >}}