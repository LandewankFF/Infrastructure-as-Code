# Instalasi & Manajemen Koleksi Ansible

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Ansible Collections dapat diunduh dan dipasang ke Control Node menggunakan utilitas baris perintah `ansible-galaxy collection install <nama_koleksi>`. Secara default, koleksi akan dipasang ke direktori `~/.ansible/collections/ansible_collections/` atau path sistem yang ditentukan dalam parameter `collections_paths` pada `ansible.cfg`. Collections mendistribusikan modul, action plugins, callback plugins, dan roles dari berbagai vendor pihak ketiga (seperti `amazon.aws`, `community.docker`, `cisco.ios`) secara independen dari siklus rilis `ansible-core`. CLI ini juga mendukung instalasi langsung dari tarball offline atau repositori Git privat internal perusahaan.

## Contoh singkat
```bash
# Menginstal koleksi Docker dari Ansible Galaxy portal
ansible-galaxy collection install community.docker
```

## Referensi resmi
- [Collections Guide](https://docs.ansible.com/ansible/latest/collections_guide/index.html)
- [Galaxy User Guide](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
