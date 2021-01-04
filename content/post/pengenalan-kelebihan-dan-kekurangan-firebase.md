+++
date = 2020-12-13T17:00:00Z
images = ["https://i.ibb.co/4P8Rx6r/pengenalan-firebase.webp"]
series = ["Flutter Firebase Tutorial"]
tags = ["flutter", " firebase"]
title = "Pengenalan, Kelebihan, Kekurangan dan Fitur-Fitur Tentang Firebase"

+++
## Pengenalan

Ketika Anda mempunyai sebuah **APP** (Aplikasi Seluler), pasti tidak asing lagi ketika mengakses sebuah aplikasi tersebut membutuhkan data pengguna misal data pengguna/user yang login maupun register, bahkan menyimpan sebuah data posting misal story, tweet, dll. Data data tersebut pasti memerlukan ruang penyimpanan, dan terdapat logic-logic yang berada di sisi backend. Dan jika Anda ingin simple membuat app tanpa perlu back end firebase ini lah solusinya.

**Apa itu Firebase?**

**_Firebase adalah_** platform seluler Google yang membantu Anda mengembangkan aplikasi berkualitas tinggi dan menumbuhkan bisnis dengan cepat. (Source: firebase.google.com).

Firebase ini adalah sebuah project buatan oleh **google.com**, dimana kita tahu hampir semua teknologi yang dibuat oleh google itu mempunyai performa dan kualitas yang sangat bagus, jadi tidak ada salahnya kita mencoba menggunakan salah satu teknologinya buatan Google ini.

Pada **Firebase** ada dan terdapat beberapa kelebihan dan kekurangannya, untuk penjelasan selengkapnya bisa baca dibawah ini:

## Kelebihan Firebase

Sebuah tools dan project dibuat pasti ada kelebihan dari yang lain, Untuk Firebase ini terdapat banyak sekali kelebihan, yang dapat kita pertimbangkan ketika ingin membuat sebuah app sendiri.

### 1. Cepat dan Tidak Banyak Effort

Yup **Firebase** diciptakan salah satunya untuk mempermudah seorang Pengembang/Developer untuk membangun sebuah Aplikasi mereka dengan cepat tanpa perlu memerlukan banyak usaha/effort yang kita butuhkan. Kelebihan ini bisa Anda manfaatkan ketika/jika Anda membangun sebuah app dengan Tim skala kecil, maupun project pribadi.

### 2. Free/Gratis

