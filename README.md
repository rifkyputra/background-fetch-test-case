# tesheadless

A new Flutter project.


issue : Headless gagal memanggil plugin sqflite (com.tekartik.sqflite).

## UPDATE 
Issue Solved See How To Solve


## HOW TO REPRODUCE :
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


## HOW TO SOLVE

di dalam contoh ini kita dapat sukses menjalankan headless mode dengan cara\
MENGGANTI VERSI package berikut ini :

```
  keyboard_visibility: ^0.5.3\
``` 


lalu jalankan ``pub get ``










