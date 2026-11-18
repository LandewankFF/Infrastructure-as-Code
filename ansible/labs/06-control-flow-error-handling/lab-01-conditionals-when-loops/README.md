# Lab: Kombinasi Klausa when dan Loop

## Tujuan Lab
Menerapkan pengkondisian selektif di dalam perulangan task untuk memproses hanya item yang memenuhi kriteria tertentu.

## Prasyarat
- Paham sintaks loop dan loop_control

## Langkah-langkah Pengerjaan
1. Lengkapi playbook `conditional-tasks.yml` dengan sebuah loop yang mengiterasi daftar user dictionary (nama dan role).
2. Tambahkan klausul `when: item.role == 'admin'` agar hanya user admin yang diproses.
3. Gunakan `loop_control.label` agar tampilan terminal ringkas dan tidak memunculkan data sensitif.

## Kriteria Berhasil (Checklist)
- [ ] Hanya item yang lolos evaluasi kondisi `when` yang dieksekusi
- [ ] Item non-admin otomatis dilewati dengan status `skipping`
- [ ] Output console bersih dan rapi dengan custom label
