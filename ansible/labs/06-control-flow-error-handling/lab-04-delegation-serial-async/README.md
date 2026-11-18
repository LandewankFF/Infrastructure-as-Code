# Lab: Orkestrasi Lanjutan: delegate_to, serial, dan async

## Tujuan Lab
Menerapkan pembatasan konkurensi batching dengan serial dan mendelegasikan eksekusi task spesifik ke control node lokal.

## Prasyarat
- Paham konsep rolling update dasar

## Langkah-langkah Pengerjaan
1. Periksa host di `inventory.ini` yang memuat 3 host simulasi lokal.
2. Setel parameter `serial: 1` pada play di `batch-run.yml`.
3. Di dalam play, gunakan `delegate_to: localhost` pada salah satu task pencatatan log.
4. Jalankan playbook dan amati bagaimana host diproses satu demi satu secara bergantian.

## Kriteria Berhasil (Checklist)
- [ ] Playbook mengeksekusi host dalam batch sesuai nilai parameter `serial`
- [ ] Task delegasi sukses dijalankan di localhost
