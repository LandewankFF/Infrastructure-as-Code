# Pengenalan AWX & Ansible Automation Platform (AAP)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
AWX adalah proyek open-source upstream dari Red Hat Ansible Automation Platform (AAP) yang menyediakan antarmuka grafis web (Web UI), REST API terpusat, dan kontrol akses berbasis peran (RBAC) untuk mengelola automasi Ansible di tingkat organisasi. AWX memecahkan tantangan eksekusi Ansible dari laptop individual dengan menyediakan penjadwalan job terpusat, audit log riwayat eksekusi, manajemen credential aman tanpa perlu membagikan SSH key ke developer, serta fitur Job Template dan Visual Workflow DAG. Melalui AWX, tim operasional dapat mendelegasikan tombol eksekusi playbook kepada tim non-DevOps secara aman.

## Contoh singkat
```yaml
# Konsep deklarasi Job Template di AWX via API atau IaC
job_template:
  name: "Deploy Production Web"
  playbook: "site.yml"
  inventory: "Production Inventory"
  credentials: ["Vault-Key", "SSH-Prod-Key"]
```

## Referensi resmi
- [AWX Project](https://github.com/ansible/awx)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
