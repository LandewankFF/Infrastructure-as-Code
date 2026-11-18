# Struktur Dasar Playbook dan Plays

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Playbook terdiri dari satu atau lebih play yang dieksekusi secara berurutan dari atas ke bawah. Setiap play memiliki header yang mendefinisikan target host (`hosts`), nama deskriptif (`name`), hak akses (`become`), variabel play (`vars`), serta daftar pekerjaan (`tasks`). Task di dalam play dieksekusi satu per satu pada seluruh host target sebelum Ansible melanjutkan ke task berikutnya (secara default synchronous lock-step). Pemisahan play di dalam satu playbook berguna saat Anda perlu mengonfigurasi host yang berbeda dengan peran yang berbeda dalam satu alur orkestrasi (misal play 1 untuk database, play 2 untuk web server).

## Contoh singkat
```yaml
---
- name: Play 1 - Setup Database
  hosts: databases
  become: true
  tasks:
    - name: Ping DB
      ansible.builtin.ping:

- name: Play 2 - Setup Web App
  hosts: webservers
  tasks:
    - name: Ping Web
      ansible.builtin.ping:
```

## Referensi resmi
- [Playbook Guide](https://docs.ansible.com/ansible/latest/playbook_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
