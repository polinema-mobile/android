# Backstack Pada Fragment

Goal dari penggunaan fragment pada aplikasi android adalah membuat kode program dengan prinsip one activity dan multiple fragment, artinya aplikasi akan memiliki satu activity dan banyak fragment. Dengan desain yang seperti ini pada sebuah activity hanya akan disediakan placeholder untuk fragment dan isi dari fragment di ubah sesuai kebutuhan pada saat runtime. Namun jika anda perhatikan pada praktikum dynamic fragment jika kita menekan tombol back dari activity dynamic akan langsung kembali ke activity main, untuk mengatasi hal ini harus ditambahkan sebuah back stack terhadap fragment yang di load.

## Langkah Praktikum

- Ubah lah isi fungsi handler pada dynamic activity dengan menambahkan pemanggilan ke method `addToBackStack()`

```java
    public void handleClickLoadRedFragment(View view) {
        FragmentTransaction fragmentTransaction = getSupportFragmentManager().beginTransaction();
        fragmentTransaction.replace(R.id.dynamic_fragment_placeholder,new RedFragment(),"RED_FRAGMENT");
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();
    }

    public void handleClickLoadBlueFragment(View view) {
        FragmentTransaction fragmentTransaction = getSupportFragmentManager().beginTransaction();
        fragmentTransaction.replace(R.id.dynamic_fragment_placeholder,new BlueFragment(),"BLUE_FRAGMENT");
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();
    }

```

- Jalankan kembali aplikasi dan perhatikan apa yang berubah.
