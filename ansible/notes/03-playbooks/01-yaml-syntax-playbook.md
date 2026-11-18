# Sintaks YAML dalam Playbook

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Playbook Ansible dibangun di atas format YAML yang mewajibkan penulisan yang rapi, berpasangan, dan terindentasi dengan tepat. Setiap dokumen diawali dengan `---` dan menggunakan indentasi 2 spasi (tidak boleh ada karakter tab) untuk menunjukkan hierarki data. Komponen utama dalam playbook adalah list of mappings, di mana tanda `-` menunjukkan elemen list baru (misalnya daftar play atau daftar task). String yang diawali tanda kurung kurawal ganda Jinja2 `{{` wajib diapit tanda kutip untuk mencegah kesalahan parser YAML yang mengira kurawal tersebut adalah dictionary inline.

## Contoh singkat
```yaml
---
# Contoh penulisan YAML playbook yang valid
- name: Setup Web Server
  hosts: all
  vars:
    site_title: "My Production Site"
  tasks:
    - name: Tampilkan judul
      ansible.builtin.debug:
        msg: "Situs: {{ site_title }}"
```

## Referensi resmi
- [YAML Syntax Reference](https://docs.ansible.com/ansible/latest/reference_appendices/YAMLSyntax.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
