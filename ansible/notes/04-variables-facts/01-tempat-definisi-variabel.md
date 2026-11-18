# Lokasi & Tempat Mendefinisikan Variabel

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Variabel dalam Ansible berfungsi untuk memisahkan konfigurasi dinamis dari logika playbook agar kode automasi tetap generik dan reusable. Variabel dapat didefinisikan di berbagai tempat, antara lain di dalam file inventory, direktori `group_vars/` dan `host_vars/`, blok `vars` pada play, file terpisah via `vars_files`, serta di dalam role (`defaults/` dan `vars/`). Pemilihan lokasi definisi harus mempertimbangkan cakupan (scope): apakah variabel bersifat global untuk semua host, spesifik untuk grup tertentu, spesifik untuk satu host, atau hanya dibutuhkan di dalam satu play lokal. Memisahkan variabel konfigurasi dari alur eksekusi task adalah prinsip inti best practice Ansible.

## Contoh singkat
```yaml
- name: Contoh deklarasi variabel pada Play
  hosts: all
  vars:
    app_port: 8080
    app_user: "apprunner"
  vars_files:
    - "vars/environment.yml"
```

## Referensi resmi
- [Variables Guide](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_variables.html)
- [Special Variables (Magic Vars)](https://docs.ansible.com/ansible/latest/reference_appendices/special_variables.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
