# Include Role (Dynamic) vs Import Role (Static)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Ansible menyediakan dua mekanisme untuk memanggil role di dalam task list, yaitu `ansible.builtin.import_role` (statis) dan `ansible.builtin.include_role` (dinamis). `import_role` diproses secara statis saat playbook pertama kali diparsing sebelum task dijalankan; akibatnya opsi seperti `when` akan diterapkan ke setiap task individual di dalam role, dan tags diwariskan secara statis. Sebaliknya, `include_role` diproses secara dinamis saat giliran task tersebut tiba di runtime; artinya evaluasi variabel kondisi `when` baru dilakukan saat task berjalan dan nama role bahkan dapat ditentukan melalui variabel dinamis. Pemilihan antara import dan include bergantung pada apakah Anda memerlukan sifat deterministik statis atau fleksibilitas dinamis.

## Contoh singkat
```yaml
# Dynamic include role berdasarkan kondisi runtime
- name: Load database role hanya jika db_enabled true
  ansible.builtin.include_role:
    name: "{{ database_type }}_db"
  when: db_enabled | bool
```

## Referensi resmi
- [Re-using artifacts](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
