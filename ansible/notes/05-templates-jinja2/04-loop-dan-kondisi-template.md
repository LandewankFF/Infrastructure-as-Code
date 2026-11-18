# Kondisi (if) dan Perulangan (for) di Template

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Di dalam file template Jinja2, Anda dapat menggunakan struktur kontrol seperti percabangan `{% if %}` dan perulangan `{% for %}` untuk menghasilkan baris konfigurasi yang adaptif. Blok `if/elif/else` berguna untuk memasukkan parameter konfigurasi hanya jika suatu kondisi variabel atau fakta sistem terpenuhi (misalnya menyalakan SSL hanya di environment produksi). Perulangan `for` sangat ideal untuk mengiterasi daftar port, domain virtual host, atau daftar IP backend cluster ke dalam satu file konfigurasi terpusat. Jinja2 juga menyediakan variabel khusus di dalam loop seperti `loop.index` dan `loop.last` untuk membantu formatting seperti koma atau titik koma.

## Contoh singkat
```jinja2
# Contoh iterasi upstream server di konfigurasi Nginx
upstream backend_cluster {
{% for host in groups['webservers'] %}
    server {{ hostvars[host]['ansible_default_ipv4']['address'] }}:8080;
{% endfor %}
}
```

## Referensi resmi
- [Templating (Jinja2)](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_templating.html)
- [Using filters to manipulate data](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_filters.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
