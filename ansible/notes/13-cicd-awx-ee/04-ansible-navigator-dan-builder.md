# Tooling Modern: ansible-navigator & ansible-builder

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Untuk mendukung ekosistem Execution Environments secara penuh, Ansible menyediakan dua tooling modern: `ansible-builder` dan `ansible-navigator`. `ansible-builder` membaca file definisi deklaratif `execution-environment.yml` yang merinci dependensi sistem, paket Python, dan collections, lalu secara otomatis mengompilasinya menjadi image kontainer OCI. Sementara itu, `ansible-navigator` adalah antarmuka terminal interaktif (TUI) modern yang menggantikan peran `ansible-playbook` tradisional, memungkinkan eksekusi dan penelusuran hasil playbook langsung di dalam kontainer Execution Environment secara visual.

## Contoh singkat
```bash
# Menjalankan playbook di dalam Execution Environment menggunakan ansible-navigator
ansible-navigator run site.yml --ee true --mode stdout
```

## Referensi resmi
- [ansible-navigator documentation](https://ansible.readthedocs.io/projects/navigator/)
- [ansible-builder documentation](https://ansible.readthedocs.io/projects/builder/)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
