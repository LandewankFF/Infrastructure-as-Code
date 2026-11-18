# Lab: Enkripsi Inline Variabel dengan encrypt_string

## Tujuan Lab
Mengamankan data rahasia individual langsung di dalam playbook YAML plaintext menggunakan ansible-vault encrypt_string.

## Prasyarat
- Paham blok !vault di dalam file YAML

## Langkah-langkah Pengerjaan
1. Jalankan `ansible-vault encrypt_string 'Rahasia123' --name 'my_secret_var'` di terminal.
2. Salin blok output YAML yang dihasilkan dan tempelkan ke bagian `vars:` pada `vault-vars-play.yml`.
3. Jalankan playbook dengan flag `--ask-vault-pass` dan pastikan nilainya terbaca dengan benar oleh task debug.

## Kriteria Berhasil (Checklist)
- [ ] Variabel rahasia terenkripsi rapi secara inline tanpa mengenkripsi file keseluruhan
- [ ] Playbook dapat dieksekusi dengan mendekripsi string rahasia saat runtime via password prompt
