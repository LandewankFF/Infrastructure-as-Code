# Penggunaan Direktori group_vars dan host_vars

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Menyimpan variabel langsung di dalam file inventory dapat membuat inventory sulit dibaca dan melanggar prinsip modularitas. Best practice Ansible adalah memisahkan variabel ke dalam direktori khusus bernama `group_vars/` dan `host_vars/` yang diletakkan sejajar dengan file inventory atau playbook. File di dalam `group_vars/<nama_grup>.yml` akan otomatis dibaca dan diterapkan ke semua host anggota grup tersebut, termasuk `group_vars/all.yml` untuk variabel global. Variabel spesifik untuk satu host didefinisikan di `host_vars/<nama_host>.yml` dan memiliki prioritas lebih tinggi daripada variabel grup.

## Contoh singkat
```yaml
# Isi file: group_vars/webservers.yml
http_port: 80
max_clients: 200
enable_ssl: true
```

## Referensi resmi
- [Variables in Inventory](https://docs.ansible.com/ansible/latest/inventory_guide/intro_inventory.html#assigning-a-variable-to-many-machines-group-variables)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
