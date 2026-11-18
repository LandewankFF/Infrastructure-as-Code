# Modul Manajemen Kontainer (community.docker)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Koleksi `community.docker` menyediakan seperangkat modul lengkap untuk mengelola Docker Engine, images, containers, networks, dan volumes secara deklaratif. Modul `community.docker.docker_image` digunakan untuk mem-pull atau membangun Docker image baru di remote host. Modul `community.docker.docker_container` adalah modul inti untuk menjalankan, menghentikan, mengatur port mapping, bind mounts volume, environment variables, dan restart policy sebuah container. Modul ini menjamin idempotency di mana container hanya akan dibuat ulang jika terdapat perbedaan parameter konfigurasi atau image tag yang baru.

## Contoh singkat
```yaml
- name: Menjalankan container Nginx dengan port mapping
  community.docker.docker_container:
    name: web_service
    image: nginx:alpine
    state: started
    ports:
      - "80:80"
    restart_policy: always
```

## Referensi resmi
- [community.docker collection](https://docs.ansible.com/ansible/latest/collections/community/docker/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
