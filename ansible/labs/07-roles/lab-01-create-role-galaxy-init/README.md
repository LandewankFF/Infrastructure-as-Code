# Lab: Scaffolding Role Baru Menggunakan CLI ansible-galaxy

## Tujuan Lab
Membuat kerangka struktur direktori role terstandarisasi menggunakan command ansible-galaxy role init dan memanggilnya dari playbook utama.

## Prasyarat
- ansible-galaxy CLI tersedia

## Langkah-langkah Pengerjaan
1. Masuk ke direktori lab dan jalankan `ansible-galaxy role init roles/web_server`.
2. Periksa pohon struktur direktori role yang terbentuk (`tasks`, `handlers`, `vars`, `defaults`, `templates`, `meta`).
3. Isi task sederhana pada `roles/web_server/tasks/main.yml`.
4. Panggil role tersebut di dalam file `site.yml` dan jalankan.

## Kriteria Berhasil (Checklist)
- [ ] Struktur direktori role terbentuk lengkap dan sesuai konvensi resmi
- [ ] Role berhasil dipanggil dan dieksekusi dari file `site.yml`
