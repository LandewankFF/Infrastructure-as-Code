# CLI ansible-playbook & Opsi Eksekusi

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
`ansible-playbook` adalah perkakas baris perintah utama untuk mengeksekusi playbook automasi Ansible secara berurutan. Perintah ini membaca file playbook YAML, mengumpulkan facts dari host target (jika tidak dimatikan), dan menjalankan serangkaian task dengan mekanisme penanganan status. CLI ini dilengkapi fitur pengujian yang kuat seperti `--syntax-check` untuk memvalidasi sintaks sebelum eksekusi, `--check` untuk dry-run, dan `--diff` untuk melihat preview perubahan konfigurasi. Opsi pembatasan seperti `-l` (`--limit`) dan `-t` (`--tags`) memungkinkan pengembang menjalankan subset tertentu dari playbook besar.

## Contoh singkat
```bash
# Menjalankan playbook dengan mode check (dry-run) dan melihat perbedaan konfigurasi
ansible-playbook -i inventory.ini site.yml --check --diff
```

## Referensi resmi
- [Ansible Command Guide](https://docs.ansible.com/ansible/latest/command_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
