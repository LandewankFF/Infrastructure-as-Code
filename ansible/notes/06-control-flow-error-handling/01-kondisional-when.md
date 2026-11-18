# Eksekusi Kondisional dengan when

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Klausa `when` digunakan untuk mengeksekusi suatu task hanya jika ekspresi kondisi yang ditentukan bernilai benar (`True`). Kondisi yang ditulis pada `when` dievaluasi langsung sebagai ekspresi Jinja2 tanpa perlu tanda kurung kurawal ganda `{{ ... }}`. Anda dapat menggabungkan beberapa kondisi menggunakan operator logika Python seperti `and`, `or`, `not`, atau dengan menyusun daftar list yang secara implisit berarti logika `and`. Klausa `when` sering dipadukan dengan facts sistem operasi, variabel lingkungan, atau output status dari task sebelumnya yang ditangkap dengan direktif `register`.

## Contoh singkat
```yaml
- name: Restart service hanya jika file konfigurasi mengalami perubahan
  ansible.builtin.service:
    name: nginx
    state: restarted
  when: config_result.changed and ansible_facts['os_family'] == "Debian"
```

## Referensi resmi
- [Conditionals](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_conditionals.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
