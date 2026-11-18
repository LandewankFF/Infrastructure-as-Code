# Lab: Inspeksi dan Filter Ansible Facts Sistem

## Tujuan Lab
Mengumpulkan fakta sistem target secara otomatis dan menggunakan modul setup untuk memfilter informasi spesifik seperti antarmuka jaringan dan memori.

## Prasyarat
- Paham struktur variabel ansible_facts

## Langkah-langkah Pengerjaan
1. Jalankan ad-hoc command dengan modul `setup` terfilter: `ansible localhost -m setup -a 'filter=ansible_distribution*' -i localhost, -c local`.
2. Lengkapi playbook `inspect-facts.yml` untuk menampilkan IP address default, total memori RAM, dan OS distribution.
3. Uji efisiensi eksekusi dengan menyetel `gather_facts: false` dan amati efeknya jika task mencoba membaca facts.

## Kriteria Berhasil (Checklist)
- [ ] Mampu mengekstrak fakta sistem spesifik menggunakan filter modul setup
- [ ] Playbook berhasil mencetak detail hardware dan sistem operasi localhost
- [ ] Memahami kapan harus menyalakan atau mematikan gather_facts
