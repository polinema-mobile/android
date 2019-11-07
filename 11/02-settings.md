# Settings

Anda dapat mengatur kebutuhan aplikasi sesuai dengan kebutuhan pengguna.
Pengaturan ini akan disimpan dalam `SharedPreferences`. Untuk memudahkan, anda
dapat menggunakan library `androidx.preference`. Silahkan tambahkan library ke
dalam file `build.gradle` (app).

```
implementation 'androidx.preference:preference:1.1.0'
```

## Hirarki dan Widget

Untuk membangun pengaturan pada pengguna. Anda tinggal mendefinisikan sebuah
skema yang dibungkus dalam `PreferenceScreeen`. Untuk mengelompokkan pengaturan
anda dapat menggunakan `PreferenceCategory`. Selain itu dalam pengaturan juga
dikenal bermacam widget yang umum digunakan antara lain:

- `CheckBoxPreference`
- `EditTextPreference`
- `ListPreference`
- `MultiSelectListPreference`
- `SeekbarPreference`
- `SwitchPreference`

Penggunaan widget yang dibutuhkan, disesuaikan dengan jenis data yang akan
disimpan.

## Pembuatan Pengaturan

Untuk menampilkan pengaturan yang diinginkan, buatlah sebuah fragment yang
diturunkan dari class `PreferenceFragmentCompat`. Dalam class tersebut, override
method `onCreatePreferences` dan atur resource file xml yang dibutuhkan dengan
menggunakan method `setPreferencesFromResource(R.xml.nama_pref, rootKey)`.

## Langkah Percobaan

- Bukalah project SettingsExample dari repository yang telah anda fork.
 Tunggu proses build sampai selesai serta pelajari susunan starter code yang
 telah disiapkan.

- Bukalah file `preferences.xml`, dan salin kode berikut:

```xml
<PreferenceScreen
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">

    <PreferenceCategory
        android:title="@string/basic_preferences">

        <Preference
            android:key="preference"
            android:title="@string/title_basic_preference"
            android:summary="@string/summary_basic_preference"/>

        <Preference
            android:key="icon"
            android:title="@string/title_icon_preference"
            android:summary="@string/summary_icon_preference"
            android:icon="@android:drawable/ic_menu_camera"/>

        <Preference
            android:key="single_line_title"
            android:title="@string/title_single_line_title_preference"
            android:summary="@string/summary_single_line_title_preference"
            app:singleLineTitle="true"/>
    </PreferenceCategory>

    <PreferenceCategory
        android:title="@string/widgets">

        <CheckBoxPreference
            android:key="checkbox"
            android:title="@string/title_checkbox_preference"
            android:summary="@string/summary_checkbox_preference"/>

        <SwitchPreferenceCompat
            android:key="switch"
            android:title="@string/title_switch_preference"
            android:summary="@string/summary_switch_preference"/>

        <DropDownPreference
            android:key="dropdown"
            android:title="@string/title_dropdown_preference"
            android:entries="@array/islands"
            app:useSimpleSummaryProvider="true"
            android:entryValues="@array/islands"/>

        <SeekBarPreference
            android:key="seekbar"
            android:title="@string/title_seekbar_preference"
            android:max="10"
            android:defaultValue="5"/>
    </PreferenceCategory>

    <PreferenceCategory
        android:title="@string/dialogs">

        <EditTextPreference
            android:key="edittext"
            android:title="@string/title_edittext_preference"
            app:useSimpleSummaryProvider="true"
            android:dialogTitle="@string/dialog_title_edittext_preference"/>

        <ListPreference
            android:key="list"
            android:title="@string/title_list_preference"
            app:useSimpleSummaryProvider="true"
            android:entries="@array/islands"
            android:entryValues="@array/islands"
            android:dialogTitle="@string/dialog_title_list_preference"/>

        <MultiSelectListPreference
            android:key="multi_select_list"
            android:title="@string/title_multi_list_preference"
            android:summary="@string/summary_multi_list_preference"
            android:entries="@array/islands"
            android:entryValues="@array/islands"
            android:dialogTitle="@string/dialog_title_multi_list_preference"/>
    </PreferenceCategory>

    <PreferenceCategory
        android:key="advanced"
        android:title="@string/advanced_attributes"
        app:initialExpandedChildrenCount="1">

        <Preference
            android:key="expandable"
            android:title="@string/title_expandable_preference"
            android:summary="@string/summary_expandable_preference"/>

        <Preference
            android:title="@string/title_intent_preference"
            android:summary="@string/summary_intent_preference">

            <intent android:action="android.intent.action.VIEW"
                android:data="http://www.android.com"/>

        </Preference>

        <SwitchPreferenceCompat
            android:key="parent"
            android:title="@string/title_parent_preference"
            android:summary="@string/summary_parent_preference"/>

        <SwitchPreferenceCompat
            android:key="child"
            android:dependency="parent"
            android:title="@string/title_child_preference"
            android:summary="@string/summary_child_preference"/>

        <SwitchPreferenceCompat
            android:key="toggle_summary"
            android:title="@string/title_toggle_summary_preference"
            android:summaryOn="@string/summary_on_toggle_summary_preference"
            android:summaryOff="@string/summary_off_toggle_summary_preference"/>

        <Preference
            android:key="copyable"
            android:title="@string/title_copyable_preference"
            android:summary="@string/summary_copyable_preference"
            android:selectable="false"
            app:enableCopying="true"/>
    </PreferenceCategory>

</PreferenceScreen>
```

- Amati dan pelajari hasil luaran, pada tab design.
- Tambahkan file `SettingsFragment` pada package fragments dengan menggunakan template java class.
- Definisikan class `SettingsFragment` yang diturunkan dari `PreferenceFragmentCompat`

  ```java
  public class SettingsFragment extends PreferenceFragmentCompat {

  }
  ```

- Implementasikan method yang wajib di override pada turunan dari
 `PreferenceFragmentCompat`, anda dapat menggunakan shortcut `Alt + Enter`.
 Android Studio akan menambahkan secara otomatis method `onCreatePreferences()`.

- Atur logika pada method `onCreatePreferences()` dengan menambahkan kode
 untuk mengatur layout preferences yang diinginkan. Kode final dari implementasi
 ini, sebagai berikut.

  ```java
  @Override
  public void onCreatePreferences(Bundle savedInstanceState, String rootKey) {
      setPreferencesFromResource(R.xml.preferences, rootKey);
  }
  ```
- Pada tahapan ini, anda telah berhasil untuk membuat pengaturan aplikasi
 android.
- Silahkan anda buka file `Application.java`, file ini berisi instansiasi
 SharedPreferences yang dapat diakses dari satu project android. Pendekatan ini
 digunakan untuk memudahkan akses dan instansiasi object SharedPreferences.

- Untuk mendapatkan akses SharedPreferences anda dapat menggunakan kode berikut.

  ```java
  SharedPreferences preferences = Application.getPreferences();
  ```

- Selanjutnya, perhatikan pada fragment `WidgetsFragment`, `DialogsFragments`
 serta `AdvancedFragment`. Anda akan menjumpai logika untuk pengambilan nilai
 pengaturan yang tersimpan pada SharedPreferences.

- Jalankan aplikasi serta amati perubahan yang terjadi.
