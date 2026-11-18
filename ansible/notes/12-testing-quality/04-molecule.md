# Testing Framework Terisolasi dengan Molecule

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Molecule adalah framework pengujian terstandar yang dirancang khusus untuk menguji roles Ansible dalam lingkungan terisolasi menggunakan ephemeral container (Docker/Podman) atau Virtual Machine. Siklus pengujian Molecule mencakup pembuatan instance ephemeral (`molecule create`), eksekusi playbook role (`molecule converge`), pengujian idempotency (`molecule idempotence`), verifikasi fungsional sistem menggunakan testinfra/pytest (`molecule verify`), dan penghapusan environment (`molecule destroy`). Dengan Molecule, developer dapat menguji apakah role berfungsi dengan baik pada berbagai distro Linux (Ubuntu, Debian, AlmaLinux) secara lokal sebelum kode di-push ke branch utama repositori.

## Contoh singkat
```bash
# Menjalankan seluruh rangkaian skenario pengujian role secara otomatis
molecule test
```

## Referensi resmi
- [Molecule documentation](https://ansible.readthedocs.io/projects/molecule/)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
