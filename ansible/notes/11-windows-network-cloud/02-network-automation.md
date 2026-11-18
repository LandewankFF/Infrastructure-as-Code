# Automasi Perangkat Jaringan (Network Automation)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Ansible Network Automation memungkinkan manajemen router, switch, dan firewall (seperti Cisco IOS/NX-OS, Arista EOS, Juniper Junos) tanpa memerlukan Python di perangkat target. Koneksi dilakukan menggunakan connection plugin khusus seperti `ansible.netcommon.network_cli` atau `httpapi` yang berinteraksi langsung melalui sesi SSH terminal atau REST API. Variabel penting `ansible_network_os` wajib ditentukan di inventory (misal `cisco.ios.ios`) agar Ansible memahami dialek CLI perangkat jaringan tersebut. Modul jaringan terbagi menjadi modul baris perintah imperatif (`*_command`) dan Resource Modules deklaratif (`*_interfaces`, `*_vlans`) yang mendukung state idempotent.

## Contoh singkat
```yaml
- name: Backup running-config pada switch Cisco IOS
  cisco.ios.ios_command:
    commands:
      - show running-config
  register: config_output
```

## Referensi resmi
- [Network basic concepts](https://docs.ansible.com/ansible/latest/network/getting_started/basic_concepts.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
