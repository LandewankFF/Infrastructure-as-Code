# Kontrol Status: failed_when, changed_when, ignore_errors

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Secara default, Ansible menganggap sebuah task gagal jika modul mengembalikan exit code non-zero atau parameter error internal lainnya, dan task sukses tanpa perubahan sebagai `ok`. Dengan `failed_when`, Anda dapat mengkustomisasi kriteria kegagalan task berdasarkan teks keluaran stdout/stderr tertentu daripada exit code semata. `changed_when` digunakan untuk mengontrol kapan task harus dilaporkan sebagai `changed` (kuning) atau `ok` (hijau), mencegah task seperti `command` atau `shell` selalu memicu status `changed` yang merusak idempotency. `ignore_errors: true` memungkinkan Ansible tetap melanjutkan eksekusi playbook meskipun task tersebut mengalami error fatal.

## Contoh singkat
```yaml
- name: Menjalankan script pemeriksa status
  ansible.builtin.command: /usr/local/bin/check_health.sh
  register: health_check
  failed_when: "'CRITICAL' in health_check.stdout"
  changed_when: false
```

## Referensi resmi
- [Error Handling](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_error_handling.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
