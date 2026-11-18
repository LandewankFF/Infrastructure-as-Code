# Dynamic Inventory Script & Inventory Plugins

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Pada arsitektur cloud dinamis di mana instance server sering dibuat dan dimatikan (auto-scaling), inventory statis tidak lagi memadai. Ansible menyediakan Inventory Plugins modern (seperti `amazon.aws.aws_ec2`, `google.cloud.gcp_compute`, atau `azure.azcollection.azure_rm`) yang membaca konfigurasi file YAML berakhiran `.aws_ec2.yml` atau `.gcp.yml` untuk memanggil API provider secara langsung. Metode plugin ini menggantikan dynamic inventory script lama berbasis Python yang mengembalikan output JSON standar `{"_meta": {...}}`. Inventory plugins memungkinkan pembuatan grup otomatis berdasarkan tag cloud, status instance, dan availability zone secara real-time.

## Contoh singkat
```yaml
# Contoh konfigurasi inventory plugin AWS EC2: aws_ec2.yml
plugin: amazon.aws.aws_ec2
regions:
  - ap-southeast-1
keyed_groups:
  - key: tags.Environment
    separator: ""
```

## Referensi resmi
- [How to build your inventory](https://docs.ansible.com/ansible/latest/inventory_guide/intro_inventory.html)
- [Dynamic inventory](https://docs.ansible.com/ansible/latest/inventory_guide/intro_dynamic_inventory.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
