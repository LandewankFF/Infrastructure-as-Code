# Aturan Prioritas Variabel (Variable Precedence)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Ketika sebuah nama variabel yang sama didefinisikan di lebih dari satu tempat, Ansible menyelesaikan konflik tersebut menggunakan aturan prioritas berjenjang (variable precedence). Terdapat 22 tingkatan prioritas di Ansible; secara garis besar, `role defaults` memiliki prioritas paling rendah (mudah ditimpa), diikuti oleh variabel inventory grup dan host, variabel play (`vars`), variabel task, `set_fact`, dan prioritas tertinggi dipegang oleh extra variables (`-e` pada CLI). Memahami urutan ini mencegah bug di mana variabel yang Anda ubah di inventory tidak berefek karena tertimpa oleh variabel di level yang lebih tinggi. Aturan umum: gunakan `role defaults` untuk nilai bawaan dan gunakan `extra vars` jika ingin memaksakan nilai dari luar.

## Contoh singkat
```bash
# Nilai dari opsi -e akan selalu memenangkan prioritas atas nilai di playbook/inventory
ansible-playbook -i inventory.ini site.yml -e "app_port=9090"
```

## Referensi resmi
- [Understanding variable precedence](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_variables.html#understanding-variable-precedence)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
