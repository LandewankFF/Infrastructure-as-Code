# Proyek Capstone: Baseline Linux Server Hardening & Standard Setup

## 🎯 Tujuan Proyek
Membangun role dan playbook Ansible untuk melakukan setup awal dan pengamanan standar (hardening) pada server Linux baru (Ubuntu/Debian) secara otomatis dan idempotent.

---

## 📋 Requirements & Spesifikasi
- **User Management**: Membuat user administratif khusus dengan sudo privilege (passwordless sudo), memasang SSH authorized_key pengguna, dan menonaktifkan login langsung root via SSH.
- **SSH Hardening**: Mengonfigurasi `/etc/ssh/sshd_config` agar menonaktifkan autentikasi password (`PasswordAuthentication no`), menonaktifkan X11 forwarding, dan hanya mengizinkan key-based authentication.
- **Firewall (UFW)**: Mengaktifkan firewall dengan default policy deny incoming dan allow outgoing; membuka hanya port SSH (22) dan port NTP (123 UDP).
- **Time Synchronization**: Menginstal dan memastikan service `chrony` atau `systemd-timesyncd` aktif dengan timezone terkonfigurasi ke `UTC` atau `Asia/Jakarta`.
- **Paket & Utilitas Dasar**: Memperbarui cache package manager dan menginstal perkakas esensial: `curl`, `git`, `htop`, `vim`, `ufw`, `fail2ban`, `net-tools`.

---

## 📦 Deliverables yang Harus Dibuat
- `roles/baseline/ (tasks, handlers, templates, defaults, vars, meta)`: Struktur role baseline lengkap
- `inventory.ini`: File inventory target server (multi-host)
- `site.yml`: Master playbook yang memanggil role baseline
- `README.md`: Petunjuk cara menjalankan dan memverifikasi hasil

---

## ✅ Kriteria Verifikasi (Checklist)
- [ ] Playbook lolos `ansible-lint site.yml` tanpa error
- [ ] User admin baru dapat login via SSH key dengan hak akses sudo
- [ ] Percobaan SSH menggunakan password ditolak oleh server
- [ ] Firewall UFW aktif dan hanya melewatkan port yang diizinkan
- [ ] Service NTP sinkron dan waktu server terkonfigurasi tepat
- [ ] Eksekusi kedua playbook menghasilkan `changed=0` (100% idempotent)
