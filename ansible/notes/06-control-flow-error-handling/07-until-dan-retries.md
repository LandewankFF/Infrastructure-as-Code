# Polling Status dengan until, retries, dan delay

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Mekanisme polling retry di Ansible digunakan untuk menunggu hingga suatu kondisi terpenuhi dengan cara mengulang eksekusi suatu task secara berkala. Keyword `until` mendefinisikan kondisi keberhasilan (berbasis ekspresi Jinja2) yang harus dipenuhi sebelum loop retry dihentikan. Keyword `retries` menentukan jumlah maksimum percobaan ulang sebelum task dianggap gagal total (default 3 kali), dan `delay` menentukan waktu tunggu jeda (dalam detik) di antara setiap percobaan eksekusi. Fitur ini sangat umum digunakan untuk menunggu port service terbuka setelah server direboot, menunggu container Docker berstatus healthy, atau menunggu respon API eksternal.

## Contoh singkat
```yaml
- name: Menunggu service API merespon HTTP 200
  ansible.builtin.uri:
    url: http://localhost:8080/health
    status_code: 200
  register: api_result
  until: api_result.status == 200
  retries: 10
  delay: 5
```

## Referensi resmi
- [Retrying a task until a condition is met](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_loops.html#retrying-a-task-until-a-condition-is-met)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
