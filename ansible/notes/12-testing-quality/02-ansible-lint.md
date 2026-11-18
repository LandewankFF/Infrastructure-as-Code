# Analisis Best Practices dengan ansible-lint

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
`ansible-lint` adalah linter resmi dan paling penting dalam ekosistem Ansible yang melakukan analisis statik pada playbook, roles, dan collections. Tool ini tidak hanya memeriksa sintaksis YAML, melainkan mengaudit kepatuhan kode terhadap best practice industri, standar keamanan, dan konvensi penamaan modern (seperti kewajiban menggunakan FQCN, larangan menggunakan modul `command` jika modul builtin tersedia, penamaan setiap task, dan proteksi rahasia). Setiap aturan diberi kode unik (misal `fqcn-builtins`, `name[missing]`), dan kegagalan linting dapat diintegrasikan sebagai quality gate dalam pipeline CI/CD. Konfigurasi aturan dapat dikontrol melalui file `.ansible-lint`.

## Contoh singkat
```bash
# Menjalankan audit kepatuhan best practices pada seluruh direktori
ansible-lint
```

## Referensi resmi
- [ansible-lint documentation](https://ansible.readthedocs.io/projects/lint/)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
