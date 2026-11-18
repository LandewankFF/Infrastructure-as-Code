# Lab: Membangun Dependensi Antar-Role via meta/main.yml

## Tujuan Lab
Mengonfigurasi rantai dependensi role di mana eksekusi role aplikasi otomatis memicu jalannya role prasyarat (common/base).

## Prasyarat
- Paham format meta/main.yml

## Langkah-langkah Pengerjaan
1. Buat dua role: `base_role` dan `app_role`.
2. Buka `roles/app_role/meta/main.yml` dan tambahkan `dependencies: - role: base_role`.
3. Di dalam `site.yml`, hanya panggil `app_role`.
4. Verifikasi bahwa task dari `base_role` dieksekusi terlebih dahulu sebelum task `app_role` dijalankan.

## Kriteria Berhasil (Checklist)
- [ ] Role dependensi dieksekusi secara otomatis tanpa dideklarasikan manual di playbook
- [ ] Urutan eksekusi berjalan logis dari dependensi menuju role utama
