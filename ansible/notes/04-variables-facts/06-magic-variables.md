# Magic Variables (hostvars, groups, group_names)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Magic variables adalah sekumpulan variabel khusus bawaan Ansible yang secara otomatis diinjeksi ke dalam eksekusi dan tidak boleh didefinisikan ulang secara manual oleh pengguna. Variabel `hostvars` memungkinkan sebuah host mengakses variabel atau facts dari host lain di inventory, yang sangat krusial saat menyusun konfigurasi cluster atau load balancer (misal mendaftarkan IP backend ke template proxy). Variabel `groups` berisi kamus seluruh grup beserta daftar anggotanya, sedangkan `group_names` memuat daftar grup di mana host yang sedang dieksekusi bernaung. Variabel `inventory_hostname` menyimpan nama pengenal unik host sesuai yang tercantum di file inventory.

## Contoh singkat
```yaml
# Mengakses IP internal dari host database pada task di webserver
- name: Tampilkan IP host database
  ansible.builtin.debug:
    msg: "Alamat DB: {{ hostvars['db01.example.com']['ansible_default_ipv4']['address'] }}"
```

## Referensi resmi
- [Special Variables](https://docs.ansible.com/ansible/latest/reference_appendices/special_variables.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
