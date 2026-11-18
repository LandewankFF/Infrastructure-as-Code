# Modul Manajemen Paket: apt, dnf, pip, package

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Ansible menyediakan modul spesifik untuk berbagai package manager sistem operasi, seperti `ansible.builtin.apt` untuk Debian/Ubuntu, `ansible.builtin.dnf` untuk RHEL/Fedora/CentOS, dan `ansible.builtin.pip` untuk modul library Python. Jika Anda menginginkan playbook yang agnostik terhadap distro OS, modul generik `ansible.builtin.package` dapat digunakan sebagai wrapper yang secara otomatis memanggil package manager yang sesuai di managed node. Modul-modul ini memastikan prinsip idempotensi: jika paket sudah terpasang dengan versi yang diminta (`state: present`), Ansible tidak akan melakukan instalasi ulang. Parameter seperti `update_cache: true` dan `state: latest` digunakan untuk pembaharuan repositori dan paket.

## Contoh singkat
```yaml
- name: Install Nginx menggunakan modul apt
  ansible.builtin.apt:
    name: nginx
    state: present
    update_cache: true
```

## Referensi resmi
- [ansible.builtin.apt module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)
- [ansible.builtin.package module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/package_module.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
