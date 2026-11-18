# CLI ansible-config & Audit Konfigurasi

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
`ansible-config` digunakan untuk memeriksa, meninjau, dan mendiagnosis parameter konfigurasi `ansible.cfg` yang sedang aktif digunakan. Perintah ini membantu engineer memastikan file konfigurasi mana yang sedang diprioritaskan oleh sistem dan mendeteksi apakah suatu opsi telah ditimpa oleh environment variable. Perintah `ansible-config dump --only-changed` menampilkan daftar seluruh pengaturan yang telah diubah dari nilai default bawaan Ansible beserta sumber file konfigurasinya. Perintah `ansible-config list` menyajikan kamus lengkap seluruh opsi konfigurasi yang tersedia beserta penjelasan fungsinya.

## Contoh singkat
```bash
# Menampilkan hanya konfigurasi yang nilainya berbeda dari default bawaan
ansible-config dump --only-changed
```

## Referensi resmi
- [Ansible Command Guide](https://docs.ansible.com/ansible/latest/command_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
