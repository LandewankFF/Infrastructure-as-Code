# Metadata Role & Dependensi (meta/main.yml)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
File `meta/main.yml` menyimpan informasi administratif mengenai role, termasuk nama author, lisensi, platform dan distribusi OS yang didukung, serta dependensi terhadap role lain (`dependencies:`). Ketika sebuah role yang memiliki dependensi dieksekusi, Ansible akan secara otomatis menjalankan seluruh role yang didefinisikan di dalam `dependencies:` terlebih dahulu sebelum menjalankan task role itu sendiri. Hal ini memudahkan pembentukan rantai automasi, misalnya memastikan role `common` dan role `firewall` selesai dipasang sebelum role `database` mulai dieksekusi. File meta ini juga menjadi persyaratan wajib jika role hendak dipublikasikan ke portal Ansible Galaxy.

## Contoh singkat
```yaml
# meta/main.yml
galaxy_info:
  author: DevOps Team
  description: Role instalasi dan konfigurasi Nginx
  license: MIT
dependencies:
  - role: common
```

## Referensi resmi
- [Role dependencies](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html#role-dependencies)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
