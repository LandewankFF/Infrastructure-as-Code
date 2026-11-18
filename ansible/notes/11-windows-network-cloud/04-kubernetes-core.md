# Manajemen Kluster Kubernetes (kubernetes.core)

> Status: [ ] Belum  [ ] Sedang dipelajari  [ ] Paham
> Tanggal belajar:
> Sumber (video/artikel):

## Ringkasan materi
Koleksi `kubernetes.core` menyediakan modul untuk mengelola manifes manifest Kubernetes, helm charts, dan resource objek kluster (seperti Deployment, Service, ConfigMap, Ingress) langsung dari Ansible. Menggunakan modul `kubernetes.core.k8s`, Anda dapat mendefinisikan resource Kubernetes baik secara inline YAML di dalam playbook maupun merender file template manifest Jinja2 eksternal. Modul ini berinteraksi dengan Kubernetes API server melalui library Python `kubernetes` menggunakan kredensial `kubeconfig` lokal. Integrasi ini sangat menguntungkan saat Anda perlu mengorkestrasi pipeline aplikasi modern yang melibatkan konfigurasi server VM sekaligus deploy beban kerja container ke Kubernetes.

## Contoh singkat
```yaml
- name: Deploy aplikasi Nginx ke Kubernetes namespace default
  kubernetes.core.k8s:
    state: present
    definition:
      apiVersion: apps/v1
      kind: Deployment
      metadata:
        name: web-deployment
      spec:
        replicas: 2
        selector:
          matchLabels:
            app: web
```

## Referensi resmi
- [kubernetes.core collection](https://docs.ansible.com/ansible/latest/collections/kubernetes/core/index.html)

---
## Pemahaman saya


## Hasil praktek


## Error yang ditemui & solusinya


## Pertanyaan / belum paham
