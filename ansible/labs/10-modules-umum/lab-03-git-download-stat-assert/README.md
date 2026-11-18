# Lab: Utilitas Sistem: Git, Download, Stat, dan Assert

## Tujuan Lab
Menggunakan get_url untuk download aset, stat untuk verifikasi kondisi berkas, assert untuk validasi logika, dan git untuk kloning repositori.

## Prasyarat
- Koneksi internet untuk mendownload aset

## Langkah-langkah Pengerjaan
1. Lengkapi `utility-play.yml` dengan task `ansible.builtin.get_url` untuk mengunduh file publik ke direktori `/tmp`.
2. Gunakan modul `ansible.builtin.stat` untuk memeriksa checksum atau keberadaan file tersebut.
3. Gunakan `ansible.builtin.assert` untuk memvalidasi bahwa file memang ada dan ukurannya lebih besar dari 0 byte.

## Kriteria Berhasil (Checklist)
- [ ] Aset berhasil diunduh secara idempotent
- [ ] Modul stat berhasil menangkap metadata file ke register variable
- [ ] Task assert lolos validasi tanpa menghentikan playbook
