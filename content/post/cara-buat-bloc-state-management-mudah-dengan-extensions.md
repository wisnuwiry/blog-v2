+++
date = 2020-11-08T17:00:00Z
images = ["https://i.ibb.co/pbddZQG/bloc-extensions.png", "https://i.ibb.co/9pWqwjT/screenshot-22538.png", "https://i.ibb.co/pjLp9h4/screenshot-22537.png", "https://raw.githubusercontent.com/felangel/bloc/master/extensions/vscode/assets/wrap-with-usage.gif", "https://raw.githubusercontent.com/felangel/bloc/master/extensions/vscode/assets/new-bloc-usage.gif"]
tags = ["extension", "flutter", "tips"]
title = "Cara Mudah Menggunakan Bloc State Management dengan Extensions"

+++
Jika Anda adalah pengguna **Bloc state management** di **Flutter**, Sekarang tidak perlu lagi membuat state management baru awal, sudah ada extensions untuk mengenerate state management bloc.

Author dari **Bloc** yaitu [Felix Angelov](http://github.com/felangel/) telah membuat dan menyediakan extensions yang bernama **bloc** yang diperuntukkan agar kita ketika membuat Bloc state management jadi lebih mudah dan menyenangkan. Tenang saja untuk extensions Bloc ini sudah mendukung di beberapa **Text Editor dan IDE yang di support oleh Flutter**.

**Extension Bloc** ini adalah tool yang digunakan untuk generate state management baru, dan juga tersedia beberapa snippet yang membantu pekerjaan Anda.

Berikut Text Editor dan IDE yang sudah di support extensions bloc:

1. **Android Studio** ([lihat](https://plugins.jetbrains.com/plugin/12129-bloc "Extensions Bloc generator in Android Studio"))
2. **Intellij IDEA** ([lihat](https://plugins.jetbrains.com/plugin/12129-bloc "Extensions Bloc generator in Intellij IDE"))
3. **Visual Studio Code** ([lihat](https://marketplace.visualstudio.com/items?itemName=FelixAngelov.bloc "Extensions Bloc in Visual Studio Code"))

Sebelumnya jangan lupa menginstall dependency beberapa di **pubspec.yaml**, terlebih dahulu. Berikut contoh dependency yang harus diinstall:

```yaml {linenos=table,hl_lines=["13-14"]}
name: counter # example name project
description: desc
version: 1.0.0+1

environment:
  sdk: ">=2.7.0 <3.0.0"

dependencies:
  flutter:
    sdk: flutter
  flutter_localizations:
    sdk: flutter
  equatable: ^1.2.5 # Add this
  flutter_bloc: ^6.0.6 # add this

dev_dependencies:
  flutter_test:
    sdk: flutter

flutter:
# ...
```

Ketika sudah install dependency tersebut, jangan lupa install terlebih dahulu extensions bloc, sesuai dengan Text Editor/IDE Anda.

Kemudian tinggal buat dengan bloc extensions deh.

## VS Code

Di VS Code untuk extension Bloc ini lumayan lengkap fiturnya, ada **Generator Bloc**, **Snippet untuk Bloc**, dan juga **Wrapping Widget**.

## Generate Bloc

Untuk di VS Code mengenerate Bloc cukup mudah, tinggal klik kanan di folder >> Input nama Bloc nya. Atau bisa menggunakan Command Pallete di VS Code. Selengkapnya bisa lihat di [dokumentasinya](https://bloclibrary.dev/#/blocvscodeextension?id=commands "Flutter Bloc Documentation in Generate Bloc in VS Code"). Berikut contohnya:

![Image Bloc generator in VS Code](https://raw.githubusercontent.com/felangel/bloc/master/extensions/vscode/assets/new-bloc-usage.gif "Image Bloc generator in VS Code")

Image from: [https://bloclibrary.dev/](https://bloclibrary.dev/ "https://bloclibrary.dev/")

## Wrapping Widget

Untuk wrapping widget pada bloc ini digunakan untuk memasukkan Widget apapun ke dalam beberapa widget yang ada di Bloc. Berikut contoh previewnya:

![](https://raw.githubusercontent.com/felangel/bloc/master/extensions/vscode/assets/wrap-with-usage.gif)

Image from: [https://bloclibrary.dev/](https://bloclibrary.dev/ "https://bloclibrary.dev/")

Wrapping widget terdapat beberapa widget Bloc  yang didukung yaitu:

1. BlocBuilder
2. BlocListener
3. BlocConsumer
4. BlocProvider
5. RepositoryProvider

## Snippet

Saat saya menulis artikel ini terdapat beberapa snippet yang kita dapatkan ketika install extension bloc ini, diantaranya berikut:

## Intellij / Android Studio

Untuk di Intellij IDEA ataupun di Android Studio ketika buat **Bloc state management**, cukup klik kanan `New` >> dan pilih **Bloc Class.**

Berikut contohnya:

![Flutter Generete Bloc code in Android Studio](https://i.ibb.co/pjLp9h4/screenshot-22537.png "Flutter Generete Bloc code in Android Studio")

![Flutter Change Name Flutter Bloc in Android Studio](https://i.ibb.co/9pWqwjT/screenshot-22538.png "Flutter Change Name Flutter Bloc in Android Studio")

## Reference:

* [https://bloclibrary.dev/](https://bloclibrary.dev/ "https://bloclibrary.dev/")