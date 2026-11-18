# Sintaks Dasar Templating Jinja2

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Jinja2 adalah template engine berbasis Python yang digunakan oleh Ansible untuk merender string dinamis dan file konfigurasi. Sintaks dasar Jinja2 menggunakan tiga penanda utama: kurung kurawal ganda `{{ ... }}` untuk mencetak nilai variabel atau hasil ekspresi, kurung kurawal dengan persen `{% ... %}` untuk pernyataan kontrol logika seperti pengkondisian atau perulangan, dan kurung kurawal dengan pagar `{# ... #}` untuk komentar internal template. Jinja2 dievaluasi di Control Node sebelum file ditransfer atau diaplikasikan ke managed node. Penggunaan Jinja2 sangat penting agar satu file konfigurasi standar dapat beradaptasi secara otomatis dengan variabel lingkungan dan fakta sistem server masing-masing.

## Contoh singkat
```jinja2
{# Template sederhana Jinja2 #}
ServerAdmin webmaster@{{ ansible_facts['fqdn'] }}
Listen {{ http_port | default(80) }}
```

## Referensi resmi
- [Templating (Jinja2)](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_templating.html)
- [Using filters to manipulate data](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_filters.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
