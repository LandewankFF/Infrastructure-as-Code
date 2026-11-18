# Kompilasi Flag CLI Esensial

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Menguasai flag pada baris perintah Ansible sangat meningkatkan produktivitas dan kontrol operasional seorang DevOps engineer. Flag koneksi dan autentikasi seperti `-u` (remote user), `-b` (become/sudo), `-K` (ask become pass), dan `-k` (ask SSH pass) menentukan bagaimana akses administratif diperoleh di target node. Flag operasional seperti `-i` (inventory), `-l` (limit), `-e` (extra vars untuk override variabel), dan `-f` (forks untuk konkurensi) mengatur cakupan dan performa eksekusi. Tingkat log keluaran diatur dengan `-v` hingga `-vvvv` untuk penelusuran masalah koneksi SSH dan internal modul secara presisi.

## Contoh singkat
```bash
# Menjalankan playbook dengan variabel dinamis, become, dan verbosity level 3
ansible-playbook -i inventory.ini deploy.yml -e "app_version=2.1.0" -b -K -vvv
```

## Referensi resmi
- [Ansible Command Guide](https://docs.ansible.com/ansible/latest/command_guide/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
