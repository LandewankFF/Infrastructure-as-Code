# CLI ansible-doc & Eksplorasi Dokumentasi Lokal

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
`ansible-doc` menyediakan akses langsung ke dokumentasi resmi modul, plugin koneksi, filter, dan lookup langsung dari terminal Anda tanpa memerlukan koneksi internet. Tool ini mengekstrak metadata dan blok dokumentasi yang tertanam di dalam kode modul yang terpasang pada Control Node. Menggunakan `ansible-doc <nama_modul>` akan menampilkan parameter yang didukung, tipe data, nilai default, dan contoh playbook nyata (`EXAMPLES`). Opsi `-s` (`--snippet`) menampilkan template penulisan singkat dalam format YAML yang siap disalin langsung ke dalam playbook.

## Contoh singkat
```bash
# Menampilkan snippet YAML siap pakai untuk modul file
ansible-doc -s ansible.builtin.file
```

## Referensi resmi
- [Ansible Command Guide](https://docs.ansible.com/ansible/latest/command_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
