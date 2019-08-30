# Integrasi Git Android Studio

## Git

Git adalah Version Control System (VCS) terdistribusi yang diciptakan oleh Linus
Torvalds. Digunakan sebagai perkakas bantu untuk bekerja antar para programmer.
Git digunakan untuk melacak perubahan pada berkas-berkas code. Pada praktikum
ini digunakan [GitHub](https://github.com) yang merupakan salah satu penyedia layanan Git di cloud.

## Akun GitHub

Sebelum melakukan langkah-langkah berikut, pastikan anda telah memiliki akun
[GitHub](http://github.com) terlebih dahulu. Untuk melakukan registrasi silahkan
klik tautan [Join Github](https://github.com/join) berikut. Kemudian lengkapi
formulir isian yang dibutuhkan.

## Setup GitHub pada Android Studio

Pada praktikum pemrograman mobile, digunakan Android Studio sebagai Git Client.
Terdapat beberapa langkah untuk menyiapkannya. Silahkan ikuti langkah-langkah
berikut:

- Buka aplikasi terminal (cmd) pada sistem operasi anda
- Untuk memeriksa apakah sudah terdapat setting akun Git, jalankan perintah `git
 config --global --get user.email`. Jika hasil perintah kosong, maka anda perlu
 mengkonfigurasi akun Git terlebih dahulu.
- Jalankan perintah di bawah ini untuk mengatur informasi akun Git berupa email
 (email akun GitHub) dan nama anda.

  ```
  git config --global  user.email "<youremail>@email.com"
  git config --global  user.name "<your name>"
  ```
