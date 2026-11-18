# Tingkat Verbosity (-v s/d -vvvv) & Teknik Debugging

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Ketika playbook mengalami kendala atau berperilaku tidak sesuai ekspektasi, opsi tingkat verbosity pada CLI adalah alat diagnosis utama. Flag `-v` menampilkan detail kembalian hasil task, `-vv` menyertakan detail konfigurasi task, `-vvv` menampilkan seluruh negosiasi koneksi SSH dan perintah shell remote, dan `-vvvv` menyalakan output debug internal modul dan plugin secara mendalam. Di samping verbosity, Anda dapat menyisipkan modul `ansible.builtin.debug` untuk menginspeksi nilai variabel atau modul `ansible.builtin.assert` untuk memvalidasi prasyarat sebelum task berbahaya dijalankan. Opsi CLI `--step` dan `--start-at-task` juga sangat membantu proses isolasi masalah langkah demi langkah.

## Contoh singkat
```bash
# Debugging mendalam terhadap koneksi SSH yang bermasalah
ansible-playbook -i inventory.ini site.yml -vvv
```

## Referensi resmi
- [Tips and Tricks](https://docs.ansible.com/ansible/latest/tips_tricks/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
