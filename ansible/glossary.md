# Glossary Istilah Ansible

Tabel glosarium ini berisi istilah-istilah inti dalam ekosistem Ansible (berdasarkan ansible-core 2.16) untuk memudahkan pemahaman konsep fundamental dan lanjutan.

| Istilah | Arti | Catatan terkait |
| :--- | :--- | :--- |
| **Control Node** | Mesin tempat Ansible diinstal dan dieksekusi untuk mengelola infrastruktur target. | Membutuhkan OS berbasis Unix/Linux/macOS dan Python. Windows tidak didukung sebagai Control Node secara native (bisa via WSL). |
| **Managed Node** | Mesin target (server, VM, container, perangkat jaringan) yang dikonfigurasi dan dikelola oleh Ansible. | Bersifat *agentless*, hanya membutuhkan Python dan akses SSH (Linux/Unix) atau WinRM/OpenSSH (Windows). |
| **Inventory** | File atau sumber data yang mendefinisikan daftar host, IP, pengelompokan grup, dan variabel koneksi target. | Format umum berupa INI atau YAML. Mendukung statis maupun *dynamic inventory plugins*. |
| **Playbook** | File konfigurasi terstruktur dalam format YAML yang berisi satu atau lebih *play*. | Merupakan inti orkestrasi di mana Anda mendefinisikan *state* yang diinginkan pada managed nodes. |
| **Play** | Blok pemetaan di dalam playbook yang menghubungkan target host tertentu dengan serangkaian *tasks*. | Menentukan *who* (hosts), *how* (become, vars), dan *what* (tasks/roles). |
| **Task** | Unit aksi terkecil dan atomic di dalam play yang mengeksekusi modul tertentu dengan parameter spesifik. | Ansible menjalankan task satu per satu secara berurutan sesuai urutan deklarasi. |
| **Handler** | Task khusus yang hanya berjalan ketika dipicu oleh instruksi `notify` dari task lain yang mengalami perubahan (`changed: true`). | Umumnya dipakai untuk me-restart atau me-reload service saat konfigurasi berubah. Dieksekusi di akhir play secara default. |
| **Role** | Struktur pengorganisasian artefak automasi standar (tasks, handlers, vars, defaults, templates, files, meta) agar reusable dan modular. | Memudahkan pembagian kode antartim dan dapat didistribusikan melalui Ansible Galaxy. |
| **Module** | Unit kode diskrit yang dikirim dan dieksekusi oleh Ansible di managed node untuk menyelesaikan pekerjaan spesifik. | Modul bersifat idempotent (misal `ansible.builtin.apt`, `ansible.builtin.copy`, `ansible.builtin.service`). |
| **Plugin** | Potongan kode Python yang memperluas fungsi inti Ansible dan berjalan di Control Node. | Contoh: connection plugin, lookup plugin, filter plugin, inventory plugin, callback plugin. |
| **Collection** | Format distribusi standar modern yang membungkus modul, plugin, roles, dan playbook dalam satu namespace terpadu. | Diperkenalkan sejak Ansible 2.9/2.10, menggantikan arsitektur monolitik lama. Contoh namespace: `community.general`, `ansible.posix`. |
| **Idempotency** | Sifat operasi di mana eksekusi berulang kali dengan konfigurasi yang sama akan menghasilkan *state* akhir yang konsisten tanpa efek samping tambahan jika state target sudah tercapai. | Task yang sudah memenuhi state yang diminta akan menghasilkan status `ok` (bukan `changed`). |
| **FQCN** | *Fully Qualified Collection Name*: format penamaan kanonikal lengkap untuk modul atau plugin (`<namespace>.<collection>.<plugin>`). | Contoh: `ansible.builtin.copy`, `ansible.builtin.template`, `community.docker.docker_container`. Standar wajib sejak migrasi ke collections. |
| **Fact** | Data dan informasi spesifik mengenai kondisi sistem managed node (distro OS, IP, RAM, disk, hostname) yang dikumpulkan secara otomatis. | Diambil pada awal play via modul `ansible.builtin.setup` dan disimpan dalam dictionary variabel `ansible_facts`. |
| **Ad-hoc Command** | Perintah baris tunggal menggunakan CLI `ansible` untuk menjalankan satu modul pada managed nodes tanpa membuat playbook. | Sangat berguna untuk operasi cepat seperti `ping`, reboot server, atau cek uptime. |
| **Magic Variables** | Variabel bawaan yang disediakan otomatis oleh Ansible saat runtime tanpa perlu didefinisikan manual. | Contoh: `hostvars`, `group_names`, `groups`, `inventory_hostname`, `play_hosts`. |
| **Ansible Vault** | Fitur enkripsi bawaan berbasis AES-256 untuk mengamankan data sensitif seperti password, API key, dan sertifikat SSL. | Mendukung enkripsi file penuh (`ansible-vault encrypt`) maupun enkripsi string tunggal (`ansible-vault encrypt_string`). |
