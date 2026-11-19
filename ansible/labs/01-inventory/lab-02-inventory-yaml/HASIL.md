# Log Hasil Praktek: Konversi dan Penyusunan Inventory YAML

> Tanggal pengerjaan: 19 November 2026  
> Status: [x] Selesai Sukses  [ ] Selesai Sebagian  [ ] Mengalami Kendala  

---

## 1. Perintah yang Dijalankan

```bash
# 1. Menampilkan struktur visual pohon hierarki grup dan host dari inventory YAML
ansible-inventory -i hosts.yml --graph

# 2. Mengecek detail variabel koneksi pada host database
ansible-inventory -i hosts.yml --host 192.168.1.20

# 3. Menampilkan seluruh representasi inventory dalam format JSON
ansible-inventory -i hosts.yml --list
```

---

## 2. Output Eksekusi Terminal

### A. Output Graph Hierarki (`--graph`)
```text
@all:
  |--@ungrouped:
  |--@Docker_Swarm:
  |  |--192.168.1.11
  |  |--192.168.1.12
  |  |--192.168.1.13
  |--@Database:
  |  |--192.168.1.20
```

### B. Output Detail Variabel Host (`--host 192.168.1.20`)
```json
{
    "ansible_ssh_private_key_file": "~/.ssh/id_ansible",
    "ansible_user": "root"
}
```

---

## 3. Temuan, Insight & Catatan Penting

### A. Mental Model: Analogi Struktur Folder & File
Format YAML pada Ansible Inventory mengikuti struktur pohon (hierarki data) yang terikat aturan mutlak. Cara paling mudah memahaminya adalah menganalogikannya dengan sistem folder di komputer:

| Komponen di Komputer | Kata Kunci di Ansible YAML | Fungsi & Makna |
| :--- | :--- | :--- |
| **Root Drive (C:)** | `all:` | Folder induk terluar yang membawahi seluruh sistem inventory. |
| **Sub-Folder** | `children:` | Menandakan: *"Di dalam sini ada folder/grup turunan lain"*. |
| **File Sungguhan** | `hosts:` | Menandakan: *"Di dalam sini ada server fisik/IP sungguhan"*. |
| **Folder Properties** | `vars:` | Menandakan: *"Pengaturan/variabel yang ditempelkan ke folder/grup ini"*. |

---

### B. 4 Kata Kunci "Keramat" Ansible Inventory YAML
Ansible hanya mengenali 4 kata kunci struktural:
1. `all:` $\rightarrow$ Root group bawaan.
2. `children:` $\rightarrow$ Menampung daftar sub-grup.
3. `hosts:` $\rightarrow$ Menampung daftar node/IP server.
4. `vars:` $\rightarrow$ Menampung variabel/koneksi SSH.

Semua nama yang kita buat sendiri (seperti `Docker_Swarm` atau `Database`) adalah **nama grup kustom**. Oleh karena itu, nama-nama tersebut **wajib diletakkan di bawah `children:`**.

---

### C. Menjawab Keraguan & Rumus Mutlak Sintaks

1. **Kenapa `children:` ada di atas `Docker_Swarm`?**
   * Karena `Docker_Swarm` adalah sebuah **grup**, bukan server tunggal.
   * Jika ditaruh di bawah `children:`, Ansible mengerti itu adalah grup yang membawahi server-server lain.
   * Jika ditaruh di bawah `hosts:`, Ansible akan salah mengartikannya sebagai 1 server bernama `Docker_Swarm`.

2. **Kapan `children:` digunakan?**
   * `children:` dipakai setiap kali suatu grup memiliki grup turunan di dalamnya.
   * Karena root `all:` membawahi grup `Docker_Swarm` dan `Database`, maka di bawah `all:` wajib ada `children:`.

3. **Apakah `hosts:` selalu di bawah `vars:` atau grup?**
   * **`hosts:` berada langsung di bawah GRUP**, bukan di dalam `vars:`.
   * Posisi `hosts:`, `vars:`, dan `children:` adalah **sejajar** (saudara kandung satu level indentasi).
   * Di dalam `vars:` hanya berisi pasangan key-value variabel (`ansible_user: root`, dsb).

4. **Apakah urutan baris atas-bawah bersifat kaku?**
   * **Tidak.** Di YAML, yang menentukan hubungan hierarki adalah **indentasi spasi**, bukan siapa yang ditulis lebih dulu.
   * Menulis `vars:` sebelum `children:` atau `children:` sebelum `vars:` menghasilkan data yang sama persis di Ansible.

5. **Kewajiban Tanda Titik Dua (`:`) pada IP Host:**
   * Di format YAML, alamat IP seperti `192.168.1.11:` harus diakhiri tanda titik dua `:` karena IP tersebut bertindak sebagai key dalam dictionary YAML.
