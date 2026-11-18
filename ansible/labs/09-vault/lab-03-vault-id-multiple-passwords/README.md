# Lab: Multi-Password Vault Menggunakan Opsi --vault-id

## Tujuan Lab
Mengelola file rahasia dengan label dan password berbeda untuk environment dev dan production menggunakan mekanisme --vault-id.

## Prasyarat
- Paham format label@source pada vault-id

## Langkah-langkah Pengerjaan
1. Buat dua file password simulasi: `.vault_pass_dev` dan `.vault_pass_prod` (pastikan diabaikan git).
2. Enkripsi file `dev_secrets.yml` dengan `--vault-id dev@.vault_pass_dev`.
3. Enkripsi file `prod_secrets.yml` dengan `--vault-id prod@.vault_pass_prod`.
4. Jalankan playbook yang mengimpor kedua file tersebut menggunakan parameter `--vault-id` multi-sumber.

## Kriteria Berhasil (Checklist)
- [ ] Kedua file memiliki header label vault ID yang sesuai di cipher teks
- [ ] Ansible mampu membuka kedua file secara simultan dengan memetakan ID masing-masing secara otomatis
