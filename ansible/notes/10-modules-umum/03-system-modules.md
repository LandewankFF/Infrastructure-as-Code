# Modul Administrasi Sistem & Service

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Pengelolaan siklus hidup daemon sistem, pengguna, dan penjadwalan dilakukan melalui modul-modul administrasi sistem bawaan. Modul `ansible.builtin.service` dan `ansible.builtin.systemd` (khusus init systemd modern) digunakan untuk menyalakan (`state: started`), mematikan, atau mengaktifkan service saat boot (`enabled: true`), serta me-reload konfigurasi daemon (`daemon_reload: true`). Modul `ansible.builtin.user` dan `ansible.builtin.group` mengelola akun pengguna, grup sekunder, dan home directory. Modul `ansible.builtin.cron` mengelola entri crontab berkala, sedangkan `ansible.builtin.reboot` mampu menangani proses reboot mesin remote secara aman dan menunggu hingga mesin kembali online.

## Contoh singkat
```yaml
- name: Pastikan service SSH aktif dan menyala saat boot
  ansible.builtin.service:
    name: sshd
    state: started
    enabled: true
```

## Referensi resmi
- [ansible.builtin.service module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/service_module.html)
- [ansible.builtin.user module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/user_module.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
