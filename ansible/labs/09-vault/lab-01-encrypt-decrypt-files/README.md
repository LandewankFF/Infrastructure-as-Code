# Lab: Manajemen Enkripsi File Penuh dengan ansible-vault

## Tujuan Lab
Melakukan operasi dasar Ansible Vault: mengenkripsi file rahasia, melihat isinya tanpa dekripsi, dan mengedit langsung di editor.

## Prasyarat
- ansible-vault CLI tersedia

## Langkah-langkah Pengerjaan
1. Periksa file `secrets.yml` yang masih berupa plaintext.
2. Enkripsi file tersebut menggunakan `ansible-vault encrypt secrets.yml`.
3. Gunakan `ansible-vault view secrets.yml` untuk melihat isinya.
4. Gunakan `ansible-vault edit secrets.yml` untuk menambahkan variabel baru.
5. Dekripsi file kembali menjadi plaintext menggunakan `ansible-vault decrypt secrets.yml`.

## Kriteria Berhasil (Checklist)
- [ ] File berhasil dienkripsi menjadi format $ANSIBLE_VAULT;1.1;AES256
- [ ] Mampu melihat dan mengedit konten tanpa mengekspos plaintext di disk secara permanen
- [ ] Memahami siklus hidup enkripsi dan dekripsi file penuh
