# Mendefinisikan Variabel Runtime dengan set_fact

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Modul `ansible.builtin.set_fact` digunakan untuk membuat atau memperbarui variabel secara dinamis di tengah-tengah eksekusi playbook saat runtime. Variabel yang dibuat dengan `set_fact` berlaku per host dan bertahan selama siklus eksekusi play berlangsung. Modul ini sering digunakan untuk menyimpan hasil olahan string, memanipulasi dictionary, atau menentukan nilai variabel konfigurasi baru berdasarkan fakta sistem atau keluaran dari task sebelumnya. Variabel yang dibuat melalui `set_fact` memiliki prioritas yang tinggi di dalam hirarki precedence Ansible.

## Contoh singkat
```yaml
- name: Tentukan environment target berdasarkan nama hostname
  ansible.builtin.set_fact:
    target_env: "{{ 'prod' if 'prod' in inventory_hostname else 'dev' }}"

- name: Cetak environment
  ansible.builtin.debug:
    var: target_env
```

## Referensi resmi
- [ansible.builtin.set_fact module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/set_fact_module.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
