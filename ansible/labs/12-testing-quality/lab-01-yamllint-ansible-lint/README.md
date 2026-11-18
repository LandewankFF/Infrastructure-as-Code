# Lab: Pembersihan Kode dengan yamllint & ansible-lint

## Tujuan Lab
Mendiagnosis dan memperbaiki file playbook yang memiliki berbagai pelanggaran sintaksis, whitespace error, dan pelanggaran best practice Ansible.

## Prasyarat
- yamllint dan ansible-lint terinstal

## Langkah-langkah Pengerjaan
1. Jalankan `yamllint dirty-playbook.yml` dan amati daftar error indentasi dan trailing spaces.
2. Jalankan `ansible-lint dirty-playbook.yml` dan catat pelanggaran aturan FQCN serta penamaan task.
3. Perbaiki seluruh masalah di dalam file tersebut hingga kedua linter memberikan hasil bersih tanpa peringatan (exit code 0).

## Kriteria Berhasil (Checklist)
- [ ] File `.yamllint` terkonfigurasi dengan aturan yang sesuai
- [ ] `yamllint` mengembalikan 0 error dan 0 warning
- [ ] `ansible-lint` mengembalikan 0 violations
