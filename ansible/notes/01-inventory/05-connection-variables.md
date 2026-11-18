# Variabel Koneksi dan Autentikasi Ansible

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Variabel koneksi adalah variabel khusus yang memberi tahu Ansible bagaimana cara menghubungi dan mengautentikasi target managed node. Parameter umum meliputi `ansible_host` (alamat IP atau hostname riil), `ansible_port` (port SSH, default 22), `ansible_user` (username SSH), dan `ansible_connection` (seperti `ssh`, `local`, `docker`, `winrm`). Selain koneksi, terdapat variabel become seperti `ansible_become`, `ansible_become_method`, dan `ansible_become_user` untuk eskalasi privilege. Variabel-variabel ini biasanya didefinisikan di dalam `group_vars/all.yml` atau per host di inventory.

## Contoh singkat
```ini
# Mendefinisikan koneksi lokal dan custom port di inventory INI
localhost ansible_connection=local
custom-box ansible_host=192.168.1.50 ansible_port=2222 ansible_user=deploy
```

## Referensi resmi
- [Behavioral inventory parameters](https://docs.ansible.com/ansible/latest/inventory_guide/intro_inventory.html#connecting-to-hosts-behavioral-inventory-parameters)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
