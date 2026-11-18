# Tuning Performa: Forks, Pipelining, Fact Caching

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Seiring bertambahnya jumlah server yang dikelola, performa eksekusi Ansible dapat dioptimalkan melalui beberapa penyesuaian konfigurasi pada `ansible.cfg`. Parameter `forks` (default bernilai 5) dapat dinaikkan (misal ke 20 atau 50) untuk memperbanyak jumlah host yang diproses secara paralel, disesuaikan dengan kapasitas CPU dan bandwidth Control Node. Mengaktifkan SSH `pipelining = True` mengurangi jumlah koneksi SSH bolak-balik dengan mengeksekusi modul langsung dari memori tanpa menyalinnya ke temporary file disk remote. Terakhir, mengaktifkan `fact_caching` (misal menggunakan backend `jsonfile` atau `redis`) menghemat waktu eksekusi secara signifikan karena Ansible tidak perlu menjalankan `setup` berulang kali jika data fact belum kedaluwarsa.

## Contoh singkat
```ini
# ansible.cfg optimasi performa tinggi
[defaults]
forks = 25
fact_caching = jsonfile
fact_caching_connection = /tmp/ansible_facts_cache
fact_caching_timeout = 86400

[ssh_connection]
pipelining = True
```

## Referensi resmi
- [Ansible Tips and Tricks](https://docs.ansible.com/ansible/latest/tips_tricks/index.html)
- [Ansible Frequently Asked Questions](https://docs.ansible.com/ansible/latest/reference_appendices/faq.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
