# Lab: Mengunci Dependensi Koleksi dengan requirements.yml

## Tujuan Lab
Menyusun file manifes requirements.yml deklaratif dan menginstal seluruh dependensi secara otomatis dalam satu langkah.

## Prasyarat
- Paham format YAML requirements

## Langkah-langkah Pengerjaan
1. Lengkapi file `requirements.yml` dengan dependensi koleksi (misal `ansible.posix` versi `>=1.4.0`).
2. Jalankan perintah instalasi: `ansible-galaxy install -r requirements.yml`.
3. Amati proses download dan verifikasi hash paket.

## Kriteria Berhasil (Checklist)
- [ ] File requirements.yml valid dan memuat spesifikasi versi yang jelas
- [ ] Seluruh dependensi terinstal secara serentak via flag `-r`
