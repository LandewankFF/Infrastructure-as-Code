# Urutan Eksekusi Task: pre_tasks, tasks, post_tasks

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Ansible memiliki siklus hidup eksekusi play yang teratur dan terprediksi untuk memfasilitasi kebutuhan orkestrasi kompleks. Urutan eksekusi dimulai dari pengumpulan fakta (`gather_facts`), dilanjutkan dengan blok `pre_tasks`. Jika ada handler yang dinotifikasi oleh `pre_tasks`, handler tersebut dapat dipanggil sebelum melanjutkan ke daftar `roles` atau `tasks` utama. Setelah seluruh task utama selesai, Ansible akan menjalankan `post_tasks`, dan terakhir mengeksekusi sisa handlers yang belum terpicu. Pola ini sangat krusial dalam skenario deployment bertahap, misalnya melepaskan node dari load balancer pada `pre_tasks` dan mendaftarkannya kembali pada `post_tasks`.

## Contoh singkat
```yaml
---
- name: Siklus Deployment Lengkap
  hosts: webservers
  pre_tasks:
    - name: Lepaskan server dari load balancer
      ansible.builtin.debug:
        msg: "Drain traffic..."
  tasks:
    - name: Deploy aplikasi versi baru
      ansible.builtin.debug:
        msg: "Mengupdate kode..."
  post_tasks:
    - name: Hubungkan kembali server ke load balancer
      ansible.builtin.debug:
        msg: "Enable traffic..."
```

## Referensi resmi
- [Playbook Keywords](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
