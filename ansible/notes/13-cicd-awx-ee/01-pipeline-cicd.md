# Pipeline CI/CD (GitHub Actions & GitLab CI)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Mengintegrasikan Ansible ke dalam pipeline CI/CD memungkinkan penerapan praktik GitOps di mana setiap perubahan konfigurasi infrastruktur diuji dan diterapkan secara otomatis melalui alur kerja Git. Tahap (stages) standar dalam pipeline Ansible mencakup: Linting (`yamllint` dan `ansible-lint`), Syntax Validation (`ansible-playbook --syntax-check`), Testing isolasi dengan Molecule, dan Deployment bertingkat (otomatis ke staging saat pull request di-merge, dan manual approval gate sebelum masuk ke production). Credential rahasia seperti password vault atau private key SSH disimpan dengan aman di Secrets Provider milik CI/CD platform.

## Contoh singkat
```yaml
# Contoh job GitHub Actions untuk linting Ansible
name: Ansible Lint
on: [push, pull_request]
jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run Ansible Lint
        uses: ansible/ansible-lint@main
```

## Referensi resmi
- [Ansible in CI/CD](https://docs.ansible.com/ansible/latest/reference_appendices/test_strategies.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
