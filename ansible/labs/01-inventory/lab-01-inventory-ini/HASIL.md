# Log Hasil Praktek: Menyusun Inventory Format INI

> Tanggal pengerjaan: 19 November 2026  
> Status: [x] Selesai Sukses  [ ] Selesai Sebagian  [ ] Mengalami Kendala  

---

## 1. Perintah yang Dijalankan

```bash
# 1. Menampilkan struktur visual pohon hierarki grup dan host
ansible-inventory -i hosts.ini --graph

# 2. Mengecek detail variabel koneksi pada host tertentu
ansible-inventory -i hosts.ini --host 192.168.1.11

# 3. Menampilkan seluruh inventory dalam format JSON
ansible-inventory -i hosts.ini --list
```

---

## 2. Output Eksekusi Terminal

### A. Output Graph Hierarki (`--graph`)
```text
@all:
  |--@ungrouped:
  |--@production:
  |  |--@Docker_Swarm:
  |  |  |--192.168.1.11
  |  |  |--192.168.1.12
  |  |  |--192.168.1.13
  |  |--@Database:
  |  |  |--192.168.1.20
```

### B. Output Detail Variabel Host (`--host 192.168.1.11`)
```json
{
    "ansible_ssh_private_key_file": "~/.ssh/id_ansible",
    "ansible_user": "root"
}
```

---

## 3. Temuan, Insight & Catatan Penting

### A. Struktur File INI pada Studi Kasus Docker Swarm & Database
Pada studi kasus ini terdapat dua grup fungsional:
1. `[Docker_Swarm]` : Berisi 3 server node swarm (`192.168.1.11`, `192.168.1.12`, `192.168.1.13`).
2. `[Database]` : Berisi 1 server database (`192.168.1.20`).

### B. Nested Group (`:children`)
Untuk mengelola banyak grup sekaligus dalam satu eksekusi, Ansible menyediakan fitur *nested group* dengan pola `[<nama_grup_induk>:children]`.
```ini
[production:children]
Docker_Swarm
Database
```
* **Keuntungan:** Kita bisa menjalankan playbook ke grup `production` (`hosts: production`), dan perintah otomatis menjangkau semua server di grup `Docker_Swarm` dan `Database`.

### C. Penanganan Variabel Grup (`:vars`)
Ada 2 skenario utama saat mengelola variabel koneksi SSH:
1. **Semua grup memakai user dan SSH key yang sama (Global):**
   * Gunakan grup bawaan `[all:vars]`.
   * Variabel otomatis diwariskan ke grup `Docker_Swarm` maupun `Database` tanpa perlu menduplikasi penulisan variabel.
2. **Kredensial tiap grup berbeda (Spesifik per grup):**
   * Gunakan `[Docker_Swarm:vars]` untuk user root swarm.
   * Gunakan `[Database:vars]` untuk user khusus database (misal: `ansible_user=dbadmin`).
