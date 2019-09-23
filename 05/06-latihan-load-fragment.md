# Latihan

- Pada dynamic fragment masih terdapat sedikit bug dimana ketika `RedFragment` sudah di load, jika kita klik kembali tombol Load Red Fragment fragment tersebut kembali di load.
- Modifikasi lah kode program sehingga `RedFragment` hanya di load jika tidak ada instance `RedFragment` pada activity.
- Hint
  - Untuk mencari fragment yang sedang ada di activity bisa digunakan id atau TAG pada fragment silahkan baca link ini untuk mendapatkan solusi : https://guides.codepath.com/android/creating-and-using-fragments#looking-up-a-fragment-instance
