# Menyimpan Output Task dengan Variabel Register

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Direktif `register` digunakan untuk menangkap hasil keluaran eksekusi dari suatu task dan menyimpannya ke dalam variabel untuk digunakan pada task berikutnya. Nilai yang disimpan berupa dictionary data yang memuat informasi status eksekusi, seperti `changed`, `failed`, `rc` (return code), `stdout`, `stderr`, dan detail JSON kembalian dari modul terkait. Variabel hasil register sering dikombinasikan dengan kondisi `when` untuk mengambil keputusan kondisional atau dengan modul `ansible.builtin.debug` untuk melakukan troubleshooting data output. Variabel register terikat pada masing-masing host, sehingga nilai output pada host A tidak akan tertukar dengan host B.

## Contoh singkat
```yaml
- name: Jalankan command custom
  ansible.builtin.command: uname -r
  register: kernel_info

- name: Tampilkan kernel release
  ansible.builtin.debug:
    msg: "Versi kernel adalah: {{ kernel_info.stdout }}"
```

## Referensi resmi
- [Registering variables](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_variables.html#registering-variables)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
