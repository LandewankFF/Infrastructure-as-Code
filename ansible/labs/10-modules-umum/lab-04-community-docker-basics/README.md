# Lab: Otomasi Lifecycle Docker Container (community.docker)

## Tujuan Lab
Menggunakan modul community.docker.docker_container untuk mem-pull image dan menjalankan container terisolasi secara deklaratif.

## Prasyarat
- Docker Engine terpasang dan service docker aktif (atau simulasi konfigurasi)

## Langkah-langkah Pengerjaan
1. Pastikan modul `community.docker` tersedia di sistem.
2. Lengkapi `docker-app.yml` untuk menjalankan container Nginx dengan nama `web-sandbox`.
3. Petakan port 8080 host ke port 80 container dan atur `restart_policy: unless-stopped`.
4. Uji idempotensi dengan menjalankan ulang playbook.

## Kriteria Berhasil (Checklist)
- [ ] Playbook mendefinisikan container Docker dengan parameter yang lengkap
- [ ] Container berjalan sesuai spesifikasi port dan restart policy
- [ ] Eksekusi ulang menghasilkan status `ok` (idempotent)
