# Lab: Menyusun Playbook Pertama & Rangkaian Tasks

## Tujuan Lab
Menyusun playbook terstruktur yang memuat deklarasi play, variabel lokal, dan serangkaian task berurutan.

## Prasyarat
- Paham sintaks YAML playbook

## Langkah-langkah Pengerjaan
1. Lengkapi file `playbook.yml` dengan play yang menargetkan `localhost`.
2. Buat task 1: Membuat direktori `/tmp/ansible-lab-03` dengan permission `0755`.
3. Buat task 2: Membuat file `/tmp/ansible-lab-03/info.txt` dengan isi teks dari variabel play.
4. Validasi playbook dengan `ansible-playbook --syntax-check playbook.yml` sebelum menjalankannya.
5. Eksekusi playbook dan amati output play recap.

## Kriteria Berhasil (Checklist)
- [ ] File playbook lolos pengujian syntax-check
- [ ] Kedua task dieksekusi dengan sukses dan idempotent saat diulang
- [ ] File dan direktori target tercipta sesuai spesifikasi permission
