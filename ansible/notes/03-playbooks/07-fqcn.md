# Standar Fully Qualified Collection Name (FQCN)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Fully Qualified Collection Name (FQCN) adalah standar penamaan canonical lengkap untuk modul, action plugins, dan lookup plugins dalam arsitektur modern Ansible (`namespace.collection.plugin`). Sebelum arsitektur collections diperkenalkan, modul dipanggil dengan nama pendek seperti `copy` atau `apt`, namun sejak Ansible 2.10 dan ansible-core 2.16, penggunaan FQCN seperti `ansible.builtin.copy` menjadi aturan baku best practice. Standar ini mencegah ambiguitas jika ada dua modul berbeda dengan nama yang sama yang berasal dari koleksi yang berbeda (misalnya modul `docker_container` pada `community.docker` vs koleksi pihak ketiga lainnya). `ansible-lint` akan memberikan peringatan pelanggaran jika FQCN tidak digunakan.

## Contoh singkat
```yaml
# Penggunaan FQCN sesuai standar modern Ansible 2.16
- name: Membuat direktori web
  ansible.builtin.file:
    path: /var/www/my-app
    state: directory
    mode: '0755'
```

## Referensi resmi
- [Collections Guide](https://docs.ansible.com/ansible/latest/collections_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
