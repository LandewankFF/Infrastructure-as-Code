# Komparasi Mendalam: Role vs Collection

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Memahami perbedaan antara Role dan Collection sangat krusial dalam merancang arsitektur automasi yang dapat dipelihara dalam jangka panjang. Role berfokus pada alur konfigurasi terstruktur yang mengemas tasks, handlers, variables, dan templates untuk tujuan tunggal tertentu (misalnya menginstal Nginx). Sebaliknya, Collection adalah artefak packaging tingkat atas yang dapat membungkus banyak hal sekaligus: modul executable baru, berbagai jenis plugin Python (connection, lookup, callback), dokumentasi, dan bahkan beberapa roles internal di dalamnya. Singkatnya, Collection mendistribusikan kapabilitas automasi baru, sedangkan Role mendistribusikan prosedur konfigurasi terstandar.

## Contoh singkat
```yaml
# Menggunakan role yang berada di dalam sebuah collection
- name: Gunakan role dari collection
  hosts: all
  roles:
    - role: my_namespace.my_collection.my_custom_role
```

## Referensi resmi
- [Collections Guide](https://docs.ansible.com/ansible/latest/collections_guide/index.html)
- [Galaxy User Guide](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
