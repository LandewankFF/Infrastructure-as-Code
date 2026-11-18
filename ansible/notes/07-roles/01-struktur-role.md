# Arsitektur & Struktur Direktori Standar Role

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Role adalah cara standar Ansible untuk mengemas playbook, tasks, handlers, variabel, template, dan file pendukung ke dalam struktur direktori mandiri yang terorganisir dan reusable. Struktur standar role memiliki subdirektori spesifik: `tasks/` (alur pekerjaan utama), `handlers/` (task penanganan event), `defaults/` (variabel default dengan prioritas terendah), `vars/` (variabel internal dengan prioritas tinggi), `templates/` (file Jinja2 `.j2`), `files/` (file statis), dan `meta/` (metadata dan dependensi). Dengan membagi automasi ke dalam role, playbook utama Anda (`site.yml`) menjadi sangat bersih dan ringkas karena hanya memanggil nama-nama role yang dibutuhkan.

## Contoh singkat
```yaml
# Contoh pemanggilan role di dalam playbook utama
---
- name: Setup Web Server
  hosts: webservers
  roles:
    - role: common
    - role: nginx
      vars:
        nginx_port: 8080
```

## Referensi resmi
- [Roles](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html)
- [Galaxy User Guide](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
