# Lab: Pola Transaksi Resilient dengan block, rescue, dan always

## Tujuan Lab
Membangun mekanisme penanganan error terstruktur di mana kegagalan di dalam block memicu langkah perbaikan di rescue dan pembersihan di always.

## Prasyarat
- Paham alur kerja exception handling di Ansible

## Langkah-langkah Pengerjaan
1. Buka `resilient-play.yml` dan buat task sengaja gagal di dalam blok `block:` menggunakan modul `command: /bin/false`.
2. Di dalam bagian `rescue:`, buat task pemulihan/rollback.
3. Di dalam bagian `always:`, buat task yang mencetak log selesai terlepas dari status eksekusi.
4. Jalankan playbook dan amati bahwa playbook selesai dengan sukses secara keseluruhan karena error berhasil ditangani oleh rescue.

## Kriteria Berhasil (Checklist)
- [ ] Kegagalan di block secara otomatis dialihkan ke bagian rescue
- [ ] Bagian always tetap dieksekusi dengan pasti
- [ ] Playbook tidak crash/abort berkat penanganan error yang tepat
