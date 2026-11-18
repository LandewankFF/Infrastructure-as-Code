# Inisialisasi & Scaffolding Role via CLI

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Perintah `ansible-galaxy role init <nama_role>` adalah cara standar untuk membuat kerangka (scaffolding) direktori role baru yang lengkap dan terstandarisasi secara instan. Perintah ini akan menghasilkan direktori role yang memuat seluruh subdirektori resmi (`tasks/`, `handlers/`, `defaults/`, `vars/`, `templates/`, `files/`, `meta/`, dan `tests/`) beserta file `main.yml` dan `README.md` placeholder di dalamnya. Menggunakan generator resmi ini memastikan tim mematuhi konvensi struktur proyek Ansible, mempermudah navigasi kode, dan memastikan kompatibilitas penuh dengan tool analisis kualitas seperti `ansible-lint`.

## Contoh singkat
```bash
# Membuat struktur role baru di dalam direktori roles/
ansible-galaxy role init roles/web_server
```

## Referensi resmi
- [Galaxy User Guide](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
