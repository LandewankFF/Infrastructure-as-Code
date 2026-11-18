# Modul Utilitas & Alur Logika (uri, git, stat, debug, assert)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Modul utilitas menyediakan fungsi-fungsi esensial untuk memeriksa status, interaksi jaringan, dan kontrol kualitas eksekusi playbook. Modul `ansible.builtin.uri` berinteraksi dengan API RESTful HTTP/HTTPS untuk pengujian health-check atau memicu webhook eksternal. Modul `ansible.builtin.get_url` mengunduh berkas dari internet, sedangkan `ansible.builtin.git` mengkloning dan memperbarui repositori Git di server target. Modul `ansible.builtin.stat` memeriksa keberadaan file, ukuran, atau checksum sebelum aksi dilakukan. Modul `ansible.builtin.debug` mencetak pesan ke terminal, dan `ansible.builtin.assert` memvalidasi kondisi asumsi logika yang akan menghentikan playbook jika kondisinya tidak terpenuhi.

## Contoh singkat
```yaml
- name: Periksa apakah endpoint web menghasilkan status HTTP 200
  ansible.builtin.uri:
    url: http://localhost/healthz
    status_code: 200
```

## Referensi resmi
- [ansible.builtin.uri module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/uri_module.html)
- [ansible.builtin.git module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/git_module.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
