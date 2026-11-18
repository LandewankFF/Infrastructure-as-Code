# Cheatsheet: Ansible CLI Commands & Flags

Kumpulan referensi cepat perintah baris (CLI) dan opsi flag yang paling sering digunakan pada **ansible-core 2.16**.

## 1. Perintah CLI Utama

| Perintah | Fungsi Utama | Contoh Penggunaan |
| :--- | :--- | :--- |
| `ansible` | Menjalankan *ad-hoc command* pada satu atau sekumpulan host. | `ansible all -i inventory.ini -m ping` |
| `ansible-playbook` | Mengeksekusi file playbook YAML terhadap inventory. | `ansible-playbook -i hosts.yml playbook.yml` |
| `ansible-inventory` | Menampilkan, memverifikasi, dan mendiagnosis struktur inventory. | `ansible-inventory -i inventory.ini --graph` |
| `ansible-doc` | Membaca dokumentasi modul, plugin, parameter, dan contoh kode langsung dari terminal. | `ansible-doc ansible.builtin.copy` |
| `ansible-config` | Memeriksa, melihat dump konfigurasi, dan melacak asal setting `ansible.cfg`. | `ansible-config dump --only-changed` |
| `ansible-galaxy` | Mengelola, mencari, dan menginstal roles serta collections dari Galaxy atau Git. | `ansible-galaxy role init my_role` |
| `ansible-vault` | Mengenkripsi, mendekripsi, dan mengedit file atau teks sensitif. | `ansible-vault encrypt vars/secrets.yml` |
| `ansible-lint` | Melakukan analisis statik dan pemeriksaan best practices pada playbook dan roles. | `ansible-lint playbook.yml` |

---

## 2. Flag & Opsi Esensial

| Flag / Opsi | Deskripsi Lengkap | Kapan Digunakan |
| :--- | :--- | :--- |
| `-i <path>` / `--inventory` | Menentukan lokasi file atau direktori inventory. | Selalu disarankan agar tidak bergantung pada default `/etc/ansible/hosts`. |
| `-m <module>` / `--module-name` | Menentukan nama modul yang dijalankan pada ad-hoc command. | Digunakan saat menjalankan perintah `ansible` (default modul: `command`). |
| `-a "<args>"` / `--args` | Argumen atau parameter yang dikirimkan ke modul pada ad-hoc command. | Digunakan bersamaan dengan opsi `-m`. Contoh: `-m command -a "uptime"`. |
| `-b` / `--become` | Mengaktifkan *privilege escalation* (default: `sudo` menjadi `root`). | Saat task membutuhkan akses administratif (install paket, edit `/etc`). |
| `-K` / `--ask-become-pass` | Meminta prompt password sudo/become secara interaktif di terminal. | Jika user remote membutuhkan password saat mengeksekusi `sudo`. |
| `-u <user>` / `--user` | Menentukan username SSH remote yang digunakan untuk koneksi. | Jika username remote berbeda dengan username lokal Control Node. |
| `-k` / `--ask-pass` | Meminta prompt password SSH koneksi remote secara interaktif. | Jika koneksi remote belum menggunakan SSH key pair. |
| `-l <subset>` / `--limit` | Membatasi eksekusi hanya ke host atau grup tertentu dari inventory. | Untuk pengujian bertahap atau perbaikan darurat pada host tertentu. |
| `-e "<vars>"` / `--extra-vars` | Mengirim variabel tambahan secara langsung via CLI (prioritas tertinggi). | Contoh: `-e "env=production port=8080"` atau `-e "@extra.json"`. |
| `-f <num>` / `--forks` | Menentukan jumlah proses paralel (default: 5). | Meningkatkan kecepatan eksekusi ketika mengelola puluhan/ratusan server. |
| `-v` / `-vv` / `-vvv` / `-vvvv` | Mengatur tingkat *verbosity* log output (makin banyak `v`, makin detail). | `-v` melihat hasil task, `-vvv` melihat koneksi SSH, `-vvvv` debug penuh. |
| `-C` / `--check` | Menjalankan *dry run* (check mode) tanpa mengubah state sistem managed node. | Memprediksi perubahan sebelum diterapkan langsung ke server produksi. |
| `-D` / `--diff` | Menampilkan perbedaan (*diff* baris demi baris) pada file yang diubah. | Sangat berguna digabung dengan `-C` untuk meninjau perubahan template/file. |
| `--syntax-check` | Memeriksa validitas sintaks YAML dan struktur playbook tanpa menjalankannya. | Digunakan di tahap awal pengujian atau pre-commit git checks. |
| `--step` | Meminta konfirmasi interaktif `[Y/n/c]` sebelum setiap task dieksekusi. | Untuk proses debugging langkah demi langkah yang aman. |
| `--start-at-task "<name>"` | Memulai eksekusi playbook dari task tertentu dengan mencocokkan namanya. | Melanjutkan proses setelah memperbaiki error pada task di tengah play. |
| `-t <tags>` / `--tags` | Menjalankan hanya task-task yang memiliki tag tertentu. | Contoh: `--tags "deploy,config"`. |
| `--skip-tags <tags>` | Melewati eksekusi task yang memiliki tag tertentu. | Contoh: `--skip-tags "slow,database"`. |
| `--list-tasks` | Menampilkan daftar seluruh task yang ada di dalam playbook tanpa menjalankannya. | Untuk memverifikasi urutan dan tag task. |
| `--list-hosts` | Menampilkan daftar seluruh host yang cocok dengan target play. | Untuk memverifikasi target host sebelum eksekusi berbahaya. |
| `--vault-id <label@source>` | Menentukan ID vault dan sumber password untuk dekripsi/enkripsi. | Contoh: `--vault-id dev@prompt` atau `--vault-id prod@.vault_pass`. |
