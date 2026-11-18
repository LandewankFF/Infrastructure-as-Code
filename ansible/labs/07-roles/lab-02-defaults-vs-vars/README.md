# Lab: Eksperimen Scoping: defaults/main.yml vs vars/main.yml

## Tujuan Lab
Membuktikan perbedaan prioritas variabel antara defaults (dapat di-override) dan vars (konstan) di dalam role.

## Prasyarat
- Telah memahami struktur role dasar

## Langkah-langkah Pengerjaan
1. Buat role sederhana `config_tester` di dalam folder `roles/`.
2. Definisikan variabel `port: 80` di `defaults/main.yml` dan variabel `internal_token: 'secret'` di `vars/main.yml`.
3. Di dalam `site.yml`, coba timpa kedua variabel tersebut melalui parameter `vars:` pada pemanggilan role.
4. Buktikan bahwa variabel `port` berhasil diubah sementara `internal_token` tetap mempertahankan nilai aslinya.

## Kriteria Berhasil (Checklist)
- [ ] Variabel di `defaults/` berhasil di-override dari level playbook
- [ ] Variabel di `vars/` memenangkan prioritas dan menolak override biasa
- [ ] Memahami prinsip penempatan konfigurasi pengguna di dalam role
