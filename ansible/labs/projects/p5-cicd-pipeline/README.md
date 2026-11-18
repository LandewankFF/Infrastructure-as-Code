# Proyek Capstone: End-to-End GitOps CI/CD Automation Pipeline

## 🎯 Tujuan Proyek
Membangun pipeline automasi pengujian berkelanjutan (CI) dan deployment (CD) lengkap untuk repositori Ansible menggunakan GitHub Actions atau GitLab CI, menerapkan quality gate bertingkat dari linting hingga multi-environment deploy.

---

## 📋 Requirements & Spesifikasi
- **Stage 1 - Quality Gate (Linting)**: Memvalidasi format YAML dengan `yamllint`, memeriksa best practices Ansible dengan `ansible-lint`, dan memverifikasi integritas playbook dengan `ansible-playbook --syntax-check`.
- **Stage 2 - Automated Testing**: Menjalankan skenario pengujian role secara otomatis menggunakan Molecule di dalam container ephemeral; menguji eksekusi playbook dan verifikasi idempotency.
- **Stage 3 - Deploy Staging**: Memicu otomatisasi deployment ke lingkungan staging saat pull request di-merge ke branch `main`.
- **Stage 4 - Production Approval Gate**: Menyediakan tombol manual trigger (approval gate) di UI CI/CD untuk deployment ke server produksi setelah tim QA memverifikasi lingkungan staging.
- **Secrets Management**: Menangani credential koneksi SSH, token API, dan password Ansible Vault menggunakan native Secrets platform CI/CD (GitHub Secrets / GitLab CI Variables) tanpa pernah mengeksposnya ke log publik.

---

## 📦 Deliverables yang Harus Dibuat
- `.github/workflows/ci-cd.yml`: Definisi pipeline CI/CD lengkap (atau `.gitlab-ci.yml`)
- `.yamllint & .ansible-lint`: File konfigurasi rules linter repositori
- `inventories/staging/ & inventories/production/`: Pemisahan direktori multi-environment inventory
- `playbooks/site.yml`: Master deployment playbook
- `README.md`: Dokumentasi arsitektur pipeline, diagram alur rilis, dan panduan konfigurasi secrets

---

## ✅ Kriteria Verifikasi (Checklist)
- [ ] Pipeline CI otomatis berjalan saat ada pull request atau commit baru
- [ ] Tahap linting berhasil mendeteksi dan menolak kode yang melanggar aturan
- [ ] Tahap testing memvalidasi role secara terisolasi sebelum deployment
- [ ] Deployment staging berjalan otomatis dan aman
- [ ] Deployment production terlindungi oleh approval gate dan berjalan sukses
