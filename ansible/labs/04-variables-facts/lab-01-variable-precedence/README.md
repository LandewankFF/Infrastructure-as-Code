# Lab: Eksperimen Tingkat Prioritas Variabel (Precedence)

## Tujuan Lab
Membuktikan hierarki prioritas variabel antara vars_files, play vars, inventory vars, dan extra vars (-e).

## Prasyarat
- Paham daftar urutan prioritas variabel Ansible

## Langkah-langkah Pengerjaan
1. Periksa variabel `app_port` yang didefinisikan di `inventory.ini` (8000), `vars.yml` (8080), dan di dalam play (9000).
2. Jalankan playbook `test-vars.yml` dan catat nilai `app_port` mana yang menang.
3. Jalankan kembali playbook dengan menyertakan extra vars `-e "app_port=7000"` dan verifikasi bahwa extra vars mengalahkan seluruh definisi lainnya.

## Kriteria Berhasil (Checklist)
- [ ] Berhasil membuktikan bahwa play vars / vars_files mengalahkan nilai dari inventory
- [ ] Berhasil membuktikan bahwa opsi `-e` memiliki prioritas absolut tertinggi
