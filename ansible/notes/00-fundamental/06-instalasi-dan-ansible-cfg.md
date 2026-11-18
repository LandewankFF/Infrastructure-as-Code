# Instalasi, File ansible.cfg, Prioritas, SSH Key, dan Become

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Instalasi Ansible modern pada Ubuntu umumnya menggunakan pip atau package manager sistem untuk memasang paket `ansible-core` versi 2.16. Konfigurasi operasional Ansible diatur melalui file `ansible.cfg`, yang dicari oleh Ansible berdasarkan urutan prioritas: variabel lingkungan `ANSIBLE_CONFIG`, direktori kerja saat ini (`./ansible.cfg`), direktori home pengguna (`~/.ansible.cfg`), dan terakhir file sistem default (`/etc/ansible/ansible.cfg`). Koneksi aman ke managed nodes dikelola melalui pertukaran SSH public key (`ssh-copy-id`) tanpa password untuk memastikan automasi non-interaktif. Untuk mengeksekusi perintah administratif, Ansible menggunakan mekanisme privilege escalation (`become: true`), yang dapat dikonfigurasi pada `ansible.cfg` untuk menggunakan `sudo`.

## Contoh singkat
```ini
# Contoh file ansible.cfg lokal di root proyek
[defaults]
inventory = inventory.ini
remote_user = ubuntu
host_key_checking = False

[privilege_escalation]
become = True
become_method = sudo
become_user = root
become_ask_pass = False
```

## Referensi resmi
- [Ansible Configuration settings](https://docs.ansible.com/ansible/latest/installation_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
