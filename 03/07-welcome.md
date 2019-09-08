# Welcome Activity

Welcome activity adalah activity yang di jalankan setelah splash screen. Pada activity welcome ini, akan ditampilkan secara singkat fitur-fitur aplikasi. Berikut ini screenshoot tampilan aplikasi yang diharapkan.

![welcome](images/welcomeactivity.png)

## Edit File activity_welcome_slide.xml

Langkah selanjutnya adalah mengubah isi file `activity_welcome_slide.xml`. Jenis
layout yang digunakan adalah constraint layout. Pastikan layout xml dimulai
dengan tag berikut ini. Tambahkan background warna putih.

```xml
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#FFFFFF"
    tools:context=".WelcomeSlide">

</android.support.constraint.ConstraintLayout>
```

Pada desain layout terdapat beberapa komponen, yaitu:

1. Gambar Character dengan Calender
2. Text Welcome
3. Sub Text Welcome
4. Text Login
5. Background Footer Merah

### Tambahkan Gambar

Tambahkan gambar dengan nama `ic_eventlist` dari folder drawable ke layout

```xml
<ImageView
  android:id="@+id/calendar"
  android:layout_width="wrap_content"
  android:layout_height="wrap_content"
  android:src="@drawable/ic_eventlist"
  app:layout_constraintTop_toTopOf="parent"
  app:layout_constraintLeft_toLeftOf="parent"
  app:layout_constraintRight_toRightOf="parent"
  android:layout_marginTop="30dp"
  />
```

Perhatikan penamaan **id** dan **constraint** dari image

![image](images/0305layout2.png)

## Tambahkan Text

Tambahkan sebuah `TextView` dengan id `welcome_text`. Ganti isi teks dengan
sesuai keinginan anda, sebagai contoh: **Welcome To DTS VSGA**

```xml
<TextView
  android:id="@+id/welcome_text"
  android:layout_width="wrap_content"
  android:layout_height="wrap_content"
  android:textSize="24sp"
  android:textColor="#313131"
  android:text="Welcome To DTS VSGA"
  app:layout_constraintTop_toBottomOf="@id/calendar"
  app:layout_constraintLeft_toLeftOf="parent"
  app:layout_constraintRight_toRightOf="parent"
  android:fontFamily="@font/montserrat_semi_bold"
  />
```

Perhatikan bagaimana `TextView` disusun dan bagaimana cara mengganti font serta warna dari `TextView`.

![welcometext](images/0305welcometext.png)

## Tambahkan Sub Text

Tambahkan sebuah sub text baru di bawah `welcome_text` dengan id `sub_welcome`

```xml
<TextView
  android:id="@+id/sub_welcome"
  android:layout_width="wrap_content"
  android:layout_height="wrap_content"
  android:textColor="#313131"
  android:text="What is going to happen tomorrow ?"
  app:layout_constraintTop_toBottomOf="@+id/welcome_text"
  app:layout_constraintLeft_toLeftOf="parent"
  app:layout_constraintRight_toRightOf="parent"
  android:fontFamily="@font/montserrat_light"
  />
```

![subtext](images/0305subtext.png)

## Tambahkan Gambar Footer

Tambahkan gambar footer dengan membuat sebuah `ImageView` dengan id
`background_satu`. Perhatikan bahwa footer memiliki constraint ke parent bottom
dan menggunakan `scaleType` dengan value `fitXY`.

```xml
<ImageView
    android:id="@+id/background_satu"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:scaleType="fitXY"
    android:src="@drawable/bg_red"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent" />
```

![footer](images/0305footer.png)

## Tambahkan Text Login

Buatlah sebuah `TextView` dengan id `login_text`. Ganti font dengan `montserrat_light`, `textSize` sebesar `18sp` dan `textColor` dengan warna `#FFFFFF`

```xml
<TextView
    android:id="@+id/login_text"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintLeft_toLeftOf="parent"
    app:layout_constraintRight_toRightOf="parent"
    android:layout_marginBottom="72dp"
    android:textColor="#FFFFFF"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Login"
    android:textSize="18sp"
    android:fontFamily="@font/montserrat_light"
    />
```

![login](images/0305login.png)
