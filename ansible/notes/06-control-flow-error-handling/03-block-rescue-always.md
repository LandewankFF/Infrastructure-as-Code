# Struktur Penanganan Error: block, rescue, always

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
`block` memungkinkan pengelompokan beberapa task secara logis sekaligus menyediakan mekanisme penanganan eksepsi yang mirip dengan konstruksi `try/catch/finally` dalam bahasa pemrograman modern. Bagian `block` memuat sekumpulan task utama yang ingin dijalankan secara normal. Jika ada satu task di dalam `block` yang gagal (`failed`), eksekusi langsung dialihkan ke bagian `rescue` untuk menjalankan langkah-langkah perbaikan atau rollback konfigurasi. Bagian `always` akan selalu dieksekusi terlepas dari apakah blok utama berhasil maupun gagal, sangat ideal untuk pekerjaan bersih-bersih (cleanup) seperti menghapus file temporary atau menyalakan service kembali.

## Contoh singkat
```yaml
- name: Transaksi Deployment Aplikasi
  block:
    - name: Download versi terbaru
      ansible.builtin.get_url:
        url: https://example.com/app.tar.gz
        dest: /tmp/app.tar.gz
  rescue:
    - name: Rollback ke versi cadangan
      ansible.builtin.debug:
        msg: "Download gagal, mengembalikan versi sebelumnya..."
  always:
    - name: Hapus temporary files
      ansible.builtin.file:
        path: /tmp/app.tar.gz
        state: absent
```

## Referensi resmi
- [Blocks](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_blocks.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
