# Embedded Fragment

Embedded fragment adalah fragment yang dipasang ke sebuah activity dengan cara meng-embed (memasukkannya) melalui xml activity android, dengan cara ini sebuah fragment dapat dengan cepat di integrasikan kepada sebuah xml dari activity dengan memanggil nya menggunakan tag `<fragment>`

## Langkah Percobaan

### Modifikasi Main Activity

- Bukalah project "Praktikum Fragment" menggunakan Android Studio anda.
- Buatlah sebuah package baru pada project anda dengan nama `activities`. Pada package ini nanti akan di isi activity baru yang menjadi wadah bagi fragment yang akan dibuat. Langkah pembuatannya terlihat pada gambar dibawah ini :

  1.  Buka file tree project (Alt + 1)
  2.  Arahkan Kursor ke package utama
  3.  Alt + insert untuk menampilkan floating menu
      ![layoutjava](images/01-package-name.png)
  4.  Ketikkan "package" kemudian enter dan berikan nama package yang sesuai.
      ![layoutjava](images/02-package-name.png)
      ![layoutjava](images/03-package-name.png)

- Buatlah sebuah package baru dengan nama `fragments` pada package utama project. Pada package ini nanti akan berisi seluruh fragment yang digunakan pada aplikasi, cara pembuatannya sama dengan proses pada langkah ke dua.
- Berikut ini tampilan struktur project jika anda melakukan proses ini dengan benar.
  ![layoutjava](images/04-package-name.png)
- Selanjutnya bukalah file xml `activity_main.xml` dengan menambahkan 4 buah tombol berilah attribut berikut ini :

| No  | id                     | text                     | onClick                       |
| --- | ---------------------- | ------------------------ | ----------------------------- |
| 1   | btn_static_fragment    | Contoh Static Fragment   | handlerClickStaticFragment    |
| 2   | btn_dynamic_fragment   | Contoh Dynamic Fragment  | handlerClickDynamicFragment   |
| 3   | btn_praktikum_fragment | Tugas Praktikum Fragment | handlerClickPraktikumFragment |

- _Lengkapi dengan mengenerate fungsi handler untuk masing masing tombol_ dan aturlah layout nya agar menjadi seperti pada gambar dibawah ini.
  ![layoutjava](images/05-layout-button.png)
  ![layoutjava](images/06-layout-button.png)
  ![layoutjava](images/07-layout-button.png)

### Tambah StaticActivity

- Pada package activity buatlah sebuah empty activity baru untuk menjadi wadah bagi fragment static, berilah nama activity tersebut dengan nama `StaticActivity`
  ![layoutjava](images/08-static-activity.png)

  ![layoutjava](images/09-static-activity.png)

### Modifikasi Main Activity

- Pada `MainActivity` lakukan modifikasi isi dari fungsi `handlerClickStaticFragment` sehingga ketika tombol ditekan activity berpindah dari main ke static activity.
  > Dapat dilakukan dengan menggunakan intent yang dipelajari pada chapter 04

### Tambah Fragment

- Pada package `fragments` buatlah sebuah `blank fragment` dan berilah nama `red fragment`, perhatikan proses pembuatan fragment ini dimana dua opsi `include fragment factory` dan `include iterface callback` **tidak** dipilih

  ![layoutjava](images/10-blank-fragment.png)
  ![layoutjava](images/11-blank-fragment.png)

- Ubah lah tampilan dari fragment yang baru saja dibuat menjadi seperti berikut ini.

  ![layoutjava](images/12-red-fragment.png)

- Lakukan langkah yang sama dalam membuat fragment baru dengan nama `blue fragment` dan buatlah tampilan fragment tersebut seperti pada gambar dibawah ini.

  ![layoutjava](images/13-blue-fragment.png)

### Embed Fragment ke StaticActivity

- Untuk mengembed / menempelkan fragment ke activity dapat dilakukan dengan memodifikasi xml dari activity tersebut.
- Bukalah file `activity_static` kemudian modifikasi dengan menggunakan kode program berikut ini :

```xml
    <fragment
        android:id="@+id/red_fragment_placeholder"
        android:name="polinema.ac.id.praktikumfragment.fragments.RedFragment"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintBottom_toBottomOf="parent" />
```

- Jalankan program periksa apa yang terjadi pada saat anda menekan tombol Static Fragment

## Tugas

- Ubahlah layout Static Activity, sehingga `red_fragment` yang sebelumnya mengisi penuh satu layar menjadi mengisi setengah layar dan setengah layar sisanya di isi oleh `blue_fragment`
