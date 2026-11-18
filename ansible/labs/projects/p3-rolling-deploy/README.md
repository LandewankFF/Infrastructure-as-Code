# Proyek Capstone: Zero-Downtime Rolling Deployment dengan Resilient Rollback

## 🎯 Tujuan Proyek
Menerapkan strategi update aplikasi bergilir (rolling update) pada sekumpulan server web di balik load balancer dengan kontrol batching, pemeriksaan health-check otomatis, dan rollback terstruktur menggunakan block/rescue.

---

## 📋 Requirements & Spesifikasi
- **Batching Eksekusi**: Menggunakan parameter `serial: 1` atau persentase (misal `serial: 50%`) agar update dilakukan bertahap tanpa mematikan seluruh kluster.
- **Siklus Traffic Draining**: Mengeluarkan host yang sedang diproses dari routing load balancer sebelum proses update dimulai (bisa disimulasikan via state file maintenance atau modul load balancer).
- **Deployment Aplikasi**: Memperbarui source code aplikasi web, mengekstrak artefak rilis baru, dan me-restart service aplikasi.
- **Health Check Otomatis**: Menggunakan modul `ansible.builtin.uri` untuk memverifikasi bahwa endpoint internal `/health` atau `index.html` merespon HTTP 200 dalam batas waktu tertentu.
- **Mekanisme Rollback**: Mengelompokkan langkah deploy ke dalam `block:`; jika health check gagal, bagian `rescue:` harus secara otomatis memulihkan versi kode sebelumnya dan melaporkan status insiden.
- **Traffic Re-enabling**: Di bagian `always:`, pastikan server dimasukkan kembali ke routing pool dan mencatat log final.

---

## 📦 Deliverables yang Harus Dibuat
- `rolling-deploy.yml`: Master playbook rolling update
- `inventory.ini`: Definisi minimal 2 sampai 3 web nodes di dalam grup `webservers`
- `mock-service/`: File aplikasi sederhana atau endpoint health check simulasi
- `README.md`: Panduan pengujian termasuk cara memicu simulasi kegagalan untuk menguji alur rescue/rollback

---

## ✅ Kriteria Verifikasi (Checklist)
- [ ] Server web diproses secara bertahap satu per satu sesuai kuota serial
- [ ] Health check HTTP memvalidasi ketersediaan endpoint sebelum melanjutkan ke host berikutnya
- [ ] Skenario kegagalan sengaja berhasil memicu blok rescue dan mengembalikan sistem ke versi stabil
- [ ] Ketersediaan layanan web secara keseluruhan tetap terjaga selama proses update berlangsung
