# Arsitektur Struktur Proyek Multi-Environment

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Merancang struktur repositori yang bersih dan modular adalah kunci keberhasilan automasi jangka panjang di lingkungan produksi. Praktik terbaik merekomendasikan pemisahan inventory berdasarkan environment (misal `inventories/development/` dan `inventories/production/`), masing-masing dilengkapi folder `group_vars/` dan `host_vars/` lokal agar rahasia dan IP tidak bercampur. File playbook utama (`site.yml`) bertindak sebagai master entry-point yang memanggil playbook spesifik tier (`webservers.yml`, `databases.yml`) atau roles reusable. Menyertakan file `ansible.cfg`, `.ansible-lint`, `.gitignore`, dan `requirements.yml` di root repositori memastikan standarisasi lingkungan bagi seluruh engineer.

## Contoh singkat
```text
# Pola struktur repositori enterprise yang direkomendasikan
production-repo/
├── ansible.cfg
├── requirements.yml
├── site.yml
├── inventories/
│   ├── staging/
│   └── production/
└── roles/
```

## Referensi resmi
- [Sample Ansible setup](https://docs.ansible.com/ansible/latest/tips_tricks/sample_setup.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
