# Check Mode (Dry-run) & Diff Mode

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Check mode (`--check` atau `-C`) adalah fitur dry-run di mana Ansible menjalankan playbook dan memprediksi perubahan yang akan terjadi tanpa benar-benar memodifikasi sistem target. Sebagian besar modul bawaan mendukung check mode dan akan melaporkan status `changed` jika mendeteksi adanya ketidaksesuaian kondisi sistem dengan desired state. Diff mode (`--diff` atau `-D`) menampilkan perbandingan baris per baris sebelum dan sesudah perubahan pada file teks atau template. Menggabungkan kedua opsi (`-C -D`) menjadi standar keamanan bagi DevOps engineer untuk melakukan review audit sebelum menerapkan perubahan ke server produksi.

## Contoh singkat
```bash
# Menjalankan playbook dengan mode audit aman (dry-run & line diff)
ansible-playbook -i inventory.ini site.yml -C -D
```

## Referensi resmi
- [Validating tasks: check mode and diff mode](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_checkmode.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
