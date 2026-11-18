# Hubungan Playbook, Play, Task, Handler, dan Role

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Playbook adalah dokumen orkestrasi berformat YAML yang mengikat seluruh alur automasi Ansible. Di dalam satu playbook dapat terdapat satu atau beberapa Play, di mana setiap play memetakan sekelompok host target dengan sekumpulan Task yang akan dijalankan. Task adalah unit aksi terkecil dan terisolasi yang memanggil modul tertentu untuk mencapai status tertentu pada sistem target. Handler adalah jenis task khusus yang bersifat reaktif dan hanya akan dieksekusi jika task normal mengirimkan notifikasi (`notify`) akibat terjadi perubahan status (`changed`). Role adalah abstraksi tingkat lanjut yang mengemas tasks, handlers, variables, templates, dan files ke dalam struktur direktori standar agar dapat digunakan kembali (reusable) di berbagai playbook.

## Contoh singkat
```yaml
---
- name: Konfigurasi Web Server
  hosts: webservers
  tasks:
    - name: Salin file konfigurasi Nginx
      ansible.builtin.copy:
        src: nginx.conf
        dest: /etc/nginx/nginx.conf
      notify: Restart Nginx

  handlers:
    - name: Restart Nginx
      ansible.builtin.service:
        name: nginx
        state: restarted
```

## Referensi resmi
- [Playbook Guide](https://docs.ansible.com/ansible/latest/playbook_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
