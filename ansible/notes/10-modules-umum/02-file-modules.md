# Modul Manipulasi File & Direktori

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Keluarga modul file digunakan untuk membuat, memodifikasi, mengekstrak, dan mengatur izin berkas di sistem remote. Modul `ansible.builtin.file` mengatur atribut file, symlink, dan pembuatan direktori (`state: directory`). Modul `ansible.builtin.copy` menyalin file statis dari Control Node ke remote node, sedangkan `ansible.builtin.unarchive` mengekstrak arsip terkompresi seperti `.tar.gz` atau `.zip`. Untuk mengedit baris konfigurasi tertentu tanpa mengganti seluruh isi file, `ansible.builtin.lineinfile` dan `ansible.builtin.blockinfile` memungkinkan penambahan, penggantian (via regex), atau penghapusan blok konfigurasi secara aman dan idempotent.

## Contoh singkat
```yaml
- name: Pastikan direktori ada dengan hak akses tertentu
  ansible.builtin.file:
    path: /var/log/custom_app
    state: directory
    owner: www-data
    group: www-data
    mode: '0750'
```

## Referensi resmi
- [ansible.builtin.file module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/file_module.html)
- [ansible.builtin.lineinfile module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/lineinfile_module.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
