# Lab: Refactoring Playbook ke Standar FQCN Penuh

## Tujuan Lab
Mengubah penulisan modul lama (legacy short names) menjadi penulisan kanonikal Fully Qualified Collection Name.

## Prasyarat
- Paham namespace ansible.builtin dan community

## Langkah-langkah Pengerjaan
1. Buka file `fqcn-playbook.yml` yang masih menggunakan short names (misal `copy`, `ping`, `debug`).
2. Lakukan refactoring dengan menambahkan prefix FQCN yang tepat (`ansible.builtin.*`).
3. Jalankan playbook untuk memastikan tidak ada kesalahan pemanggilan plugin.

## Kriteria Berhasil (Checklist)
- [ ] Seluruh task telah menggunakan format FQCN secara konsisten
- [ ] Playbook berjalan sukses tanpa peringatan penamaan modul
