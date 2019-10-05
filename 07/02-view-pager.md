# View Pager

View Pager merupakan fitur untuk membagi konten yang panjang pada android menjadi konten yang ter bagi menjadi beberapa halaman. View pager dapat diimplementasikan menggunakan fragment atau layout xml. Pada praktikum ini akan dijelaskan bagaimana cara membuat viewpager dengan menggunakan data dari file layout xml. Berikut ini referensi bahan belajar dan tutorial :

1. https://www.androidhive.info/2016/05/android-build-intro-slider-app/

## Langkah Percobaan

- Untuk membuat viewpager dibutuhkan beberapa layout xml.
- Pada starter code anda sudah diberikan beberapa layout page yang akan di bagi kedalam view pager.
- Buatlah activity baru berilah nama `WelcomeActivity`
  ![splash](images/06.png)
  ![splash](images/07.png)
- Ubahlah kode program pada `SplashScreenActivity` agar melakukan intent ke `WelcomeActivity` seperti berikut ini :

```java
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_splash);

        new Handler().postDelayed(new Runnable() {
            @Override
            public void run() {
                startActivity(new Intent(SplashActivity.this,WelcomeActivity.class));
                finish();
            }
        },5000);
    }

```
