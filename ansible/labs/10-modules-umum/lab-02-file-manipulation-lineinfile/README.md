# Lab: Manipulasi File dengan copy, lineinfile, dan blockinfile

## Tujuan Lab
Melakukan manipulasi berkas teks: menyalin file statis, memodifikasi baris konfigurasi tertentu via regex, dan menyisipkan blok parameter.

## Prasyarat
- Paham penggunaan ekspresi reguler (regex) sederhana

## Langkah-langkah Pengerjaan
1. Buat file konfigurasi pengujian di `/tmp/lab-config.conf`.
2. Gunakan modul `ansible.builtin.lineinfile` untuk mengubah parameter konfigurasi tertentu.
3. Gunakan modul `ansible.builtin.blockinfile` untuk menyisipkan blok pengaturan bertanda marker khusus.
4. Verifikasi idempotensi bahwa eksekusi ulang tidak menduplikasi baris/blok teks.

## Kriteria Berhasil (Checklist)
- [ ] Baris konfigurasi berhasil diperbarui secara presisi berdasarkan pencocokan regex
- [ ] Blok konfigurasi tersisip dengan marker Ansible yang jelas
- [ ] Eksekusi berulang tidak menambahkan duplikasi baris baru
