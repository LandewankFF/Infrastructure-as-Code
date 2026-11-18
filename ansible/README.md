# Ansible Learning Repository & Hands-on Labs

Repositori ini adalah panduan komprehensif, catatan teori, dan laboratorium praktek terstruktur untuk mempelajari **Infrastructure as Code (IaC)** menggunakan **Ansible** (berbasis `ansible-core 2.16`).

---

## 🎯 Tujuan Repositori

1. **Pemahaman Teoretis Mendalam**: Memahami arsitektur *agentless*, prinsip idempotensi, orkestrasi playbook, manajemen konfigurasi, dan best practices Ansible tingkat produksi.
2. **Hands-on Lab Terarah**: Menguji dan menerapkan teori secara langsung melalui skenario lab mandiri (*learning by doing*) tanpa melihat jawaban siap pakai.
3. **Penyimpanan Pemahaman Mandiri**: Menyediakan kerangka catatan yang rapi untuk mencatat hasil eksplorasi video/buku, temuan langsung, serta pemecahan masalah (*troubleshooting*).

---

## 📂 Cara Menggunakan Repositori

Struktur repositori ini mengadopsi model **mirroring** antara teori (`notes/`) dan praktek (`labs/`):

- **Folder `notes/`**: Berisi rangkuman materi per modul topik. Di setiap file catatan terdapat template kosong (`Pemahaman saya`, `Hasil praktek`, `Error yang ditemui & solusinya`, `Pertanyaan / belum paham`) yang dapat Anda isi sesuai proses belajar Anda.
- **Folder `labs/`**: Berisi instruksi laboratorium, file *starter* minimal, kriteria keberhasilan (*checklist*), dan file `HASIL.md` sebagai log eksekusi Anda.
- **Folder `cheatsheets/`**: Kumpulan tabel ringkas untuk sintaks YAML, perintah CLI, dan filter Jinja2.
- **File `glossary.md`**: Glosarium istilah inti Ansible untuk referensi cepat.

---

## 🗺️ Roadmap Modul Belajar

| Modul | Topik Utama | Catatan Teori | Hands-on Labs | Status |
| :---: | :--- | :---: | :---: | :---: |
| **00** | Fundamental & Arsitektur | [notes/00-fundamental](notes/00-fundamental/README.md) | [labs/00-fundamental](../labs/00-fundamental/) | 🔄 Siap |
| **01** | Inventory & Grouping | [notes/01-inventory](notes/01-inventory/README.md) | [labs/01-inventory](../labs/01-inventory/) | 🔄 Siap |
| **02** | Command Line Tools | [notes/02-command-line-tools](notes/02-command-line-tools/README.md) | [labs/02-command-line-tools](../labs/02-command-line-tools/) | 🔄 Siap |
| **03** | Playbooks & Tasks | [notes/03-playbooks](notes/03-playbooks/README.md) | [labs/03-playbooks](../labs/03-playbooks/) | 🔄 Siap |
| **04** | Variables & Facts | [notes/04-variables-facts](notes/04-variables-facts/README.md) | [labs/04-variables-facts](../labs/04-variables-facts/) | 🔄 Siap |
| **05** | Templates & Jinja2 | [notes/05-templates-jinja2](notes/05-templates-jinja2/README.md) | [labs/05-templates-jinja2](../labs/05-templates-jinja2/) | 🔄 Siap |
| **06** | Control Flow & Error Handling | [notes/06-control-flow-error-handling](notes/06-control-flow-error-handling/README.md) | [labs/06-control-flow-error-handling](../labs/06-control-flow-error-handling/) | 🔄 Siap |
| **07** | Roles & Modularisasi | [notes/07-roles](notes/07-roles/README.md) | [labs/07-roles](../labs/07-roles/) | 🔄 Siap |
| **08** | Collections & Galaxy | [notes/08-collections-galaxy](notes/08-collections-galaxy/README.md) | [labs/08-collections-galaxy](../labs/08-collections-galaxy/) | 🔄 Siap |
| **09** | Vault & Keamanan Rahasia | [notes/09-vault](notes/09-vault/README.md) | [labs/09-vault](../labs/09-vault/) | 🔄 Siap |
| **10** | Modul-Modul Umum | [notes/10-modules-umum](notes/10-modules-umum/README.md) | [labs/10-modules-umum](../labs/10-modules-umum/) | 🔄 Siap |
| **11** | Windows, Network & Cloud | [notes/11-windows-network-cloud](notes/11-windows-network-cloud/README.md) | *(Topik Lanjutan)* | 🔄 Siap |
| **12** | Testing & Code Quality | [notes/12-testing-quality](notes/12-testing-quality/README.md) | [labs/12-testing-quality](../labs/12-testing-quality/) | 🔄 Siap |
| **13** | CI/CD, AWX & EE | [notes/13-cicd-awx-ee](notes/13-cicd-awx-ee/README.md) | [labs/13-cicd-awx-ee](../labs/13-cicd-awx-ee/) | 🔄 Siap |
| **14** | Troubleshooting & Best Practices | [notes/14-troubleshooting-best-practice](notes/14-troubleshooting-best-practice/README.md) | *(Best Practices)* | 🔄 Siap |
| **Projects** | Real-World Projects (p1 - p5) | *(Diterapkan dari Notes)* | [labs/projects](../labs/projects/) | 🔄 Siap |

---

## 🧭 Urutan Belajar yang Disarankan

Untuk mendapatkan kurva belajar DevOps engineer yang paling efektif, disarankan mengikuti alur 4 fase berikut:

```
[ Fase 1: Fondasi Inti (Core) ]
00-fundamental ➔ 01-inventory ➔ 02-command-line-tools ➔ 03-playbooks ➔ 04-variables-facts
➔ 05-templates-jinja2 ➔ 06-control-flow-error-handling ➔ 07-roles ➔ 09-vault ➔ 10-modules-umum ➔ 08-collections-galaxy
                                    │
                                    ▼
[ Fase 2: Kualitas & Delivery Enterprise ]
12-testing-quality ➔ 13-cicd-awx-ee ➔ 14-troubleshooting-best-practice
                                    │
                                    ▼
[ Fase 3: Domain Khusus (Sesuai Kebutuhan) ]
11-windows-network-cloud (Windows / Network / Cloud / Kubernetes)
                                    │
                                    ▼
[ Fase 4: Proyek Nyata (Capstone Projects) ]
p1-baseline-server ➔ p2-lemp-stack ➔ p3-rolling-deploy ➔ p4-docker-monitoring ➔ p5-cicd-pipeline
```

---

## 🛠️ Lingkungan Lokal

- **Ansible Version**: `ansible-core 2.16.x`
- **Python**: `Python 3.12.x`
- **OS**: Ubuntu Linux (Control Node)
