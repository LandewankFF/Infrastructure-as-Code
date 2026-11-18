# CLI ansible (Ad-hoc Commands)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Perintah `ansible` digunakan untuk menjalankan operasi ad-hoc, yaitu eksekusi satu modul tunggal pada managed nodes tanpa perlu membuat file playbook terlebih dahulu. Perintah ad-hoc sangat ideal untuk tugas-tugas administratif cepat, seperti mengecek ketersediaan server dengan modul `ping`, memeriksa disk usage, me-reboot mesin, atau menginstal paket darurat. Sintaks dasarnya membutuhkan pola host target, path inventory (`-i`), modul yang dipanggil (`-m`), serta argumen modul (`-a`). Meskipun cepat, operasi ad-hoc tidak terdokumentasi dalam kode versi seperti halnya playbook, sehingga penggunaannya biasanya terbatas pada investigasi atau otomasi one-off.

## Contoh singkat
```bash
# Mengecek pemakaian disk di semua webserver menggunakan modul command
ansible webservers -i inventory.ini -m ansible.builtin.command -a "df -h /"
```

## Referensi resmi
- [Ansible Command Guide](https://docs.ansible.com/ansible/latest/command_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
