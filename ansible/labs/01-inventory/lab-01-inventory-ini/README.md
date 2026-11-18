# Lab: Menyusun Inventory Format INI

## Tujuan Lab
Menyusun file inventory format INI yang memuat beberapa grup server (web, database), host variables inline, dan nested group.

## Prasyarat
- Memahami sintaks dasar format INI

## Langkah-langkah Pengerjaan
1. Buka file `hosts.ini` dan definisikan grup `[webservers]` dengan 2 host dummy.
2. Definisikan grup `[databases]` dengan 1 host dummy.
3. Buat nested group `[production:children]` yang menggabungkan grup webservers dan databases.
4. Uji keabsahan struktur inventory menggunakan `ansible-inventory -i hosts.ini --graph`.

## Kriteria Berhasil (Checklist)
- [ ] File `hosts.ini` tersusun rapi dengan pengelompokan yang diminta
- [ ] Nested group `production` berhasil membawahi `webservers` dan `databases`
- [ ] Output visual `ansible-inventory --graph` menampilkan hierarki pohon yang benar
