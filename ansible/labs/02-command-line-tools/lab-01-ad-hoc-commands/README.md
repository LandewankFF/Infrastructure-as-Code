# Lab: Eksplorasi Perintah Ad-Hoc Ansible

## Tujuan Lab
Melatih penggunaan perintah baris tunggal CLI ansible dengan berbagai modul seperti command, shell, copy, dan service.

## Prasyarat
- ansible CLI siap di terminal

## Langkah-langkah Pengerjaan
1. Jalankan ad-hoc dengan modul `command` untuk memeriksa `uname -a` pada localhost.
2. Jalankan ad-hoc dengan modul `copy` untuk membuat file `/tmp/adhoc-test.txt`.
3. Bandingkan perbedaan eksekusi pertama (changed: true) dengan eksekusi kedua (changed: false) untuk mengamati idempotensi.
4. Dokumentasikan seluruh perintah dan output pada `HASIL.md`.

## Kriteria Berhasil (Checklist)
- [ ] Berhasil menjalankan perintah ad-hoc menggunakan flag `-m` dan `-a`
- [ ] Mengamati perbedaan status `changed` vs `ok` pada eksekusi berulang
- [ ] File pengujian berhasil dibuat di target
