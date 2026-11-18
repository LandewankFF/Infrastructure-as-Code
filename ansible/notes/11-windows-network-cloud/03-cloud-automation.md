# Automasi Cloud Multi-Provider (AWS, GCP, Azure)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Ansible dapat digunakan sebagai tool provisioning infrastruktur cloud untuk membuat Virtual Machines, VPC, subnet, security group, dan load balancer di provider AWS (`amazon.aws`), Google Cloud (`google.cloud`), dan Microsoft Azure (`azure.azcollection`). Modul-modul cloud ini berkomunikasi dengan API provider menggunakan credential autentikasi (seperti IAM access key atau service account JSON) yang dieksekusi secara lokal di Control Node (`delegate_to: localhost`). Pendekatan ini memungkinkan orkestrasi hibrida yang terpadu: Ansible membuat VM cloud, mendaftarkannya ke inventory dinamis, lalu langsung melakukan konfigurasi aplikasi di dalamnya dalam satu pipeline playbook.

## Contoh singkat
```yaml
- name: Membuat security group di AWS EC2
  amazon.aws.ec2_security_group:
    name: web_secgroup
    description: Allow HTTP and SSH
    region: ap-southeast-1
    rules:
      - proto: tcp
        ports: [80, 22]
        cidr_ip: 0.0.0.0/0
```

## Referensi resmi
- [Ansible Cloud Guide](https://docs.ansible.com/ansible/latest/collections/amazon/aws/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
