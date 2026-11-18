# Eksekusi Asynchronous: async & poll

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Secara default, Ansible menjalankan task secara synchronous di mana connection tetap terbuka menunggu proses selesai sebelum lanjut ke task berikutnya. Untuk operasi yang memakan waktu lama (seperti backup database berukuran besar atau compile kernel), keyword `async` menentukan batas waktu maksimal (timeout dalam detik) proses diizinkan berjalan di background pada managed node. Nilai `poll` menentukan interval polling Ansible untuk mengecek status proses tersebut; jika `poll: 0`, Ansible akan langsung melanjutkan ke task berikutnya (*fire-and-forget*). Status pekerjaan asynchronous yang berjalan di background dapat dicek di task selanjutnya menggunakan modul `ansible.builtin.async_status`.

## Contoh singkat
```yaml
- name: Menjalankan backup database lama secara asynchronous
  ansible.builtin.command: /opt/scripts/full_backup.sh
  async: 3600
  poll: 0
  register: backup_job
```

## Referensi resmi
- [Asynchronous actions and polling](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_async.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
