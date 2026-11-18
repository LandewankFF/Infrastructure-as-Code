# Pengelompokan Host & Nested Group (Children)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Pengelompokan host memungkinkan eksekusi playbook ditargetkan ke server dengan fungsi yang sama secara efisien. Ansible mendukung pembuatan grup bertingkat atau nested group menggunakan keyword `:children` pada format INI atau blok `children:` pada format YAML. Pola ini sangat berguna untuk membuat pengelompokan geografis (seperti `datacenter_asia`), lingkungan kerja (seperti `production` yang membawahi `prod_web` dan `prod_db`), atau arsitektur multi-tier. Sebuah host dapat menjadi anggota dari beberapa grup sekaligus tanpa menduplikasi definisi host tersebut.

## Contoh singkat
```ini
# Format INI dengan nested group (:children)
[web_prod]
prod-web01.example.com
prod-web02.example.com

[db_prod]
prod-db01.example.com

[production:children]
web_prod
db_prod
```

## Referensi resmi
- [How to build your inventory](https://docs.ansible.com/ansible/latest/inventory_guide/intro_inventory.html)
- [Dynamic inventory](https://docs.ansible.com/ansible/latest/inventory_guide/intro_dynamic_inventory.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
