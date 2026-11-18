# Multi-Password Management Menggunakan --vault-id

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Mulai Ansible 2.4 dan menjadi standar di ansible-core 2.16, opsi `--vault-id` menggantikan penggunaan opsi tunggal `--vault-password-file` lama untuk mendukung manajemen multi-password secara terlabel. Fitur ini memungkinkan Anda memisahkan rahasia untuk lingkungan yang berbeda (seperti `dev`, `staging`, `prod`) menggunakan password enkripsi yang berbeda pula dalam satu repositori yang sama. Format penulisan ID menggunakan `<label>@<source>`, di mana sumber dapat berupa prompt interaktif (`prompt`), file plaintext (`path/ke/file`), atau executable script penarik password dari password manager. Saat mengenkripsi data, Anda dapat menentukan ID label yang diinginkan, dan Ansible akan mencatat label tersebut di header cipher.

## Contoh singkat
```bash
# Menjalankan playbook dengan dua vault ID berbeda (dev dan prod)
ansible-playbook -i inventory.ini site.yml \
  --vault-id dev@.vault_pass_dev \
  --vault-id prod@prompt
```

## Referensi resmi
- [Managing multiple vault passwords](https://docs.ansible.com/ansible/latest/vault_guide/vault_managing_passwords.html#managing-multiple-vault-passwords)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
