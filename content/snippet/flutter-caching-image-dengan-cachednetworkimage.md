+++
date = 2021-04-05T06:00:00Z
draft = true
series = []
tags = ["snippet", "library"]
title = "Flutter Caching Image dengan CachedNetworkImage"
toc = false

+++
Flutter dapat menyimpan cache gambar yang pernah di muat sebelumnya dan disimpan ke dalam storage dengan bantuan library [cached_network_image](https://pub.dev/packages/cached_network_image "cached_network_image"). Sebenarnya ketika kita menggunakan Widget Image pada Flutter gambar yang dimuat tersebut otomatis disimpan tapi hanya sementara/ penyimpanan di memory(RAM).

Pada library/dependency `cached_network_image` kita dapat menyimpan data gambar kita sebelumnya yang pernah kita muat, jadi pada proses selanjutnya akan tidak muat ulang dari awal lagi, sehingga ini bisa menghemat resource ketika muat selanjutnya. Dependency ini cocok sekali jika Anda menargetkan aplikasi Anda bisa berjalan dengan Internet maupun tidak. Berikut contoh dan penjelasanya:





**More Info**: https://pub.dev/packages/cached_network_image "cached_network_image