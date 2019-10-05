# Bottom Navbar

Bottom navbar adalah navigasi yang disarankan oleh android untuk menangani menu utama yang berjumlah 3 s.d 5 menu. Selain bottom navigation juga terdapat tab navigation (untuk 2 menu) dan navigation drawer (untuk lebih dari 5 menu)

## Langkah Percobaan

- Tambahkan library gradle

```gradle
    implementation 'com.google.android.material:material:1.0.0'
```

- Buatlah file xml baru dengan tipe `menu` berikan sebuah file menu dengan nama `navigation.xml`

```xml
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:id="@+id/action_food"
        android:title="Makanan"
        android:icon="@drawable/ic_food" />
    <item android:id="@+id/action_movie"
        android:title="Movie"
        android:icon="@drawable/ic_movie" />
    <item android:id="@+id/action_discount"
        android:title="Discount"
        android:icon="@drawable/ic_discount" />
</menu>

```

- Buatlah 3 buah `fragment` pada package `fragments` berilah nama `FoodFragment`, `MovieFragment` dan `DiscountFragment`

- Ubah `ActivityMain.xml` menjadi seperti berikut ini.

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".activities.MainActivity">

    <FrameLayout
        android:id="@+id/fragment_container"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:layout_behavior="@string/appbar_scrolling_view_behavior"
        />

    <com.google.android.material.bottomnavigation.BottomNavigationView
        android:id="@+id/navigation"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@color/dot_light_screen1"
        app:layout_constraintBottom_toBottomOf="parent"
        app:menu="@menu/navigation"
        />
</androidx.constraintlayout.widget.ConstraintLayout>

```

- Ubahlah MainActivity untuk implement library bottom navigation.

```java
public class MainActivity extends AppCompatActivity implements BottomNavigationView.OnNavigationItemSelectedListener
```

- Generate Implement methods dari Bottom Navigaiton View

```java
public class MainActivity extends AppCompatActivity implements BottomNavigationView.OnNavigationItemSelectedListener {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    @Override
    public boolean onNavigationItemSelected(@NonNull MenuItem menuItem) {

    }

    @Override
    public void onPointerCaptureChanged(boolean hasCapture) {

    }
}

```

- Load fragment awal pada method on create dan set listener pada bottom navigation

```java
public class MainActivity extends AppCompatActivity implements BottomNavigationView.OnNavigationItemSelectedListener {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        loadFragment(new FoodFragment());
        BottomNavigationView bottomNavigationView = findViewById(R.id.navigation);
        // beri listener pada saat item/menu bottomnavigation terpilih
        bottomNavigationView.setOnNavigationItemSelectedListener(this);
    }

    @Override
    public boolean onNavigationItemSelected(@NonNull MenuItem menuItem) {

    }

    @Override
    public void onPointerCaptureChanged(boolean hasCapture) {

    }
}

```

- buat function loader fragment

```java
public class MainActivity extends AppCompatActivity implements BottomNavigationView.OnNavigationItemSelectedListener {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        loadFragment(new FoodFragment());
        BottomNavigationView bottomNavigationView = findViewById(R.id.navigation);
        // beri listener pada saat item/menu bottomnavigation terpilih
        bottomNavigationView.setOnNavigationItemSelectedListener(this);
    }

    private boolean loadFragment(Fragment fragment) {
        if (fragment != null) {
            getSupportFragmentManager().beginTransaction()
                    .replace(R.id.fragment_container, fragment)
                    .addToBackStack(null)
                    .commit();
            return true;
        }
        return false;
    }

    @Override
    public boolean onNavigationItemSelected(@NonNull MenuItem menuItem) {

    }

    @Override
    public void onPointerCaptureChanged(boolean hasCapture) {

    }
}
```

- tambahkan logika untuk memilih fragment yang di load sesuai navigasi yang dipilih

```java
public class MainActivity extends AppCompatActivity implements BottomNavigationView.OnNavigationItemSelectedListener {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        loadFragment(new FoodFragment());
        BottomNavigationView bottomNavigationView = findViewById(R.id.navigation);
        // beri listener pada saat item/menu bottomnavigation terpilih
        bottomNavigationView.setOnNavigationItemSelectedListener(this);
    }

    private boolean loadFragment(Fragment fragment) {
        if (fragment != null) {
            getSupportFragmentManager().beginTransaction()
                    .replace(R.id.fragment_container, fragment)
                    .addToBackStack(null)
                    .commit();
            return true;
        }
        return false;
    }

    @Override
    public boolean onNavigationItemSelected(@NonNull MenuItem menuItem) {
        Fragment fragment = null;
        switch (menuItem.getItemId()) {
            case R.id.action_food:
                fragment = new FoodFragment();
                break;
            case R.id.action_movie:
                fragment = new MovieFragment();
                break;
            case R.id.action_discount:
                fragment = new DiscountFragment();
                break;
        }
        return loadFragment(fragment);
    }

    @Override
    public void onPointerCaptureChanged(boolean hasCapture) {

    }
}

```
