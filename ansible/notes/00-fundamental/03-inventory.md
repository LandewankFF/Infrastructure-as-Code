# Pengenalan Konsep Inventory

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Inventory adalah komponen fundamental Ansible yang mendefinisikan daftar host target yang akan dikelola serta bagaimana host-host tersebut dikelompokkan secara logis. Ansible menggunakan inventory untuk mengetahui server mana saja yang menjadi target eksekusi task, port yang digunakan, user SSH, serta variabel spesifik per grup atau per host. File inventory dapat ditulis dalam format sederhana INI atau YAML, dan dapat berupa file statis tunggal maupun direktori yang memuat dynamic inventory plugin untuk mengambil data host dari cloud provider. Pemahaman pengelompokan host (grup dan subgrup) sangat penting untuk menerapkan konfigurasi hanya pada server tertentu, misalnya webserver atau database.

## Contoh singkat
```ini
# Contoh inventory sederhana dalam format INI
[webservers]
web1.example.com ansible_host=192.168.1.11
web2.example.com ansible_host=192.168.1.12

[databases]
db1.example.com ansible_host=192.168.1.21
```

## Referensi resmi
- [How to build your inventory](https://docs.ansible.com/ansible/latest/inventory_guide/intro_inventory.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
