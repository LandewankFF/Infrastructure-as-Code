# Cheatsheet: Sintaks YAML untuk Ansible

Playbook dan konfigurasi Ansible ditulis dalam format **YAML** (YAML Ain't Markup Language). Berikut adalah aturan sintaks dasar dan perangkap umum yang harus dipahami.

## 1. Aturan Dasar & Struktur Dokumen

- Dokumen YAML diawali dengan tiga tanda hubung (`---`) untuk menandai awal dokumen.
- Akhir dokumen ditandai dengan tiga titik (`...`) (opsional).
- **Indentasi**: Gunakan spasi murni (standar 2 spasi per level). **Tab dilarang keras**.

```yaml
---
# Contoh struktur dokumen YAML Ansible
- name: Play pertama
  hosts: all
  gather_facts: false
  tasks:
    - name: Ping host
      ansible.builtin.ping:
```

---

## 2. Tipe Data Dasar

### A. Key-Value (Dictionary / Mapping)
Selalu beri spasi setelah tanda titik dua (`:`):
```yaml
web_port: 80
server_name: "web01.example.com"
is_production: false
```

### B. List / Sequences
Diawali tanda strip (`-`) diikuti spasi:
```yaml
packages:
  - nginx
  - mariadb-server
  - php-fpm

# Format inline (JSON-style list):
dns_servers: [8.8.8.8, 1.1.1.1]
```

### C. List of Dictionaries (Struktur Umum Tasks)
```yaml
tasks:
  - name: Install Nginx
    ansible.builtin.apt:
      name: nginx
      state: present

  - name: Pastikan service berjalan
    ansible.builtin.service:
      name: nginx
      state: started
```

---

## 3. String & Multiline Scalar

### A. Quoting Strings & Jinja2 Gotcha
Jika sebuah nilai string diawali dengan kurung kurawal ganda Jinja2 (`{{ ... }}`), baris tersebut **wajib** diapit tanda kutip (`"` atau `'`) agar parser YAML tidak mengira itu adalah mapping inline.

```yaml
# SALAH (Menyebabkan YAML Syntax Error):
message: {{ greeting }}

# BENAR:
message: "{{ greeting }}"
dest_path: "/var/www/{{ app_name }}"
```

### B. Literal Block Scalar (`|`)
Menjaga format baris baru (*preserve newlines*). Cocok untuk script multi-baris atau konfigurasi multiline:
```yaml
script_content: |
  #!/usr/bin/env bash
  set -euo pipefail
  echo "Mulai deployment"
  systemctl restart nginx
```

### C. Folded Block Scalar (`>`)
Menggabungkan baris baru menjadi satu spasi (*fold newlines* into single space), kecuali untuk baris kosong:
```yaml
long_description: >
  Ini adalah kalimat yang sangat panjang
  yang dipecah ke beberapa baris agar kode
  tetap rapi di bawah 80 karakter per baris.
```

---

## 4. Nilai Boolean

Ansible mendukung beberapa representasi boolean, namun best practice resmi menyarankan `true` atau `false` dengan huruf kecil:
```yaml
# Best practice:
enabled: true
restart_on_change: false

# Nilai lain yang didukung YAML tetapi kurang disarankan:
legacy_yes: yes
legacy_no: no
```

---

## 5. Perangkap Umum (Common Pitfalls)

1. **Tab vs Spasi**: Selalu konfigurasi editor teks Anda untuk mengubah tombol `Tab` menjadi 2 spasi.
2. **Karakter Titik Dua**: `key: value` harus memiliki spasi setelah `:`. Tulisan `http://` di dalam teks sering memicu parse error jika tidak di-quote.
3. **Karakter Khusus**: Karakter seperti `*`, `&`, `!`, `%`, `@` memiliki arti khusus di YAML. Selalu apit string yang memuat karakter ini dengan tanda kutip.
