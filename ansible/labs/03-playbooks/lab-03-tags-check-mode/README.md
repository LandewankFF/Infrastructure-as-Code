# Lab: Seleksi Eksekusi dengan Tags dan Pengujian Check Mode

## Tujuan Lab
Menyematkan tags pada berbagai task dan memverifikasi perilaku eksekusi selektif serta preview perubahan via dry-run check mode.

## Prasyarat
- Telah menyelesaikan lab playbook dasar

## Langkah-langkah Pengerjaan
1. Buka file `site.yml` dan perhatikan tag yang disematkan (`setup`, `config`, `cleanup`).
2. Jalankan playbook hanya untuk tag `config` dengan flag `--tags config`.
3. Jalankan playbook dengan melewati tag `cleanup` menggunakan flag `--skip-tags cleanup`.
4. Jalankan playbook secara menyeluruh dalam check mode dengan flag `-C` dan amati bahwa sistem tidak diubah secara nyata.

## Kriteria Berhasil (Checklist)
- [ ] Hanya task yang memiliki tag relevan yang dieksekusi saat menggunakan filter `--tags`
- [ ] Task bertag dilewati saat menggunakan `--skip-tags`
- [ ] Mode `-C` berhasil menyimulasikan eksekusi tanpa mengubah state sistem
