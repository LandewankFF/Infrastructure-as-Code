# Lab: Mengontrol Status dengan changed_when & failed_when

## Tujuan Lab
Mencegah perintah command/shell merusak sifat idempotensi dengan mengatur parameter changed_when dan mendefinisikan kriteria error kustom dengan failed_when.

## Prasyarat
- Paham output register variable pada task command

## Langkah-langkah Pengerjaan
1. Buka `custom-status.yml` yang menjalankan perintah arbitrary.
2. Gunakan `changed_when: false` pada task read-only agar tidak memicu status kuning (changed).
3. Gunakan `failed_when: "'FATAL' in result.stdout"` pada task berikutnya untuk menentukan kegagalan berdasarkan string output.

## Kriteria Berhasil (Checklist)
- [ ] Task read-only menghasilkan status hijau `ok` dan bukan kuning `changed`
- [ ] Kondisi error kustom berhasil dievaluasi sesuai isi teks stdout
