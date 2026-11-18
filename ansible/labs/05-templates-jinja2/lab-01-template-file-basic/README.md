# Lab: Rendering File Template Jinja2 Sederhana

## Tujuan Lab
Membuat file template MOTD (Message of the Day) berbasis Jinja2 dan merendernya ke target host menggunakan modul template.

## Prasyarat
- Paham ekspresi {{ variable }} di Jinja2

## Langkah-langkah Pengerjaan
1. Buka file `templates/motd.j2` dan gunakan variabel facts seperti `ansible_facts['hostname']` dan `ansible_facts['os_family']`.
2. Lengkapi playbook `playbook.yml` untuk memanggil modul `ansible.builtin.template` ke tujuan `/tmp/custom_motd.txt`.
3. Jalankan playbook dan periksa isi file hasil render di `/tmp/custom_motd.txt`.

## Kriteria Berhasil (Checklist)
- [ ] Template berhasil dirender tanpa error Jinja2 undefined variable
- [ ] File tujuan berisi informasi hostname dan OS yang sesuai dengan mesin lokal
