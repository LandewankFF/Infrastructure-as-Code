# Lab: Instalasi dan Uji Ping Pertama

## Tujuan Lab
Melakukan verifikasi instalasi ansible-core di lingkungan lokal dan menguji konektivitas ad-hoc menggunakan modul ping terhadap target localhost.

## Prasyarat
- Python 3.12 terinstal di sistem Ubuntu
- Paket ansible-core terpasang di environment

## Langkah-langkah Pengerjaan
1. Periksa versi Ansible dengan perintah `ansible --version`.
2. Lengkapi file `inventory.ini` untuk mendefinisikan target host `localhost` dengan koneksi lokal.
3. Jalankan ad-hoc command menggunakan modul `ansible.builtin.ping`.
4. Catat output JSON kembalian (termasuk status `"ping": "pong"`) ke dalam `HASIL.md`.

## Kriteria Berhasil (Checklist)
- [ ] Perintah `ansible --version` menampilkan ansible-core 2.16.x dan Python 3.12.x
- [ ] Target localhost berhasil didefinisikan dengan parameter `ansible_connection=local`
- [ ] Eksekusi ad-hoc ping berhasil menghasilkan status SUCCESS dan respon 'pong'
- [ ] File HASIL.md telah terisi dengan log perintah dan output eksekusi
