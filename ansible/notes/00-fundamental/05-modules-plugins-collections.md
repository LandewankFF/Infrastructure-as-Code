# Modules, Plugins, dan Collections

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Ansible membagi fungsionalitasnya ke dalam modul, plugin, dan koleksi. Modul adalah unit kode executable diskrit yang ditransfer ke managed node untuk menjalankan pekerjaan nyata (seperti menginstal paket atau membuat user) dan mengembalikan format JSON standar. Plugin adalah potongan kode Python yang memperluas fungsi inti Ansible dan berjalan di Control Node, seperti connection plugin (SSH, Docker), lookup plugin (membaca file/env), dan filter plugin (manipulasi data Jinja2). Collections adalah format distribusi modular standar modern (diperkenalkan sejak Ansible 2.9/2.10) yang membungkus modules, plugins, roles, dan documentation ke dalam namespace terpadu untuk memudahkan versioning dan distribusi independen dari core Ansible.

## Contoh singkat
```yaml
# Memanggil modul dari koleksi standar (ansible.builtin) menggunakan FQCN
- name: Membuat user aplikasi
  ansible.builtin.user:
    name: deployer
    state: present
    shell: /bin/bash
```

## Referensi resmi
- [About collections](https://docs.ansible.com/ansible/latest/collections_guide/index.html)
- [Plugin documentation](https://docs.ansible.com/ansible/latest/plugins/plugins.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
