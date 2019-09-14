# Intent

Membuat aplikasi mobile khususnya Android, mungkin membutuhkan lebih dari satu
activity. Pengolahan data atau menjalankan tugas tidak memungkinkan dilakukan
pada UI main thread, karena jika tugas ini membutuhkan waktu yang lama aplikasi
akan mengalami force close. Aplikasi Android juga menjalankan tugas berdasarkan
event yang diterima. Hal-hal ini dapat dilakukan menggunakan konsep Intent.

## Pengertian Intent

Intent merupakan sebuah mekanisme yang digunakan untuk melakukan sebuah aksi
dari komponen aplikasi. Untuk dapat melakukan sebuah aksi pada sebuah intent,
ada 3 cara yang dapat dilakukan:

- Menjalankan sebuah activity lain baik dengan data ataupun tanpa data
- Membuat sebuah service untuk menjalankan pekerjaan tertentu pada sebuah
 background/non main thread.
- Mengirimkan sebuah broadcast. Pesan yang dikirimkan dalam keadaan tertentu,
 misalkan ketika booting atau sedang melakukan pengisian data baru mengirimkan
 data.

Terdapat 2 model Intent dalam pemrograman Android yaitu:

### Explicit Intent

Dikatakan intent explicit karena intent tersebut biasanya dibuat oleh seorang
programmer berdasarkan kebutuhan yang ada. Untuk memanggil intent tersebut
biasanya digunakan nama kelas, misalkan `id.ac.polinema.WelcomeActivity`

### Implicit Intent

Model intent ini sebaliknya dari intent explicit, kita tidak perlu menggunakan
nama kelas untuk memanggilnya. Intent model ini sudah disediakan oleh system
android, sebagai contoh kita akan melakukan pemanggilan telp maka seorang
programmer tanpa harus membuat intent untuk melakukan pemanggilan telp.

## Komunikasi Data dengan Intent

Antara Activity satu dengan Activity yang lain dapat saling berkomunikasi. Tipe
data primitif sudah didukung secara langsung oleh Intent.

### Intent dengan ResultActivity

Intent dengan ResultActivity berkaitan dengan sebuah perpindahan dari Activity
satu ke Activity yang lain. Jadi ada kebutuhan ketika ada sebuah Activity yang
dijalankan oleh Activity pemanggilnya menginginkan nilai balik/kembalian.
Activity dapat mengembalikan nilai balik ketika sudah ditutup. Misalkan Activity
A memanggil Activity B, Activity A dapat menrima nilai tertentu dari Activity B
setelah Activity B ditutup.

### Explicit Intent dengan Parcelable

Dengan menggunakan parcelable kita tidak hanya dapat melewatkan sebuah nilai
pada sebuah Intent, tetapi dapat juga melewatkan sebuah obyek. Obyek yang akan
dilewatkan melalui Intent dengan implement interface Parcelable.

