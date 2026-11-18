# Validasi Keamanan File dengan Parameter validate

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Parameter `validate` pada modul `template` (dan juga `copy` / `lineinfile`) digunakan untuk memverifikasi keabsahan sintaksis file hasil render pada managed node sebelum menimpa file tujuan yang sebenarnya. Ansible menyalin file ke direktori sementara pada managed node, lalu menjalankan perintah validasi yang ditentukan dengan `%s` mewakili path file sementara tersebut; jika perintah mengembalikan exit code non-zero, operasi dibatalkan dan file asli tidak diubah. Fitur ini sangat krusial untuk mencegah insiden server down akibat kesalahan sintaks konfigurasi, seperti pada file `/etc/sudoers` (`visudo -cf %s`), file Nginx (`nginx -t -c %s`), atau file SSH daemon (`sshd -t -f %s`).

## Contoh singkat
```yaml
- name: Update konfigurasi sudoers dengan validasi aman
  ansible.builtin.template:
    src: sudoers.j2
    dest: /etc/sudoers.d/custom_admins
    validate: '/usr/sbin/visudo -cf %s'
```

## Referensi resmi
- [ansible.builtin.template module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/template_module.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
