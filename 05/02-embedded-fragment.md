# Embedded Fragment

Embedded fragment adalah fragment yang dipasang ke sebuah activity dengan cara meng-embed (memasukkannya) melalui xml activity android, dengan cara ini sebuah fragment dapat dengan cepat di integrasikan kepada sebuah xml dari activity dengan memanggil nya menggunakan tag `<fragment>`

## Langkah Percobaan

1. Bukalah project "Praktikum Fragment" menggunakan Android Studio anda.
2. Buatlah sebuah package baru pada project anda dengan nama `activities`. Pada package ini nanti akan di isi activity baru yang menjadi wadah bagi fragment yang akan dibuat. Langkah pembuatannya terlihat pada gambar dibawah ini :

   1. Buka file tree project (Alt + 1)
   2. Arahkan Kursor ke package utama
   3. Alt + insert untuk menampilkan floating menu
      ![layoutjava](images/01-package-name.png)
   4. Ketikkan "package" kemudian enter dan berikan nama package yang sesuai.
      ![layoutjava](images/02-package-name.png)
      ![layoutjava](images/03-package-name.png)

3. Buatlah sebuah package baru dengan nama `fragments` pada package utama project. Pada package ini nanti akan berisi seluruh fragment yang digunakan pada aplikasi, cara pembuatannya sama dengan proses pada langkah ke dua.
4. Berikut ini tampilan struktur project jika anda melakukan proses ini dengan benar.
   ![layoutjava](images/04-package-name.png)
5. Selanjutnya bukalah file xml `activity_main.xml` dengan menambahkan 4 buah tombol berilah attribut berikut ini :

   | No  | id                   | text                    | handler                     |
   | --- | -------------------- | ----------------------- | --------------------------- |
   | 1   | btn_static_fragment  | Contoh Static Fragment  | handlerClickStaticFragment  |
   | 2   | btn_dynamic_fragment | Contoh Dynamic Fragment | handlerClickDynamicFragment |
