# doc-flutter-firebase
ini dokumentasi singkat yang saya buat untuk setup flutter yang dihubungkan dengan firebase.

#### catatan: Cara kali ini menggunakan firebase-cli

- Instalasi Flutter:
  - buka VS Code kamu dan menuju kebagian terminal.
    
    ![image](https://github.com/dimasachmad2/doc-flutter-firebase/assets/17348628/747eedee-5e07-49e4-8372-0767e8c2955c)
    
  - buat projek baru flutter dengan menjalankan perintah berikut:
    
    ```bash
    $ flutter create BasicFlutter
    ```
    
  - Jika sudah dibuat, buka projek tersebut  dengan menjalankan perintah berikut:
    
    ```bash
    $ code BasicFlutter
    ```
    
- SetUp Firebase in flutter
  - Install firebase-tools

    ```bash
    $ npm install -g firebase-tools
    ```
    
  - Login ke Firebase menggunakan akun Google Anda dengan menjalankan perintah berikut:

    ```bash
    $ firebase login
    ```
    Setelah ini kamu akan diarahkan untuk login ke akun firebase kamu.
    
  - Instal FlutterFire CLI dengan menjalankan perintah berikut dari direktori mana saja:

    ```bash
    $ dart pub global activate flutterfire_cli
    ```

  - Konfigurasikan aplikasi Anda untuk menggunakan Firebase.  Jalankan perintah berikut untuk memulai alur kerja konfigurasi aplikasi:

     ```bash
    $ flutterfire configure
    ```
    Akan muncul list projek yang ada diakun firebase kamu, kamu bisa memilih list projek yang ada atau membuat projek baru untuk dihubungkan ke projek flutter kamu.
    
  - Lakukan inisialisasi Firebase di aplikasi Anda.
    
    Dari direktori project Flutter Anda, jalankan perintah berikut untuk menginstal plugin inti:
    ```bash
    $ flutter pub add firebase_core
    ```
    
    Dalam file ```lib/main.dart```, impor plugin inti Firebase dan file konfigurasi yang Anda buat sebelumnya:

     ```bash
      import 'package:firebase_core/firebase_core.dart';
      import 'firebase_options.dart';
    ```

    Selain itu, di file ```lib/main.dart```, lakukan inisialisasi Firebase menggunakan objek DefaultFirebaseOptions yang diekspor oleh file konfigurasi:

    ```bash
      await Firebase.initializeApp(
        options: DefaultFirebaseOptions.currentPlatform,
      );
    ```

    Setelah selesai, bangun ulang project Flutter Anda:

    ```bash
      $ flutter run
    ```
    
  - Kamu bisa tambahkan beberapa plugin Firebase lainya ke dalam projek flutter kamu sesuai kebutuhan.

    Dari direktori project Flutter Anda, jalankan perintah berikut:

    ```bash
      $ flutter pub add {PLUGIN_NAME}
    ```

    Selanjutnya jalankan perintah berikut untuk Anda dapat memastikan konfigurasi Firebase aplikasi Flutter sudah yang terbaru dan dapat menambahkan plugin Gradle yang diperlukan ke aplikasi Anda untuk Crashlytics dan Performance Monitoring di Android:

    ```bash
      $ flutterfire configure
    ```

    Untuk plugin apa saja yang bisa digunakan, kamu bisa langsun cek di Documentation [Firebase-Flutter](https://firebase.google.com/docs/flutter/setup?hl=id&platform=android).
    

    


