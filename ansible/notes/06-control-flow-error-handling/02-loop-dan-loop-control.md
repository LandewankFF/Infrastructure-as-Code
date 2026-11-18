# Perulangan Modern: loop & loop_control

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Keyword `loop` adalah standar modern di Ansible untuk mengiterasi task terhadap daftar list atau struktur dictionary, menggantikan sintaks `with_*` yang lama. Di dalam task yang diulang, elemen yang sedang aktif diakses melalui variabel bawaan `item`. Untuk kontrol yang lebih rapi, direktif `loop_control` dapat digunakan untuk mengganti nama variabel `item` (`loop_var`), menambahkan indeks urutan iterasi (`index_var`), atau membatasi output log console yang terlalu berisik menggunakan `label`. Fitur ini sangat bermanfaat saat membuat banyak user, mengelola sekumpulan file, atau memasang serangkaian dependensi sistem.

## Contoh singkat
```yaml
- name: Membuat beberapa pengguna sistem
  ansible.builtin.user:
    name: "{{ user_item.name }}"
    shell: "{{ user_item.shell }}"
    state: present
  loop:
    - { name: 'alice', shell: '/bin/bash' }
    - { name: 'bob', shell: '/bin/zsh' }
  loop_control:
    loop_var: user_item
    label: "{{ user_item.name }}"
```

## Referensi resmi
- [Loops](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_loops.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
