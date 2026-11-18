# Lab: Manipulasi Runtime dengan set_fact & Magic Variables

## Tujuan Lab
Mendefinisikan variabel runtime baru menggunakan set_fact serta memanfaatkan magic variables hostvars dan groups.

## Prasyarat
- Paham konsep magic variables

## Langkah-langkah Pengerjaan
1. Periksa host yang ada di `inventory.ini`.
2. Lengkapi playbook `magic-demo.yml` untuk membaca daftar host yang ada di dalam grup `webservers` menggunakan variabel `groups['webservers']`.
3. Gunakan modul `ansible.builtin.set_fact` untuk membuat variabel baru `deployment_timestamp` saat runtime.
4. Tampilkan nilai variabel runtime tersebut pada task berikutnya.

## Kriteria Berhasil (Checklist)
- [ ] Berhasil mengiterasi atau menampilkan anggota grup via magic variable `groups`
- [ ] Variabel dinamis berhasil dibuat dan terbaca via `set_fact`
