# Lab: Pengujian dan Audit Idempotency Playbook

## Tujuan Lab
Mengidentifikasi dan memperbaiki task yang menyebabkan kebocoran idempotensi (selalu menghasilkan status changed pada setiap eksekusi).

## Prasyarat
- Paham arti status changed vs ok

## Langkah-langkah Pengerjaan
1. Jalankan playbook `idempotency-check.yml` dua kali berturut-turut.
2. Amati mengapa eksekusi kedua masih melaporkan `changed=1`.
3. Perbaiki task penyebab masalah menggunakan `creates`, `removes`, atau `changed_when` yang tepat.
4. Buktikan bahwa eksekusi kedua dan ketiga menghasilkan `changed=0` murni.

## Kriteria Berhasil (Checklist)
- [ ] Penyebab kegagalan idempotensi berhasil diidentifikasi
- [ ] Eksekusi playbook yang kedua kali menghasilkan `changed=0` dan `failed=0`
