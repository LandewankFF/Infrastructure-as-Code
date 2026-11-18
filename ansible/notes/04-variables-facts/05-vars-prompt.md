# Interaksi Input Dinamis dengan vars_prompt

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Direktif `vars_prompt` digunakan pada level play untuk meminta pengguna memasukkan data secara interaktif melalui terminal sesaat sebelum task mulai dijalankan. Fitur ini umumnya digunakan untuk meminta data sensitif seperti password sementara, konfirmasi konfirmasi deployment, atau nomor versi rilis saat Ansible dijalankan secara manual oleh operator. Parameter `private: true` (nilai default) menyembunyikan input karakter dari layar agar password tidak terlihat oleh orang lain. Meskipun berguna untuk eksekusi manual, `vars_prompt` sebaiknya dihindari dalam pipeline CI/CD yang berjalan secara otomatis tanpa interaksi manusia.

## Contoh singkat
```yaml
---
- name: Deploy Aplikasi
  hosts: webservers
  vars_prompt:
    - name: release_version
      prompt: "Masukkan versi rilis yang ingin dideploy"
      private: false
  tasks:
    - name: Tampilkan versi yang dipilih
      ansible.builtin.debug:
        msg: "Mendeploy versi {{ release_version }}"
```

## Referensi resmi
- [Prompts in playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_prompts.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
