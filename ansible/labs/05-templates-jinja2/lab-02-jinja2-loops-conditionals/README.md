# Lab: Logika Percabangan & Perulangan di Template Jinja2

## Tujuan Lab
Menerapkan loop for dan percabangan if/else di dalam file template konfigurasi virtual host web server.

## Prasyarat
- Paham sintaks {% for %} dan {% if %}

## Langkah-langkah Pengerjaan
1. Buka `templates/vhost.conf.j2` dan lengkapi blok iterasi daftar domain yang berasal dari variabel list.
2. Tambahkan kondisi `{% if enable_ssl %}` untuk menyertakan blok konfigurasi SSL port 443.
3. Jalankan playbook `render-vhost.yml` dan periksa hasil output file yang terbentuk.

## Kriteria Berhasil (Checklist)
- [ ] Seluruh elemen list domain berhasil dirender menjadi baris konfigurasi terpisah
- [ ] Blok SSL hanya muncul jika variabel `enable_ssl` disetel bernilai `true`
