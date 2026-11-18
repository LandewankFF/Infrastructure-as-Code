# Namespace Collections & Konvensi FQCN

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Setiap Ansible Collection dikelompokkan ke dalam struktur dua tingkat hierarki: `namespace` dan `collection_name`. Sebagai contoh, pada `community.docker`, `community` adalah namespace pengembang dan `docker` adalah nama koleksinya. Format kanonikal FQCN (`<namespace>.<collection>.<plugin>`) memastikan pemanggilan modul di playbook bebas dari tabrakan nama (name collision) dan memiliki dependensi eksplisit. Penggunaan FQCN mempermudah identifikasi sumber modul saat audit kode dan merupakan aturan wajib dalam standardisasi kode `ansible-lint` modern.

## Contoh singkat
```yaml
# Memanggil modul container menggunakan namespace FQCN resmi
- name: Jalankan redis container
  community.docker.docker_container:
    name: my-redis
    image: redis:alpine
    state: started
```

## Referensi resmi
- [Collections Guide](https://docs.ansible.com/ansible/latest/collections_guide/index.html)
- [Galaxy User Guide](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
