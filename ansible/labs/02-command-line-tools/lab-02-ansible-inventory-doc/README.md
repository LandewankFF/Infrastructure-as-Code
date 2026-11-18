# Lab: Inspeksi Inventory dan Eksplorasi Dokumentasi CLI

## Tujuan Lab
Menggunakan utilitas ansible-inventory untuk troubleshooting hierarki host dan ansible-doc untuk meninjau opsi modul secara offline.

## Prasyarat
- Paham penggunaan terminal dasar

## Langkah-langkah Pengerjaan
1. Gunakan `ansible-inventory -i inventory.yml --graph` dan amati strukturnya.
2. Gunakan `ansible-inventory -i inventory.yml --host node1` untuk melihat seluruh dictionary variabelnya.
3. Gunakan `ansible-doc ansible.builtin.copy` untuk membaca dokumentasi modul copy.
4. Gunakan `ansible-doc -s ansible.builtin.service` untuk melihat snippet penulisan YAML.

## Kriteria Berhasil (Checklist)
- [ ] Berhasil menampilkan relasi grafis dan host variabel via CLI
- [ ] Mampu menemukan dan menyalin snippet parameter modul dari ansible-doc
