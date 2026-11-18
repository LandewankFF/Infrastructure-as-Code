# Distribusi Eksekusi: delegate_to, run_once, serial

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Ansible menyediakan keyword khusus untuk mengatur bagaimana dan di mana task dieksekusi dalam skala cluster. `delegate_to` menginstruksikan Ansible untuk menjalankan task tertentu pada node selain target play saat ini (misalnya mendaftarkan IP managed node ke load balancer lokal atau menjalankan task di localhost). `run_once: true` memastikan task hanya dijalankan tepat satu kali di host pertama dalam grup, cocok untuk operasi terpusat seperti database migration. `serial` menentukan ukuran batch (jumlah atau persentase host) yang dieksekusi secara bersamaan dalam sebuah play, menjadi fondasi utama dalam arsitektur rolling deployment tanpa downtime.

## Contoh singkat
```yaml
- name: Rolling Deploy Web Server
  hosts: webservers
  serial: 2
  tasks:
    - name: Catat deployment di monitoring server
      ansible.builtin.uri:
        url: http://monitor.internal/api/deploy
        method: POST
      delegate_to: localhost
      run_once: true
```

## Referensi resmi
- [Playbook Execution Strategies](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_strategies.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
