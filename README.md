# 🚀 Roadmap Belajar Frappe + ERPNext (Developer Path)

---

### 🔰 Tahap 1: Dasar-Dasar Frappe & ERPNext

#### 🎯 Tujuan:

* Memahami arsitektur Frappe
* Familiar dengan ERPNext dan antarmukanya

#### ✅ Checklist:

* [ ] Install **Frappe Framework** & **ERPNext** secara lokal
  → Gunakan [frappe-bench](https://frappeframework.com/docs/v14/user/en/installation)

  * `bench init`
  * `bench new-site`
  * `bench get-app erpnext`
  * `bench install-app erpnext`
* [ ] Coba akses `http://localhost:8000` dan login ke ERPNext
* [ ] Pahami DocType (struktur data utama)
* [ ] Pelajari hubungan antara:

  * **App > Module > DocType > Field**

📚 Referensi:

* [Frappe Docs - Introduction](https://frappeframework.com/docs)
* [ERPNext Docs](https://docs.erpnext.com)

---

### ⚙️ Tahap 2: Membuat Aplikasi Custom

#### 🎯 Tujuan:

* Bisa membuat aplikasi sendiri dengan Frappe

#### ✅ Checklist:

* [ ] Buat App: `bench new-app nama_app`
* [ ] Install ke site: `bench --site mysite install-app nama_app`
* [ ] Buat Module dan DocType dari UI (Desk) atau dari file Python
* [ ] Pelajari cara insert/update data:

  * `frappe.get_doc().insert()`
  * `frappe.db.set_value()`
* [ ] Pahami bagaimana data disimpan ke MariaDB

📚 Praktik:

* Buat app **Manajemen Proyek Internal** atau **Tugas Harian**

---

### 🎯 Tahap 3: Validasi, Automation, dan Hook

#### ✅ Checklist:

* [ ] Pelajari `validate()`, `before_save()`, `on_submit()` dalam class Doctype
* [ ] Tambahkan validasi manual dengan Python
* [ ] Gunakan `hooks.py` untuk:

  * Custom scripts
  * Events (server-side)
* [ ] Buat custom method `@frappe.whitelist()` dan akses via API

📚 Referensi:

* [https://frappeframework.com/docs/v14/user/en/hooks](https://frappeframework.com/docs/v14/user/en/hooks)
* [https://frappeframework.com/docs/v14/user/en/python-api](https://frappeframework.com/docs/v14/user/en/python-api)

---

### 🖥️ Tahap 4: Client Script & Frontend

#### ✅ Checklist:

* [ ] Pelajari `Client Script` untuk menambahkan logika JS ke form
* [ ] Gunakan `frappe.msgprint`, `frappe.call`, `frappe.ui.form`
* [ ] Buat halaman Web Page dan Web Form jika perlu frontend publik

📚 Referensi:

* [https://frappeframework.com/docs/v14/user/en/client-script](https://frappeframework.com/docs/v14/user/en/client-script)
* [https://frappeframework.com/docs/v14/user/en/web-forms](https://frappeframework.com/docs/v14/user/en/web-forms)

---

### 📦 Tahap 5: Fixtures & Migrasi Data

#### ✅ Checklist:

* [ ] Pelajari konsep **Fixtures** (`bench export-fixtures`)
* [ ] Pelajari penggunaan `patches.txt` untuk script migrasi
* [ ] Pelajari `after_install`, `before_install` hooks

📚 Referensi:

* [https://frappeframework.com/docs/v14/user/en/fixtures](https://frappeframework.com/docs/v14/user/en/fixtures)

---

### 🔐 Tahap 6: Permissions & Security

#### ✅ Checklist:

* [ ] Pahami Role, Role Profile, dan User Permissions
* [ ] Buat aturan akses field (Read, Write, Create, Submit)
* [ ] Pelajari permission level pada DocType dan script

---

### 🌐 Tahap 7: REST API & Integrasi

#### ✅ Checklist:

* [ ] Pelajari cara akses API bawaan Frappe (GET/POST)
* [ ] Buat custom endpoint menggunakan `@frappe.whitelist`
* [ ] Konsumsi API dari luar (Postman / aplikasi lain)

📚 Referensi:

* [https://frappeframework.com/docs/v14/user/en/rest-api](https://frappeframework.com/docs/v14/user/en/rest-api)

---

### 🚀 Tahap 8: Deployment ke Production

#### ✅ Checklist:

* [ ] Setup Frappe + ERPNext di server (VPS / Cloud)
* [ ] Gunakan:

  * **Supervisor**
  * **Nginx**
  * **MariaDB**
* [ ] Gunakan `bench setup production` dan `bench setup nginx`
* [ ] Pelajari backup: `bench backup` dan restore: `bench restore`

📚 Referensi:

* [Production Deployment Guide (Frappe)](https://frappeframework.com/docs/v14/user/en/production-setup)

---

### 🧪 Tahap 9: Testing

#### ✅ Checklist:

* [ ] Pelajari testing dengan `frappe.test_runner`
* [ ] Gunakan `unittest` / `pytest` untuk unit test
* [ ] Buat test untuk validasi Doctype dan logic

---

### 📅 Tahap 10: Project Mini & Portofolio

#### 🎯 Tujuan:

* Menggabungkan semua skill menjadi satu project nyata

#### Ide Project:

* **Aplikasi CRM Sederhana**
* **Sistem Absensi Karyawan**
* **Sistem Booking Studio / Ruangan**
* **Aplikasi POS Sederhana**

---

## 📌 Tips Tambahan:

* Gunakan **Git** dari awal
* Gunakan **Docker** jika kamu ingin fleksibilitas
* Belajar dari **Frappe Academy** (gratis): [academy.frappe.io](https://academy.frappe.io)
* Join komunitas Frappe / ERPNext Indonesia (Telegram / Discord)
