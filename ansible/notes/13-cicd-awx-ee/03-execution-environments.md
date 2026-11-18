# Arsitektur Execution Environments (EE)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Execution Environments (EE) adalah image kontainer OCI standar (seperti Docker/Podman) yang mengemas seluruh komponen yang dibutuhkan untuk menjalankan playbook: sistem operasi dasar, versi Python tertentu, `ansible-core`, koleksi Ansible, dan library Python pihak ketiga (`requirements.txt`). Sebelum konsep EE diperkenalkan, ketidakcocokan versi Python atau pustaka sistem antar laptop developer dan server CI sering memicu error *it works on my machine*. Dengan EE, eksekusi playbook dijamin berjalan dalam lingkungan yang 100% konsisten, portabel, dan terisolasi baik saat dijalankan di terminal lokal maupun di AWX/AAP.

## Contoh singkat
```dockerfile
# Konsep dasar isi image Execution Environment (OCI container)
FROM quay.io/ansible/ansible-runner:latest
RUN pip install netaddr boto3
RUN ansible-galaxy collection install amazon.aws community.docker
```

## Referensi resmi
- [Getting started with Execution Environments](https://docs.ansible.com/ansible/latest/getting_started_ee/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
