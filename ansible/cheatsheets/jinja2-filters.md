# Cheatsheet: Jinja2 Filters di Ansible

Filter Jinja2 digunakan untuk memanipulasi, memformat, dan mengekstrak data dari variabel di dalam template maupun playbook task.

Sintaks dasar: `{{ variable | filter_name(argumen) }}`

---

## 1. Filter Penanganan Nilai Kosong & Tipe Data

| Filter | Fungsi | Contoh Penggunaan | Hasil / Contoh Output |
| :--- | :--- | :--- | :--- |
| `default(val)` | Memberikan nilai fallback jika variabel belum didefinisikan. | `{{ db_port | default(3306) }}` | `3306` (jika `db_port` undefined) |
| `default(val, true)` | Memberikan fallback jika variabel undefined ATAU bernilai kosong/false. | `{{ custom_name | default('admin', true) }}` | `'admin'` jika string kosong `""` |
| `bool` | Mengonversi string/angka menjadi boolean murni Python (`True`/`False`). | `{{ 'yes' | bool }}` | `True` |
| `int` | Mengonversi nilai menjadi integer. | `{{ '8080' | int }}` | `8080` |
| `type_debug` | Menampilkan tipe data Python dari variabel (sangat berguna untuk debugging). | `{{ my_var | type_debug }}` | `str`, `list`, `dict`, dsb. |

---

## 2. Filter Format JSON & YAML

| Filter | Fungsi | Contoh Penggunaan |
| :--- | :--- | :--- |
| `to_json` | Mengonversi dictionary/list menjadi format string JSON. | `{{ server_config | to_json }}` |
| `to_nice_json` | Mengonversi menjadi string JSON terindentasi rapi (pretty-print). | `{{ server_config | to_nice_json(indent=2) }}` |
| `from_json` | Mengurai (*parse*) string JSON menjadi struktur data Python (dict/list). | `{{ raw_json_string | from_json }}` |
| `to_yaml` | Mengonversi struktur data menjadi string YAML. | `{{ my_data | to_yaml }}` |
| `to_nice_yaml` | Mengonversi menjadi format YAML terindentasi rapi. | `{{ my_data | to_nice_yaml(indent=2) }}` |
| `from_yaml` | Mengurai string YAML menjadi objek Python. | `{{ raw_yaml_string | from_yaml }}` |

---

## 3. Filter List & Dictionary

| Filter | Fungsi | Contoh Penggunaan |
| :--- | :--- | :--- |
| `join(separator)` | Menggabungkan elemen list menjadi satu string dipisahkan delimiter. | `{{ ['10.0.0.1', '10.0.0.2'] | join(',') }}` -> `'10.0.0.1,10.0.0.2'` |
| `split(separator)` | Memecah string menjadi list berdasarkan separator. | `{{ 'a,b,c' | split(',') }}` -> `['a', 'b', 'c']` |
| `map(attribute)` | Mengekstrak satu atribut tertentu dari list of dictionaries. | `{{ users | map(attribute='name') | list }}` |
| `selectattr(attr, test)` | Menyaring list of dicts yang memenuhi kondisi tertentu. | `{{ vms | selectattr('status', 'equalto', 'running') | list }}` |
| `combine(dict2)` | Menggabungkan (*merge*) dua atau lebih dictionary. | `{{ default_cfg | combine(custom_cfg) }}` |
| `unique` | Menghilangkan duplikat elemen dari dalam list. | `{{ [1, 2, 2, 3] | unique | list }}` -> `[1, 2, 3]` |
| `flatten` | Meratakan nested list menjadi satu level list. | `{{ [1, [2, 3]] | flatten }}` -> `[1, 2, 3]` |
| `difference(list2)` | Mengembalikan elemen list1 yang tidak ada di list2 (set subtraction). | `{{ [1, 2, 3] | difference([2]) }}` -> `[1, 3]` |

---

## 4. Filter String & Path

| Filter | Fungsi | Contoh Penggunaan |
| :--- | :--- | :--- |
| `regex_replace` | Mengganti string berdasarkan pola RegEx. | `{{ 'v1.2.3' | regex_replace('^v', '') }}` -> `'1.2.3'` |
| `regex_search` | Mengekstrak substring yang cocok dengan RegEx. | `{{ version_str | regex_search('[0-9]+\\.[0-9]+') }}` |
| `b64encode` | Melakukan encode string ke format Base64. | `{{ 'secret_pass' | b64encode }}` |
| `b64decode` | Melakukan decode string dari format Base64. | `{{ encoded_val | b64decode }}` |
| `basename` | Mengambil nama file dari path lengkap. | `{{ '/etc/nginx/nginx.conf' | basename }}` -> `'nginx.conf'` |
| `dirname` | Mengambil nama direktori dari path lengkap. | `{{ '/etc/nginx/nginx.conf' | dirname }}` -> `'/etc/nginx'` |
| `expanduser` | Mengekspansi tanda tilde `~` menjadi direktori home pengguna. | `{{ '~/backup' | expanduser }}` |

---

## 5. Filter Networking (`ansible.utils`)

*Catatan: Memerlukan collection `ansible.utils` dan library Python `netaddr`.*

| Filter | Fungsi | Contoh Penggunaan |
| :--- | :--- | :--- |
| `ansible.utils.ipaddr('address')` | Memvalidasi apakah string merupakan alamat IP yang valid. | `{{ my_ip | ansible.utils.ipaddr('address') }}` |
| `ansible.utils.ipaddr('net')` | Mengambil network address dari CIDR. | `{{ '192.168.1.50/24' | ansible.utils.ipaddr('net') }}` -> `'192.168.1.0/24'` |
| `ansible.utils.ipaddr('netmask')` | Mengambil netmask dari CIDR. | `{{ '192.168.1.50/24' | ansible.utils.ipaddr('netmask') }}` -> `'255.255.255.0'` |
