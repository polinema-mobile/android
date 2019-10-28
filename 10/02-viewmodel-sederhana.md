# ViewModel Sederhana

## Langkah Percobaan 1

- Bukalah project **ColorChangerNormal** dari repository starter code yang telah
 disediakan.
- Perhatikan layout `activity_main.xml`, pada layout tersebut terdapat sebuah
 tombol yang  ketika ditekan akan merubah warna secara acak.
- Bukalah file `MainActivity.java`, pahami kode yang telah disiapkan.
- Pada file `MainActivity.java` terdapat sebuah method untuk menggenerate warna
 secara acak dengan format RGB.
- Tambahkan event click pada block method `onCreate()` seperti pada kode berikut

  ```java
  btnChangeColor.setOnClickListener(new View.OnClickListener() {
      @Override
      public void onClick(View view) {
          int color = generateRandomColor();
          rootView.setBackgroundColor(color);
      }
  });
  ```

- Deploy project ke device atau emulator!
- Tekan tombol **Ganti Warna**, kemudian coba rotate dari layout *portrait* ke
 *landscape* atau sebaliknya.
- Perhatikan apa yang terjadi pada aplikasi tersebut.
- Lakukan commit kemudian push project ke repository anda masing-masing.

## Langkah Percobaan 2
- Pada percobaan sebelumnya, ketika orientation berubah maka informasi warna
 akan berubah juga.
- Untuk menghindari terjadinya hal ini Android Jetpack merekomendasikan
 menggunakan arsitektur ViewModel.
- Untuk menggunakan ViewModel, silahkan tambahkan library pada `build.gradle`

  ```gradle
  implementation 'androidx.lifecycle:lifecycle-extensions:2.1.0'
  annotationProcessor 'androidx.lifecycle:lifecycle-compiler:2.1.0'
  ```
- Lakukan sync dan tunggu sampai proses build selesai.

- Tambahkan class `ColorViewModel` untuk  menyimpan informasi warna background
 aplikasi.

  ```java
  public class ColorViewModel extends AndroidViewModel {

    private int color = 0xfff;

    public ColorViewModel(@NonNull Application application) {
      super(application);
    }

    public int getColor() {
      return color;
    }

    public void setColor(int color) {
      this.color = color;
    }
  }
  ```
- Tambahkan atribut `colorViewModel` dengan tipe `ColorViewModel`

  ```java
  ConstraintLayout rootView;
  Button btnChangeColor;
  // Tambahkan ViewModel
  ColorViewModel colorViewModel;
  ```

- Instansiasi ViewModel pada `onCreate()`

  ```java
  colorViewModel = ViewModelProviders.of(this).get(ColorViewModel.class);
  ```
- Ganti background, tetapi gunakan informasi warna yang disimpan dalam ViewModel

  ```java
  rootView.setBackgroundColor(colorViewModel.getColor());
  ```
- Update logic pada event click, tambahkan proses untuk menyimpan warna pada
 ViewModel

  ```java
  colorViewModel.setColor(color);
  ```

- Deploy kembali pada device atau emulator, kemudian perhatikan apa bedanya.
 Coba ubah orientation portrait ke landscape dan sebaliknya.
- Commit dan push perubahan ke repository anda masing-masing.
