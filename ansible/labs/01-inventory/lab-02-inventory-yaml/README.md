# Lab: Konversi dan Penyusunan Inventory YAML

## Tujuan Lab
Menyusun inventory dalam format YAML modern menggunakan blok all, children, hosts, dan vars.

## Prasyarat
- Memahami sintaks hierarki YAML 2 spasi

## Langkah-langkah Pengerjaan
1. Lengkapi file `hosts.yml` dengan struktur `all.children`.
2. Petakan grup `webservers` dan `databases` beserta variabel per grup (misal `http_port: 80`).
3. Jalankan `ansible-inventory -i hosts.yml --list` untuk memvalidasi representasi JSON.

## Kriteria Berhasil (Checklist)
- [ ] File `hosts.yml` valid secara sintaks YAML (tidak ada karakter tab)
- [ ] Struktur grup dan variabel terbaca dengan sempurna melalui `ansible-inventory --list`
