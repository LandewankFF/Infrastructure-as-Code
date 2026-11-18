# Lab: Manipulasi Data dengan Filter & Proteksi validate

## Tujuan Lab
Mengombinasikan Jinja2 filters (default, to_nice_json, join) serta parameter validate untuk memastikan file konfigurasi aman sebelum disimpan.

## Prasyarat
- Paham penggunaan parameter validate pada modul template

## Langkah-langkah Pengerjaan
1. Buka `templates/app.conf.j2` dan manfaatkan filter `join(',')` untuk menggabungkan list IP ke dalam satu baris.
2. Di dalam `playbook.yml`, gunakan parameter `validate` (misal `grep -q 'cluster_nodes' %s`) untuk memastikan konfigurasi memiliki kata kunci wajib.
3. Uji kasus di mana validasi sengaja digagalkan dan amati bahwa file tujuan tidak disentuh sama sekali oleh Ansible.

## Kriteria Berhasil (Checklist)
- [ ] Filter Jinja2 berhasil memformat data list menjadi format string yang valid
- [ ] Parameter validate berhasil mencegah penyimpanan jika validasi mengembalikan error code
