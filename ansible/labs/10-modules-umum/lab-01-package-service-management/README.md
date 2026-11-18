# Lab: Otomasi Manajemen Paket dan Service Linux

## Tujuan Lab
Menggunakan modul package, apt, dan service/systemd untuk menginstal web server, memastikan service aktif, dan enable saat boot.

## Prasyarat
- Akses sudo pada sistem target jika menguji ke sistem riil

## Langkah-langkah Pengerjaan
1. Buka `package-service.yml` dan lengkapi task instalasi paket `curl` dan `nginx` (atau paket lokal lain).
2. Tambahkan task untuk memastikan service berstatus `started` dan `enabled: true`.
3. Jalankan playbook dan periksa keabsahan status service.

## Kriteria Berhasil (Checklist)
- [ ] Paket berhasil dipasang dengan kondisi state present
- [ ] Service terverifikasi aktif dan berjalan di background
