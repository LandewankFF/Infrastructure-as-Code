# Lab: Audit Konfigurasi dengan ansible-config & Testing Flags

## Tujuan Lab
Menganalisis konfigurasi aktif menggunakan CLI ansible-config dan menguji kombinasi flag CLI penting (-l, -e, -v).

## Prasyarat
- Memiliki pemahaman dasar opsi konfigurasi

## Langkah-langkah Pengerjaan
1. Jalankan `ansible-config dump --only-changed` di folder lab ini.
2. Jalankan ad-hoc dengan flag `-e 'pesan_tambahan=Halo'` dan tampilkan nilainya via modul debug.
3. Uji opsi verbosity dari `-v` hingga `-vvv` dan amati perbedaan detail log yang dihasilkan.

## Kriteria Berhasil (Checklist)
- [ ] Berhasil mengidentifikasi parameter yang berubah melalui ansible-config
- [ ] Berhasil menginjeksi variabel runtime melalui flag `-e`
- [ ] Memahami fungsi dari masing-masing tingkatan verbosity flag `-v`
