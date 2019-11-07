# Data Persistence 1

## SharedPreferences

Jika anda membutuhkan sekumpulan data dengan tipe key-value yang ingin anda
simpan dalam aplikasi mobile, anda dapat menggunakan `SharedPreferences` API.
Data dalam `SharedPreferences` akan disimpan dalam sebuah file yang mengandung
key-value secara berpasangan. Setiap file ini dikelola oleh Android framework
yang aksesnya dapat diatur secara private atau dibagikan. Namun dengan catatan,
data  yang dapat disimpan hanyalah data  yang tipe datanya sederhana seperti:

- String
- int/long/float
- boolean
- DateTime

Selain digunakan untuk penyimpanan data sederhana, pemanfaatan
`SharedPreferences` digunakan juga untuk menyimpan pengaturan aplikasi. Dengan
ini pengguna dapat mengatur aplikasi sesuai dengan keinginan.

## Instansiasi SharedPreferences

Ada berbagai cara untuk mendapatkan akses SharedPreferences, antara lain:

- `getSharedPreferences()` Jika anda membutuhkan lebih dari satu file yang
 diidentifikasi berdasarkan nama, dimana diatur pada parameter pertama.

   ```java
   Context context = getActivity();
   SharedPreferences pref = context.getSharedPreferences("nama pref", Context.MODE_PRIVATE);
   ```

   > **Catatan**: `Context.MODE_PRIVATE` menandakan bahwa pengaturan ini tidak
   > dibagikan ke aplikasi lain.

- `getPreferences()` Anda dapat menggunakan cara ini, jika anda membutuhkan
   sebuah pengaturan file dalam activity. Cara ini tidak membutuhkan penamaan,
   dikarenakan akan mengambil secara default yang berkaitan dengan activity.

  ```java
  SharedPreferences pref = getActivity().getPreferences(Context.MODE_PRIVATE);
  ```

- `PreferenceManager` Dapat digunakan sebagai cara alternatif cara yang kedua.
