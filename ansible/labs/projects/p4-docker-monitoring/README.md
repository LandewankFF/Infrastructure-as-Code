# Proyek Capstone: Dockerized Host Setup & Full Monitoring Stack Deployment

## 🎯 Tujuan Proyek
Mengotomatisasi konfigurasi host Docker dari nol dan mendistribusikan stack monitoring lengkap (Prometheus, Node Exporter, Grafana) menggunakan Ansible dan koleksi community.docker.

---

## 📋 Requirements & Spesifikasi
- **Docker Engine Provisioning**: Menginstal Docker CE, containerd, dan Docker Compose plugin resmi; menambahkan user non-root ke grup `docker`.
- **Daemon Configuration**: Menyediakan file konfigurasi daemon `/etc/docker/daemon.json` via template Jinja2 untuk mengatur log driver (`json-file` dengan `max-size` dan `max-file`), default bridge, dan metrics endpoint.
- **Containerized Node Exporter**: Mendeploy container `prom/node-exporter` dengan mounting direktori sistem host (`/proc`, `/sys`) secara read-only untuk metrik hardware.
- **Containerized Prometheus**: Menyiapkan direktori konfigurasi dan template `prometheus.yml.j2` yang menargetkan scraping ke Node Exporter lokal; mendeploy container `prom/prometheus` dengan named volume untuk data retention.
- **Containerized Grafana**: Mendeploy container `grafana/grafana` dengan port forwarding 3000, environment variables password admin via Vault, dan provisioning otomatis data source Prometheus.
- **Idempotency & Lifecycle**: Seluruh container dikelola dengan modul `community.docker.docker_container` dengan `restart_policy: unless-stopped`.

---

## 📦 Deliverables yang Harus Dibuat
- `roles/docker_host/`: Role instalasi dan konfigurasi Docker Engine
- `roles/monitoring_stack/`: Role manajemen container Prometheus, Node Exporter, dan Grafana
- `templates/prometheus.yml.j2`: Template dinamis konfigurasi scrape target
- `site.yml`: Playbook master orkestrasi monitoring host
- `inventory.ini`: Target server host

---

## ✅ Kriteria Verifikasi (Checklist)
- [ ] Docker Engine terpasang dan service docker berjalan normal
- [ ] Seluruh container (node-exporter, prometheus, grafana) berstatus running
- [ ] Dashboard Prometheus dapat melihat target Node Exporter berstatus `UP`
- [ ] Grafana dapat diakses di port 3000 dan telah terhubung ke datasource Prometheus
- [ ] Data metrik tetap persisten meskipun container di-restart atau di-recreate
