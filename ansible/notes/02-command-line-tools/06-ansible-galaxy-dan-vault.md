# CLI ansible-galaxy & ansible-vault Overview

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
`ansible-galaxy` dan `ansible-vault` adalah dua utilitas penting yang mendukung siklus hidup proyek automasi Ansible tingkat lanjut. `ansible-galaxy` berfungsi sebagai client untuk mengunduh, menginstal, dan menginisialisasi roles (`ansible-galaxy role init`) serta collections dari portal Ansible Galaxy atau repositori Git privat. Sementara itu, `ansible-vault` menyediakan kapabilitas enkripsi berbasis AES-256 untuk melindungi kerahasiaan data sensitif seperti password, private key SSH, dan token API, baik dalam level file maupun variabel string tunggal (`encrypt_string`). Keduanya menjadi pilar penting dalam arsitektur kode automasi enterprise yang aman dan modular.

## Contoh singkat
```bash
# Inisialisasi struktur folder role baru menggunakan galaxy CLI
ansible-galaxy role init my_custom_role
```

## Referensi resmi
- [Ansible Command Guide](https://docs.ansible.com/ansible/latest/command_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
