# Katalog Error Umum & Panduan Solusinya

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Beberapa error klasik yang paling sering ditemui dalam penggunaan Ansible meliputi: (1) `Host key verification failed`, diatasi dengan menyetel `host_key_checking = False` di `ansible.cfg` untuk lingkungan lab atau mendaftarkan public key remote host ke `known_hosts`; (2) `Missing sudo password / Incorrect sudo password`, diatasi dengan menyertakan flag `-K` atau mengonfigurasi `sudoers` remote dengan direktif `NOPASSWD: ALL`; (3) `Undefined variable`, diatasi dengan memeriksa penulisan nama variabel atau memberikan filter `| default()`; (4) `YAML Syntax / ScannerError`, diatasi dengan memastikan tidak ada spasi tab dan mengapit ekspresi kurawal ganda `{{ ... }}` dengan tanda kutip ganda.

## Contoh singkat
```bash
# Menjalankan playbook dengan prompt password sudo saat menghadapi error privilege
ansible-playbook -i inventory.ini site.yml -b -K
```

## Referensi resmi
- [Frequently Asked Questions](https://docs.ansible.com/ansible/latest/reference_appendices/faq.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
