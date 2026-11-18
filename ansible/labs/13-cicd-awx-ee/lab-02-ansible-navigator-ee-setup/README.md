# Lab: Konfigurasi dan Eksekusi via ansible-navigator

## Tujuan Lab
Mengonfigurasi file setting ansible-navigator.yml untuk menjalankan playbook di dalam kontainer Execution Environment (EE).

## Prasyarat
- Memahami konsep eksekusi berbasis container

## Langkah-langkah Pengerjaan
1. Periksa contoh file konfigurasi `ansible-navigator.yml.example`.
2. Pelajari opsi penentuan container engine (podman/docker) dan target image EE.
3. Pahami perbedaan mode antarmuka interaktif (TUI `mode: stdout` vs `mode: interactive`).

## Kriteria Berhasil (Checklist)
- [ ] File konfigurasi navigator memuat spesifikasi container engine yang benar
- [ ] Memahami cara kerja isolasi dependensi melalui Execution Environment
