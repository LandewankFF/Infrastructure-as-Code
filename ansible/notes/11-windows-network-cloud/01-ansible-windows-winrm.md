# Automasi Windows via WinRM & OpenSSH

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Ansible mampu mengelola sistem operasi Windows Server secara agentless menggunakan protokol Windows Remote Management (WinRM) atau OpenSSH for Windows. Karena lingkungan eksekusi di Windows berbasis PowerShell dan bukan bash/Python, modul Windows dikelompokkan dalam namespace khusus seperti `ansible.windows` (misal `ansible.windows.win_service`, `win_package`, `win_reboot`). Konfigurasi koneksi membutuhkan parameter variabel khusus seperti `ansible_connection: winrm`, `ansible_winrm_server_cert_validation: ignore`, dan port 5986 (HTTPS). Modul Windows dirancang dengan prinsip idempotency yang sama dengan modul Linux untuk memastikan konfigurasi state yang konsisten.

## Contoh singkat
```yaml
- name: Pastikan service Spooler Windows berjalan
  ansible.windows.win_service:
    name: Spooler
    state: started
    start_mode: auto
```

## Referensi resmi
- [Windows setup guide](https://docs.ansible.com/ansible/latest/os_guide/intro_windows.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
