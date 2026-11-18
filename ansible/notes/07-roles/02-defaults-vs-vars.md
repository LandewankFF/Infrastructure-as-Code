# Perbedaan Peran: defaults/ vs vars/

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Di dalam sebuah role, direktori `defaults/main.yml` dan `vars/main.yml` sama-sama digunakan untuk menyimpan variabel, tetapi memiliki tingkat prioritas (precedence) yang sangat berbeda. Variabel pada `defaults/` memiliki prioritas paling rendah dalam seluruh hierarki Ansible, sehingga sengaja dirancang agar mudah ditimpa (overridden) oleh pengguna melalui `group_vars`, `host_vars`, atau parameter play. Sebaliknya, variabel pada `vars/` memiliki prioritas yang sangat tinggi dan ditujukan untuk variabel internal yang bersifat konstan atau spesifik bagi logika internal role yang tidak boleh diubah sembarangan oleh pengguna eksternal. Praktik terbaik adalah menaruh seluruh opsi konfigurasi yang dapat dikustomisasi di `defaults/`.

## Contoh singkat
```yaml
# defaults/main.yml -> Pengguna dapat dengan mudah mengubah nilai ini di playbook
nginx_port: 80
nginx_worker_processes: "auto"

# vars/main.yml -> Variabel internal role, jarang di-override
nginx_package_name: "nginx-full"
```

## Referensi resmi
- [Role directory structure](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html#role-directory-structure)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
