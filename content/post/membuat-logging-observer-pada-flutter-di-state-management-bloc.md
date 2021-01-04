+++
date = 2020-12-04T17:00:00Z
images = []
tags = ["flutter", "bloc"]
title = "Membuat Logging Observer pada Flutter di State Management Bloc"

+++
Ketika membuat sebuah **State Managemen Bloc pada Flutter**, kadang kala kita perlu membutuhkan Log event dan state dari state management, untuk mengetahui state terkini dan event pada yang barusan di jalankan.

Pada Flutter untuk membuat **logging** pada **flutter_bloc**, cukuplah mudah dengan cuma tambahin template observer saja dan langsung bisa dilihat hasilnya.

## Buat Bloc Observer Class

Pada **Observer Bloc** ini dimana fitur logging dan beberapa handle logic setiap state management bisa dijalankan di sini. Adapun fungsi/method apa saja yang bisa kita handle pada Bloc Observer diantaranya yaitu:

1. `onCreate()`

   Pada method `onCreate` ini, dimana State Management Bloc ataupun Cubit di Flutter dibuat/di inisialisasikan saat pertama kalinya.
2. `onEvent()`

   Pada method `onEvent` di muculkan ketika ada aksi event ke salah satu `Bloc`, jadi untuk semua event di semua state management Bloc akan bisa dilihat disini.
3. `onChange()`

   Pada method `onChange` ketika ada perubahan state pada `StateManagement Cubit.`
4. `onTransition()`

   Pada method `onTransition` dipanggil ketika ada perubahan state dari Bloc lewat event trigger `.add()` dan di handle di `mapEventToState` pada `Bloc.`
5. `onError()`

   Method ini dipanggil ketika terjadi error pada salah satu state management di `Bloc`

   ataupun `Cubit` misal yang sering terjadi kesalahan argument event tidak sesuai atau juga logic pada state management di `Bloc` tidak sesuai/terjadi sesuatu kesalahan, Maka method ini akan dijalankan.
6. `onClose()`

   Method ini dipanggil ketika `Cubit` telah di close atau `dispose` oleh sistem atau juga user. Misal jika user pindah halaman dengan replace halaman sebelumnya dengan `Provider` pada halaman yang di replace, maka method `onClose` ini dijalankan.

Ketika membuat sebuah `Bloc Observer` sendiri secara custom, kita perlu depend ke abstract class `BlocObserver` yang merupakan bagian dari library **flutter_bloc**. Berikut contoh sederhana Bloc Observer yang saya buat.

```dart
import 'package:bloc/bloc.dart';

class AppBlocObserver extends BlocObserver {
  @override
  void onEvent(Bloc bloc, Object event) {
    print('onEvent $event');
    super.onEvent(bloc, event);
  }

  @override
  void onTransition(Bloc bloc, Transition transition) {
    print('onTransition $transition');
    super.onTransition(bloc, transition);
  }

  @override
  void onChange(Cubit cubit, Change change) {
    print('onChange ${cubit.runtimeType}'
        'From: ${change?.currentState}'
        'To: ${change.nextState}');
    super.onChange(cubit, change);
  }

  @override
  void onClose(Cubit cubit) {
    print('Close ${cubit.runtimeType}');
    super.onClose(cubit);
  }

  @override
  void onCreate(Cubit cubit) {
    print('Create ${cubit.runtimeType}');
    super.onCreate(cubit);
  }

  @override
  void onError(Cubit cubit, Object error, StackTrace stackTrace) {
    print('Error in : ${cubit.runtimeType}'
        'Error: $error'
        'StackTrace: $stackTrace');
    super.onError(cubit, error, stackTrace);
  }
}
```

Pada contoh tersebut saya hanya ingin menampilkan beberapa logging pada State management, yang berguna untuk mengetahui aktifitas pada state management yang kita buat.

## Implement Bloc Observer

Untuk implementasi Observer/Logging supaya berjalan perlu diterapkan pada file root project kita, biasanya observer bloc tiraruh pada root function `main()` , intinya observer ini harus berada paling awal sebelum adanya Provider lain dari `Bloc State Management`.

Pada contoh tadi saya buat Observer class dengan nama `AppBlocObserver`, untuk namanya observer sesuaikan dengan class name yang Anda buat. 

Berikut contoh penerapanya:

```dart
void main() {
	WidgetsFlutterBinding.ensureInitialized();
	Bloc.observer = AppBlocObserver();
    ...
}
```

Jika Anda menerapkanya pada method root di `main()` jangan lupa tambahkan method `WidgetsFlutterBinding.ensureInitialized();` sebelum menjalankan kode lainya.

Sekian dari saya, Semoga bermanfaat :)