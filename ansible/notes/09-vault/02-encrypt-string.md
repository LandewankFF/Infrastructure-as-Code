# Enkripsi String Individual dengan encrypt_string

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Alih-alih mengenkripsi keseluruhan file, `ansible-vault encrypt_string` memungkinkan enkripsi hanya pada nilai variabel sensitif individual secara inline di dalam file YAML yang tetap plaintext. Hal ini sangat menguntungkan saat bekerja dengan version control (Git), karena nama variabel dan struktur file tetap dapat dibaca serta dilakukan git-diff dengan jelas, sementara nilainya terproteksi dalam format ciphertext berawalan `!vault |`. Sintaks CLI-nya menerima string plaintext dan menghasilkan blok YAML terenkripsi yang siap ditempelkan langsung ke file `group_vars` atau playbook. Saat playbook dijalankan, Ansible akan mendekripsi blok string tersebut secara otomatis jika password vault yang tepat disertakan.

## Contoh singkat
```bash
# Menghasilkan variabel YAML terenkripsi untuk ditempel ke playbook
ansible-vault encrypt_string 'MySuperSecretP@ssw0rd' --name 'db_password'
```

## Referensi resmi
- [Encrypting individual variables with Ansible Vault](https://docs.ansible.com/ansible/latest/vault_guide/vault_encrypting_content.html#encrypting-individual-variables-with-ansible-vault)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
