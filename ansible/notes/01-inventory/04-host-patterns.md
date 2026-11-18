# Pola Pencocokan Host (Host Patterns)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Host patterns digunakan saat menentukan target `hosts:` pada play atau opsi `-l` (`--limit`) pada CLI untuk menyeleksi subset mesin dari inventory. Pola pencocokan mendukung nama host individual, nama grup, keyword khusus `all`, serta wildcard asteris (`web*`). Ansible juga mendukung operasi himpunan seperti irisan (`webservers:&production` untuk mesin yang ada di kedua grup), pengecualian (`webservers:!staging`), dan pengirisan indeks (`webservers[0:2]`). Fitur ini sangat bermanfaat dalam proses rolling deployment atau saat melakukan perbaikan darurat pada server tertentu.

## Contoh singkat
```bash
# Menjalankan playbook hanya pada webservers yang berada di environment staging
ansible-playbook -i inventory.ini site.yml --limit "webservers:&staging"
```

## Referensi resmi
- [Patterns: targeting hosts and groups](https://docs.ansible.com/ansible/latest/inventory_guide/intro_patterns.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
