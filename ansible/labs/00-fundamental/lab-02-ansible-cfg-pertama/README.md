# Lab: Membuat dan Mengonfigurasi ansible.cfg Pertama

## Tujuan Lab
Membuat file konfigurasi `ansible.cfg` di root direktori lab untuk mengatur default inventory, nonaktifkan host key checking untuk lab, dan privilege escalation.

## Prasyarat
- Telah menyelesaikan lab-01-install-dan-ping

## Langkah-langkah Pengerjaan
1. Buat atau lengkapi file `ansible.cfg` dengan section `[defaults]` dan `[privilege_escalation]`.
2. Atur `inventory = inventory.ini` agar tidak perlu mengetik opsi `-i` secara terus menerus.
3. Nonaktifkan `host_key_checking` untuk kemudahan lingkungan pengujian lab.
4. Verifikasi setting aktif menggunakan CLI `ansible-config dump --only-changed`.

## Kriteria Berhasil (Checklist)
- [ ] File `ansible.cfg` terbaca oleh Ansible saat menjalankan perintah di direktori ini
- [ ] Perintah `ansible all -m ping` dapat dijalankan tanpa argumen `-i inventory.ini`
- [ ] Perintah `ansible-config dump --only-changed` menampilkan setting yang dikonfigurasi
