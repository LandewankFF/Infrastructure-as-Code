# Lab: Instalasi Koleksi Ansible Menggunakan CLI Galaxy

## Tujuan Lab
Mengunduh dan memasang koleksi dari Ansible Galaxy portal ke direktori lokal menggunakan perintah CLI ansible-galaxy.

## Prasyarat
- Koneksi internet tersedia untuk mengunduh koleksi publik

## Langkah-langkah Pengerjaan
1. Periksa direktori instalasi koleksi default di sistem Anda.
2. Jalankan `ansible-galaxy collection install community.general`.
3. Verifikasi keberadaan koleksi yang terpasang dengan `ansible-galaxy collection list`.

## Kriteria Berhasil (Checklist)
- [ ] Koleksi berhasil diinstal ke direktori koleksi lokal
- [ ] Perintah `collection list` menampilkan namespace dan versi koleksi yang terpasang
