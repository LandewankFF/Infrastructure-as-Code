# Proteksi Kebocoran Log Output dengan no_log

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Meskipun data sensitif telah dienkripsi menggunakan Ansible Vault, nilai plaintext dari variabel tersebut berisiko terekspos ke layar terminal, file log CI/CD, atau monitoring system saat task dieksekusi. Direktif `no_log: true` disematkan pada level task atau play untuk menginstruksikan Ansible agar tidak mencetak parameter modul, argumen pemanggilan, dan output respon ke dalam log sistem. Fitur ini wajib digunakan saat menangani task pembuatan user baru dengan password, registrasi token API, atau transfer private key. Namun, saat proses debugging awal, `no_log: true` dapat menyembunyikan detail penyebab error, sehingga disarankan untuk menonaktifkannya sementara waktu hanya di lingkungan pengujian lokal yang aman.

## Contoh singkat
```yaml
- name: Set password database dengan proteksi log aman
  ansible.builtin.user:
    name: db_admin
    password: "{{ vault_db_password | password_hash('sha512') }}"
  no_log: true
```

## Referensi resmi
- [Protecting sensitive data with no_log](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_error_handling.html#protecting-sensitive-data-with-no-log)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
