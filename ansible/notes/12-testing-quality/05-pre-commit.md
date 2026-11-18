# Quality Gate Otomatis dengan pre-commit Hooks

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Framework `pre-commit` digunakan untuk mengotomatisasi pemeriksaan kualitas kode pada saat developer menjalankan perintah `git commit` di terminal lokal. Dengan mendefinisikan file konfigurasi `.pre-commit-config.yaml`, hook git dapat dikonfigurasi untuk secara otomatis memicu `yamllint`, `ansible-lint`, penghapusan trailing whitespaces, dan pemeriksaan format file sebelum commit diizinkan masuk ke riwayat Git. Mekanisme ini mencegah kode yang cacat atau melanggar aturan standar masuk ke repositori, mengurangi beban revisi pada review pull request, dan menjaga kebersihan basis kode secara konsisten di seluruh anggota tim engineering.

## Contoh singkat
```yaml
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/ansible/ansible-lint
    rev: v6.22.2
    hooks:
      - id: ansible-lint
```

## Referensi resmi
- [pre-commit framework](https://pre-commit.com/)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
