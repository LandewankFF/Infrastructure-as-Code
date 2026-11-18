# Operasi Enkripsi File: encrypt, decrypt, edit, view

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Ansible Vault menyediakan enkripsi simetris berbasis algoritma AES-256 untuk melindungi file sensitif yang disimpan dalam repositori Git. Perintah `ansible-vault encrypt <file>` mengubah seluruh isi file teks menjadi ciphertext terenkripsi, sedangkan `ansible-vault decrypt <file>` mengembalikannya menjadi plaintext murni. Untuk melakukan perubahan konfigurasi rahasia tanpa harus mendekripsi file secara permanen ke disk, Anda dapat menggunakan `ansible-vault edit <file>` yang akan membuka file di editor teks dan mengenkripsinya kembali secara otomatis saat disimpan. Perintah `ansible-vault view <file>` membaca dan menampilkan isi file terenkripsi langsung ke terminal tanpa mengubah file pada storage.

## Contoh singkat
```bash
# Mengenkripsi file rahasia dan membukanya untuk dilihat
ansible-vault encrypt vars/db_secrets.yml
ansible-vault view vars/db_secrets.yml
```

## Referensi resmi
- [Ansible Vault Guide](https://docs.ansible.com/ansible/latest/vault_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
