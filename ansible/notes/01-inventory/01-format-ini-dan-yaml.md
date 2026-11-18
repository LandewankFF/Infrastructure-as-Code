# Format File Inventory: INI vs YAML

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Inventory Ansible dapat ditulis dalam format INI maupun YAML dengan kemampuan fungsional yang setara. Format INI sangat ringkas dan mudah dibaca untuk arsitektur sederhana, di mana nama grup ditulis di dalam tanda kurung siku `[nama_grup]`. Format YAML lebih ekspresif, terstruktur, dan cocok untuk lingkungan kompleks yang memerlukan definisi variabel bersarang (nested data structure). Pemilihan format disesuaikan dengan preferensi tim, namun konsistensi dalam satu proyek sangat dianjurkan untuk menghindari kebingungan konfigurasi.

## Contoh singkat
```yaml
# Contoh inventory dalam format YAML
all:
  children:
    webservers:
      hosts:
        web01.internal:
          ansible_host: 10.0.1.10
        web02.internal:
          ansible_host: 10.0.1.11
```

## Referensi resmi
- [How to build your inventory](https://docs.ansible.com/ansible/latest/inventory_guide/intro_inventory.html)
- [Dynamic inventory](https://docs.ansible.com/ansible/latest/inventory_guide/intro_dynamic_inventory.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
