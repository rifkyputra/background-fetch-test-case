# tesheadless

A new Flutter project.


issue : Headless gagal memanggil plugin sqflite (com.tekartik.sqflite).

HOW TO REPRODUCE :
`
1. clone
2. flutter run
3. setelah aplikasi berjalan, buka terminal jalankan 
``
adb logcat *:S flutter:V, TSBackgroundFetch:V
``
4. force close aplikasi
5. buka terminal baru, jangan tutup yg sebelumnya ``adb shell cmd jobscheduler run -f com.example.ecam.tesheadless 999 ``
6. dapat dilihat ``no implementation found com.tekartik.sqflite`` di terminal no 3
`

kesimpulan :
ada 3rd party package yang tidak compatible pada saat menjalankan headless mode.

untuk mengetahui package mana saja yang tidak kompatibel dapat dilihat\
di GeneratedPluginRegistrant --> "app/src/main/java/io/flutter/plugin/GeneratedPluginRegistrant.java".\

jika di GeneratedPluginRegistrant terdapat
```    
    ShimPluginRegistry shimPluginRegistry = new ShimPluginRegistry(flutterEngine);

```

maka dapat dipastikan headless mode tidak dapat berjalan.\

di dalam contoh ini kita dapat sukses menjalankan headless mode dengan cara\
menghapus package berikut ini :

```
  app_settings: ^4.0.1+1
  mp_chart: ^0.2.2
  keyboard_visibility: ^0.5.6
  image_picker: ^0.6.3+4
  camera: ^0.5.8+2
  flutter_form_builder: ^3.12.3
  qr_code_scanner: 0.0.11
``` 

setelah itu di GeneratedPluginRegistrant,
```    
    ShimPluginRegistry shimPluginRegistry = new ShimPluginRegistry(flutterEngine);

```
line diatas akan hilang. sehingga ketika mengulang step di HOW TO REPRODUCE, Headless Mode\
akan sukses berjalan.










