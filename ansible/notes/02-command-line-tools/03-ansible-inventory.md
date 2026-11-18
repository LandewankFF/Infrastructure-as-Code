# CLI ansible-inventory & Inspeksi Host

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
`ansible-inventory` adalah utilitas baris perintah yang digunakan untuk menampilkan dan memvalidasi struktur inventory yang sedang aktif dibaca oleh Ansible. Utilitas ini sangat berharga ketika bekerja dengan inventory besar, hierarki nested group yang rumit, atau dynamic inventory plugins dari cloud provider. Dengan opsi `--graph`, Anda dapat melihat pohon visual hubungan antar grup dan host secara intuitif. Opsi `--list` mengembalikan seluruh struktur host beserta variabelnya dalam format JSON terpadu, sedangkan `--host <hostname>` menampilkan seluruh variabel gabungan dari host yang dipilih.

## Contoh singkat
```bash
# Menampilkan visualisasi pohon grup dan host dari inventory
ansible-inventory -i inventory.ini --graph
```

## Referensi resmi
- [Ansible Command Guide](https://docs.ansible.com/ansible/latest/command_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
