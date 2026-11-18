# Mekanisme Handlers dan Notifikasi (notify)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Handler adalah task khusus yang hanya dieksekusi jika dipicu oleh task reguler melalui direktif `notify`. Notifikasi ini hanya dikirimkan jika task yang memicu menghasilkan status perubahan sistem (`changed: true`); jika statusnya `ok` (tidak ada perubahan), handler tidak akan berjalan. Secara default, seluruh handler ditunda eksekusinya dan baru dijalankan satu kali di bagian akhir dari play meskipun dinotifikasi berkali-kali oleh task yang berbeda. Jika diperlukan eksekusi handler seketika di tengah-tengah task (misal restart service sebelum menjalankan database migration), modul `ansible.builtin.meta: flush_handlers` dapat digunakan.

## Contoh singkat
```yaml
tasks:
  - name: Ubah konfigurasi port
    ansible.builtin.lineinfile:
      path: /etc/ssh/sshd_config
      regexp: '^#?Port 22'
      line: 'Port 2222'
    notify: Restart SSH

handlers:
  - name: Restart SSH
    ansible.builtin.service:
      name: sshd
      state: restarted
```

## Referensi resmi
- [Handlers: running operations on change](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_handlers.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
