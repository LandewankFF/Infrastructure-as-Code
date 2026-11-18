# Ansible Facts & Modul setup

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Facts adalah variabel yang memuat informasi terperinci mengenai sistem operasi, hardware, IP address, antarmuka jaringan, partisi disk, dan konfigurasi lingkungan dari managed node. Pada awal setiap play, Ansible secara otomatis menjalankan modul internal `ansible.builtin.setup` untuk mengumpulkan data facts ini (kecuali jika `gather_facts: false` ditentukan). Seluruh fakta disimpan dalam dictionary terstruktur `ansible_facts` (misalnya `ansible_facts['os_family']` atau `ansible_facts['default_ipv4']['address']`). Data ini sangat berguna untuk membuat playbook yang adaptif terhadap berbagai jenis distribusi Linux (misalnya membedakan instalasi paket antara Debian dan RedHat).

## Contoh singkat
```yaml
- name: Task bersyarat berdasarkan fakta sistem operasi
  ansible.builtin.apt:
    name: apache2
    state: present
  when: ansible_facts['os_family'] == "Debian"
```

## Referensi resmi
- [Discovering variables: facts](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_vars_facts.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
