# Lab: Membangun GitHub Actions Workflow untuk Linter Ansible

## Tujuan Lab
Menyusun file definisi workflow CI GitHub Actions (.github/workflows) yang secara otomatis memvalidasi syntax check dan ansible-lint pada setiap pull request.

## Prasyarat
- Paham sintaks workflow GitHub Actions

## Langkah-langkah Pengerjaan
1. Pelajari file referensi template `workflow-example.yml`.
2. Konfigurasikan tahapan checkout kode, setup Python, instalasi ansible-lint, dan eksekusi linting otomatis.
3. Simulasikan skenario kegagalan pipeline jika kode yang di-push memiliki syntax error.

## Kriteria Berhasil (Checklist)
- [ ] Workflow YAML valid secara sintaks GitHub Actions
- [ ] Pipeline memuat langkah-langkah audit kualitas yang lengkap dan terstruktur
