# Lab: Scaffolding Skenario Pengujian Role Menggunakan Molecule

## Tujuan Lab
Menyiapkan kerangka skenario pengujian role mandiri dengan Molecule untuk memvalidasi siklus create, converge, dan verify.

## Prasyarat
- Molecule terpasang di Python virtual environment

## Langkah-langkah Pengerjaan
1. Pelajari alur siklus hidup pengujian Molecule (`create` -> `converge` -> `idempotence` -> `verify` -> `destroy`).
2. Buat role uji sederhana di folder `roles/`.
3. Inisialisasi skenario pengujian Molecule menggunakan driver docker.
4. Dokumentasikan struktur direktori `molecule/default/` pada `HASIL.md`.

## Kriteria Berhasil (Checklist)
- [ ] Memahami fungsi dari setiap tahap siklus pengujian Molecule
- [ ] File konfigurasi skenario `molecule.yml` dan `converge.yml` siap digunakan
