# Lab: Penerapan Handlers dan Trigger Notifikasi

## Tujuan Lab
Menerapkan mekanisme handler yang hanya terpicu jika task konfigurasi menghasilkan status changed.

## Prasyarat
- Paham konsep status changed dan handler

## Langkah-langkah Pengerjaan
1. Lengkapi playbook `web-setup.yml` dengan satu task konfigurasi yang menyalin file ke `/tmp/simulated-service.conf`.
2. Tambahkan direktif `notify: Trigger Restart` pada task tersebut.
3. Buat handler bernama `Trigger Restart` yang mencetak pesan debug menggunakan modul `ansible.builtin.debug`.
4. Jalankan playbook dua kali berturut-turut dan buktikan bahwa pada eksekusi kedua handler tidak berjalan karena status task bernilai ok.

## Kriteria Berhasil (Checklist)
- [ ] Handler hanya dieksekusi pada iterasi pertama saat file mengalami perubahan
- [ ] Pada iterasi kedua, handler otomatis dilewati karena task tidak berstatus changed
- [ ] Memahami sifat dasar handler yang menunda eksekusi hingga akhir play
