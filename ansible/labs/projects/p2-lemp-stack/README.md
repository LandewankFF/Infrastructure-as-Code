# Proyek Capstone: LEMP Stack Modular Deployment (Nginx + MySQL + PHP-FPM)

## 🎯 Tujuan Proyek
Merancang arsitektur deployment modular berbasis multi-role untuk memasang web server LEMP stack lengkap, memanfaatkan template Jinja2 dinamis untuk virtual host, serta mengamankan kredensial database menggunakan Ansible Vault.

---

## 📋 Requirements & Spesifikasi
- **Struktur Multi-Role**: Memisahkan konfigurasi ke dalam 4 role mandiri: `common`, `nginx`, `php`, dan `mysql`.
- **Role Nginx**: Memasang Nginx, mengelola file konfigurasi virtual host via template Jinja2 (`vhost.conf.j2`) dengan parameter domain, root directory, dan PHP-FPM upstream handler; menyertakan handler reload Nginx.
- **Role PHP**: Memasang PHP-FPM beserta ekstensi umum (`php-mysql`, `php-curl`, `php-mbstring`, `php-xml`); memastikan service PHP-FPM aktif dan mendengarkan pada unix socket lokal.
- **Role MySQL/MariaDB**: Memasang server database, mengamankan instalasi (remove anonymous users, test db), membuat database aplikasi, dan membuat user database dengan hak akses terbatas.
- **Keamanan Rahasia**: Password root MySQL dan password user aplikasi wajib dienkripsi menggunakan Ansible Vault (baik file vault maupun encrypt_string).
- **Sample Web App**: Menyajikan file `index.php` yang menampilkan konektivitas sukses ke database MySQL.

---

## 📦 Deliverables yang Harus Dibuat
- `roles/nginx/`: Role konfigurasi web server dan virtual host
- `roles/php/`: Role konfigurasi runtime PHP-FPM
- `roles/mysql/`: Role instalasi dan provisioning database
- `vars/vault.yml`: File variabel terenkripsi Ansible Vault
- `site.yml`: Master playbook orkestrasi LEMP stack
- `inventory.ini`: Inventory web & database host

---

## ✅ Kriteria Verifikasi (Checklist)
- [ ] Playbook berjalan sukses dari awal hingga akhir tanpa intervensi manual
- [ ] Nginx berhasil menyajikan halaman PHP melalui soket PHP-FPM
- [ ] Script index.php berhasil terhubung dan meng-query database MySQL
- [ ] Seluruh kredensial rahasia tersimpan dalam format terenkripsi Ansible Vault
- [ ] Handler reload/restart hanya terpicu saat file template konfigurasi mengalami perubahan
