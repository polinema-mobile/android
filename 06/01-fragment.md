# Komunikasi Fragment

Fragment sebaiknya secara umum hanya berkomunikasi dengan direct parent
activity. Activity bertindak sebagai controller yang mengatur semua interaksi
yang terjadi pada Fragment. Ada beberapa pengecualian, dialog fragment dan
nested child fragment. Kedua kasus ini yang bertindak sebagai controllernya
adalah parent fragment.

Hal yang perlu diperhatikan adalah, fragment sebaiknya tidak berkomunikasi
secara langsung dengan fragment lain tetapi melalui parent. Fragment bersifat
modular, dan merupakan komponen yang bisa digunakan kembali (*reusable*).

Ada tiga cara sebuah fragment dan activity berkomunikasi, antara lain:

1. **Bundle**
2. **Listener**
3. **Method**

# Referensi

- [CodePath - Communicating with Fragments](https://guides.codepath.com/android/Creating-and-Using-Fragments#communicating-with-fragments)
