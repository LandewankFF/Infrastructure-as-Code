# Metodologi Pengujian Idempotency

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Idempotency adalah sifat inti dari konfigurasi Ansible yang berkualitas: eksekusi playbook pertama kali akan mengubah sistem (`changed > 0`), namun eksekusi kedua dengan konfigurasi yang sama persis harus menghasilkan `changed=0` (hanya `ok` tanpa perubahan). Pengujian idempotency dilakukan dengan cara menjalankan playbook yang sama dua kali berturut-turut pada target environment pengujian; jika pada eksekusi kedua tercatat ada task yang masih berstatus `changed`, maka terjadi kebocoran idempotensi (idempotency bug). Penyebab paling umum adalah penggunaan task `ansible.builtin.command` atau `shell` yang tidak dikontrol dengan `changed_when: false` atau pembuatan file sementara tanpa verifikasi kondisi awal.

## Contoh singkat
```bash
# Verifikasi idempotency: eksekusi kedua wajib menghasilkan changed=0
ansible-playbook -i inventory.ini site.yml
ansible-playbook -i inventory.ini site.yml | grep -q 'changed=0.*failed=0' && echo 'IDEMPOTENT PASS'
```

## Referensi resmi
- [Ansible Test Strategies](https://docs.ansible.com/ansible/latest/reference_appendices/test_strategies.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