Untuk **Firebase** saat ini (saat saya menulis artikel ini) **Firebase** menyediakan versi gratis yang dapat kita coba, dan implementasikanya. Pada versi gratis dan berbayar fitur tidak jauh berbeda cuma berbeda sebagian performa saja.  Untuk info selengkapnya bisa lihat offfice site **Firebase** untuk pricing/harga di: [https://firebase.google.com/pricing](https://firebase.google.com/pricing "https://firebase.google.com/pricing").

### 3. Easy/Mudah Digunakan

Ketika Anda membuat sebuah project Firebase, akan dibuatkan console dashboard secara otomatis oleh Firebase, kebanyakan fitur firebase dikendalikan oleh konsole. Dan terdapat juga analisis penggunaan app kita.

### 4. Fitur Banyak

Di Firebase kita bisa mendapatkan banyak sekali fitur yang selalu diupdate oleh tim Firebase & Google, tanpa perlu memikirkan maintance, karena semua support dan perbaikan di handle oleh Firebase sendiri, jadi sebagai user kita bisa fokus ke pengerjaanya.  Di Firebase terdapat benyak sekali fitur yang dapat kita coba secara gratis, misal: **Authentication**, **Cloud Messaging**, **Firestore**, **Crashlytics**, **Machine Learning**, **Admob** dan masih banyak lagi.

### 5. Multi-Platform

Kelebihan ini salah satu yang Saya sukai dari Firebase, jadi ketika ingin membuat sebuah App/Aplikasi menggunakan Firebase tidak memandang platform/teknologi tertentu saja, melainkan banyak platform yang disupport oleh firebase ini misal: **Android**, **IOS**, Web, **Windows**, **Linux**, **Mac Os**, dll. Jadi ketika membuat sebuah project dengan Firebase bisa kita saling integrasikan walaupun beda platform yang kita gunakan. Dan untuk dokumentasi firebase ini cukup lengkap bisa kita lihat di: [https://firebase.google.com/docs](https://firebase.google.com/docs "https://firebase.google.com/docs")

***

## Kekurangan Firebase

Apapun teknologi yang dibuat oleh Manusia tidak mungkin luput dari sebuah kekurangan yang dimilikinya, pasti ada walupun itu sedikit maupun banyak pasti ada. Tidak terkecuali juga tech yang kita bahas kali ini yaitu **Firebase** yang punya bebera kekurangan yaitu:

### 1. Akses kurang luas

Karena kita tidak mempunyai platform tersebut(firebase), jadi kita tidak bisa leluasa mengubah platform tersebut. Karena jika kita memakai platform tersebut kita wajib patuh terhadap segala aturan yang dibuat oleh **Firebase**.

### 2. Membebani Frond End

Karena firebase ini adalah tech ServerSide maka mau nggak mau semua bentuk logic yang kita butuhkan berada pada **Frond End**, misal: Android, IOS, Web. Jadi ini bisa memberatkan para developer yang belum terlalu paham tentang logic logic pada back end.

### 3. Kita tidak tahu yang terjadi pada data kita

Ya, karena kita tidak mempunyai itu, jadi pihak pemilik bisa melakukan apapun yang kita tidak bisa ketahui. Karena pemilik memiliki akses 100% pada data kita.

***

## Fitur Firebase

Pada saat Saya menulis artikel ini sudah terdapat banyak sekali fitur yang dapat kita gunakan dan nikmati jika kita menggunakan Firebase Platform. Berikut beberapa fitur dan penjelasan yang kita dapatkan ketika pakai Firebase:

### 1. Analytics

Pada fitur analitics/analisis ini bisa kita gunakan untuk cek berapa pengguna app kita harian, dan beberapa event yang dilakukan oleh user yang sebelumnya kita setting terlebih dahulu bisa kita lihat dalam dahsboard ini, dengan ringkasana yang menarik dan efisien.

{{< youtube 8iZpH7O6zXo >}}

Berikut beberapa sub fitur yang kita dapatkan pada Firebase Analytics:

| Fitur | Platform | Deskripsi |
| --- | --- | --- |
| Dashboard | Android, IOS, Web | Melihat ringkasan pengguna, ringkasan error, ringkasan app versi, ringkasan platform yang digunakan user, traffic pengguna country, dll |
| Events | Android, IOS, Web | Dapat melihat event yang di trigger oleh user |
| Funnels | Android, IOS, Web | Melihat pergerakan user flow mulai dari awal sampai proses flow/peristiwa selesai |
| User Property | Android, IOS, Web | Melihat dan membedakan beberapa user dengan tipe-tipe tertentu misal seperti Mata Biru, Hidung Mancung, dll |
| Latest Release | Android, IOS, Web | Melihat ringkasan terakhir release yang digunakan oleh user |
| Ratention | Android, IOS, Web | Melihat beberapa user yang register atau pengguna baru |
| Stream View | Android, IOS, Web | Melihat secara realtime user-user yang memakai project app kita, mulai dari country, versi, dll, dalam bentuk map |

### 2. Authentication

Platform: IOS, Android, Web, C++, Unity, Java, NodeJS

{{< youtube 8sGY55yxicA >}}

Pada fitur ini kita bisa melakukan bebara metode authentikasi login dan register dengan banyak sekali pilihan yang sudah disediakan. Pada saat saya buat artikel ini method untuk login maupun register yang disediakan oleh firebase yaitu:

 1. Email dan Password
 2. Phone / Nomor Telephon
 3. Google
 4. Play Game
 5. Game Center
 6. Facebook
 7. Twitter
 8. Github
 9. Yahoo
10. Microsoft
11. Apple (only ios)
12. Annonimous

Cukup banyak sekali metode pilihan untuk authentikasi yang bisa kita  dapat implementasikan pada app Anda.

### 3. Cloud Firestore

Platform: IOS, Android, Web, Go, NodeJS, Java, Python, Unity

{{< youtube QcsAb2RR52c >}}

Pada fitur ini kita dapat menyimpan data dengan basis data NoSQL yang hampir mirip seperti dengan Mongo DB.

### 4. Realtime DataBase

Platform: IOS, Android, Web, C++

{{< youtube U5aeM5dvUpA >}}

Pada fitur ini fungsinya mirip seperti **Cloud Firestore**, cuma bedanya pada DataBase ini ketika terdapat perubahan pada database di Firebase akan secara otomatis memberi tahu pada client untuk update otomatis pada SDK firebase.

### 5. Storage

Platform: IOS, Android, Web, C++, Unity

{{< youtube _tyjqozrEPY>}}

Pada fitur ini kita dapat menyimpan dan mengupload data file raw besar seperti audio, video, foto, dll.

### 6. Hosting

Platform: Web

{{< youtube jsRVHeQd5kU>}}

Pada fitur ini kita dapat hosting web ataupun lainya secara statik maupun dinamis menggunakan fitur microservice yang disedikan oleh Firebase. Dengan kecepatan yang lumayan cepat karena berjalan pada Cloud dan CDN.

### 7. Functions

Platform: IOS, Android, C++, Web, Unity

{{< youtube vr0Gfvp5v1A>}}

Cloud Function untuk Firebase ini sebagai Serverless framework otomatis dijalankan sebagai backend yang menghandle ketika request trigger HTTP. Pada function ini dijalankan/digunakan dengan bahasa pemrograman TypeScript dan JavaScript. Di Function ini tidak perlu manage scalable server, jadi lebih mudah.

### 8. Machine Learning

Platform: IOS, Android

{{< youtube p5-BDRCAkMI>}}

Pada fitur ini Anda dapat bermain-main fitur Machine Learning dengan custom model Anda sendiri, tanpa perlu menyiapkan Machine Learning dan buat sendiri, yang dimana/biasanya proses ini membutuhkan biaya yang mahal. Dan di firebase ini bisa Anda akses gratis.

### 9. Cloud Messaging

Platform: IOS, Android, WEB, C++, Unity

{{<youtube sioEY4tWmLI>}}

Pada fitur ini Anda dapat mengirimkan dan menganalisis notifikasi yang dikirimkan ke user pada App Anda, fitur ini enak sekali sangat simple buat notifikasi tanpa ribet, untuk berbagai platform yang di support oleh Firebase tersebut.

Dan masih banyak sekali fitur firebase yang tidak bisa saya sebutkan satu-persatu dan jelaskan.

Cukup sekian dari Saya semoga bermanfaat :)