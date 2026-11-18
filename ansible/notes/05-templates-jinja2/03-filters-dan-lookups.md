# Penggunaan Jinja2 Filters & Lookups

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Filters digunakan untuk mentransformasi dan memodifikasi data variabel secara inline menggunakan karakter pipa (`|`), seperti memformat JSON (`to_nice_json`), menentukan nilai default (`default`), atau memanipulasi string dan list. Sementara itu, Lookups adalah plugin Ansible yang memungkinkan penarikan data dari sumber eksternal di luar variabel standar langsung di dalam template atau playbook. Lookup dijalankan pada Control Node dan dapat membaca file lokal (`lookup('file', 'id_rsa.pub')`), variabel environment (`lookup('env', 'HOME')`), atau query DNS. Kombinasi filters dan lookups memberikan fleksibilitas luar biasa dalam menyusun konfigurasi yang kompleks secara dinamis.

## Contoh singkat
```yaml
- name: Membaca SSH key dari control node menggunakan lookup
  ansible.builtin.authorized_key:
    user: deployer
    key: "{{ lookup('ansible.builtin.file', '~/.ssh/id_rsa.pub') }}"
```

## Referensi resmi
- [Jinja2 Filters](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_filters.html)
- [Lookups](https://docs.ansible.com/ansible/latest/plugins/lookup.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
