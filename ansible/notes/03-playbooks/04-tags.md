# Penggunaan Tags untuk Seleksi Eksekusi

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Tags adalah label pengenal yang disematkan pada play, task, atau role untuk memungkinkan eksekusi selektif dari sebagian alur playbook. Saat menjalankan `ansible-playbook`, Anda dapat menyertakan `--tags <nama_tag>` untuk mengeksekusi hanya task bertag tersebut, atau `--skip-tags <nama_tag>` untuk melewatinya. Fitur ini sangat menghemat waktu ketika Anda hanya ingin memperbarui file konfigurasi tanpa harus mengulang proses download dan instalasi paket software yang lambat. Ansible juga menyediakan reserved tags khusus seperti `always` (selalu berjalan kecuali diskip secara eksplisit) dan `never` (hanya berjalan jika tag tersebut dipanggil secara eksplisit).

## Contoh singkat
```yaml
tasks:
  - name: Install Nginx
    ansible.builtin.apt:
      name: nginx
      state: present
    tags: packages

  - name: Copy index html
    ansible.builtin.copy:
      src: index.html
      dest: /var/www/html/index.html
    tags: deploy
```

## Referensi resmi
- [Tags](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_tags.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
