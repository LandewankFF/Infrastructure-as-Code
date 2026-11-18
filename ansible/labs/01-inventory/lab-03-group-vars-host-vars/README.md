# Lab: Mengorganisasi Variabel dengan group_vars dan host_vars

## Tujuan Lab
Memisahkan variabel dari file inventory ke dalam struktur folder terpisah: group_vars/ dan host_vars/.

## Prasyarat
- Telah memahami konsep scoping variabel

## Langkah-langkah Pengerjaan
1. Periksa struktur folder `group_vars/` dan `host_vars/` yang telah disediakan.
2. Definisikan variabel global di `group_vars/all.yml` (misal `ntp_server: pool.ntp.org`).
3. Definisikan variabel grup di `group_vars/webservers.yml` (misal `http_port: 8080`).
4. Definisikan variabel spesifik di `host_vars/web1.example.com.yml` (misal `custom_motd: 'Server 1'`).
5. Jalankan playbook `test.yml` untuk memverifikasi nilai variabel yang berhasil dimuat.

## Kriteria Berhasil (Checklist)
- [ ] Ansible otomatis memuat variabel dari direktori group_vars dan host_vars tanpa deklarasi manual
- [ ] Host `web1.example.com` memiliki akses ke variabel global, variabel grup, dan variabel dirinya sendiri
- [ ] Playbook test.yml berhasil mencetak ketiga variabel dengan benar
