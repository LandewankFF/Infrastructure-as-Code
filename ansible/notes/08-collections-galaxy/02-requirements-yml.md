# Pengelolaan Dependensi dengan requirements.yml

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
File `requirements.yml` adalah file manifest deklaratif yang digunakan untuk melacak dan mengunci versi seluruh collections dan external roles yang dibutuhkan oleh proyek automasi. Mirip dengan `requirements.txt` di ekosistem Python atau `package.json` di Node.js, file ini memungkinkan seluruh anggota tim dan pipeline CI/CD mereplikasi dependensi lingkungan yang identik. Di dalamnya Anda dapat mendefinisikan nama koleksi, batasan versi (`version: ">=1.0.0"`), atau URL repositori Git untuk koleksi privat. Seluruh dependensi diinstal secara massal dengan mengeksekusi `ansible-galaxy install -r requirements.yml`.

## Contoh singkat
```yaml
# requirements.yml
collections:
  - name: community.general
    version: ">=8.0.0"
  - name: amazon.aws
    version: "7.1.0"
roles:
  - name: geerlingguy.docker
    version: "7.0.0"
```

## Referensi resmi
- [Installing collections with requirements file](https://docs.ansible.com/ansible/latest/collections_guide/collections_installing.html#install-multiple-collections-with-a-requirements-file)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
