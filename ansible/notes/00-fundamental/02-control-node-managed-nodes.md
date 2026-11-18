# Control Node vs Managed Nodes & Arsitektur Agentless

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Arsitektur Ansible terbagi menjadi dua peran utama, yaitu Control Node dan Managed Nodes. Control Node adalah mesin tempat paket Ansible dan Python diinstal dan tempat Anda mengeksekusi perintah CLI atau playbook; mesin ini harus menggunakan sistem operasi bertipe Unix/Linux atau macOS dan saat ini Windows tidak didukung sebagai Control Node secara native. Managed Nodes adalah perangkat target seperti server Linux/Windows, VM, atau perangkat jaringan yang dikelola oleh Ansible tanpa memerlukan instalasi software agen khusus. Komunikasi antara Control Node dan Managed Node berbasis Linux menggunakan protokol SSH standar dengan autentikasi berbasis SSH key pair, sedangkan untuk Windows umumnya menggunakan WinRM atau OpenSSH.

## Contoh singkat
```bash
# Pengujian konektivitas arsitektur agentless dari Control Node ke Managed Node
ansible all -i "192.168.1.10," -m ansible.builtin.ping -u ubuntu --private-key ~/.ssh/id_ed25519
```

## Referensi resmi
- [Ansible Basic Concepts](https://docs.ansible.com/ansible/latest/network/getting_started/basic_concepts.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
