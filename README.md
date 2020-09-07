# tesheadless

A new Flutter project.


issue : Headless gagal memanggil plugin sqflite (com.tekartik.sqflite).

HOW TO REPRODUCE :
`
1. clone
4. flutter run`

kesimpulan :
ada 3rd party package yang tidak compatible pada saat menjalankan headless mode.

untuk mengetahui package mana saja yang tidak kompatibel dapat dilihat\
di "app/src/main/java/io/flutter/plugin/GeneratedPluginRegistrant.java".

