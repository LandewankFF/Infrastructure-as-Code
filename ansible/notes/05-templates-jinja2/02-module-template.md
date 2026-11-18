# Modul ansible.builtin.template

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Modul `ansible.builtin.template` digunakan untuk merender file template berakhiran `.j2` dari Control Node dan mengirimkan hasil renderingnya sebagai file teks ke Managed Node. Berbeda dengan modul `copy` yang memindahkan file secara mentah tanpa modifikasi, `template` akan memproses seluruh variabel, filter, dan logika di dalam file template terlebih dahulu. Modul ini mendukung pengaturan hak akses berkas (`mode`), kepemilikan (`owner`, `group`), backup file lama (`backup: true`), dan verifikasi sintaks via `validate`. `ansible.builtin.template` adalah standar industri untuk mengelola file konfigurasi service seperti Nginx, Apache, PostgreSQL, dan systemd unit files.

## Contoh singkat
```yaml
- name: Deploy file konfigurasi Nginx dari template Jinja2
  ansible.builtin.template:
    src: nginx.conf.j2
    dest: /etc/nginx/nginx.conf
    owner: root
    group: root
    mode: '0644'
```

## Referensi resmi
- [ansible.builtin.template module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/template_module.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
