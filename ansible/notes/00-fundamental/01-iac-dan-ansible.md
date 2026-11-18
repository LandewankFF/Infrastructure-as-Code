# Infrastructure as Code (IaC) & Konsep Inti Ansible

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Infrastructure as Code (IaC) adalah metodologi pengelolaan dan penyediaan infrastruktur komputasi melalui kode terstruktur yang dapat dilacak versinya, bukan melalui konfigurasi manual. Ansible menggunakan pendekatan deklaratif di mana Anda mendefinisikan kondisi akhir (desired state) dari sistem daripada menuliskan urutan langkah imperatif. Salah satu prinsip utama Ansible adalah idempotency, yang menjamin bahwa menjalankan automasi berulang kali dengan parameter yang sama tidak akan mengubah sistem jika kondisi akhir sudah tercapai. Ansible beroperasi secara agentless dengan model push, mengirim modul langsung dari control node ke target managed nodes melalui SSH atau WinRM tanpa perlu menginstal daemon agen pada server target.

## Contoh singkat
```yaml
# Pendekatan deklaratif: memastikan Nginx terpasang dan service berjalan
- name: Pastikan Nginx terpasang dan aktif
  ansible.builtin.apt:
    name: nginx
    state: present
    update_cache: true
```

## Referensi resmi
- [Ansible Getting Started](https://docs.ansible.com/ansible/latest/getting_started/index.html)
- [Ansible Installation Guide](https://docs.ansible.com/ansible/latest/installation_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
