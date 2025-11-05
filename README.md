## 👤 Profil Mahasiswa

| Atribut         | Keterangan                |
| --------------- | ------------------------- |
| **Nama**        | ferly ardiasnyah          |
| **NIM**         | 312310448                 |
| **Kelas**       | TI.23.A.5                 |
| **Mata Kuliah** | Pemrograman Visual        |

---

# 🏫 Tugas UTS  
# 📘 ardiansyah jaya putra — Deployment & Setup Guide

> Panduan instalasi & konfigurasi aplikasi **ardiasnyah jaya putra**  
> Berbasis **IIS**, **MongoDB**, dan **.NET Framework**

---

## ⚙️ Prasyarat

Pastikan environment kamu sudah memiliki:

- **Windows + IIS (Internet Information Services)**
- **.NET Runtime / Hosting Bundle** (sesuai versi proyek)
- **MongoDB**
- (Opsional) **Git** untuk clone project

---

## 🧩 1. Setup Database MongoDB

1. Pastikan service MongoDB sudah berjalan.  
2. Buka **MongoDB Compass**.  
3. Buat database baru bernama:  
   ```
   ardiansyah jaya putra_db
   ```
4. Buat collection:
   - `pesan`
   - `payment`

5. Masukkan contoh data awal menggunakan fitur **Insert Document** di Compass.

---

## 🖥️ 2. Deploy ke IIS

1. Buka **IIS Manager** di Windows.  
2. Tambahkan **Application Pool** baru:

   | Properti | Nilai |
   |-----------|--------|
   | Name | `ardiasnyah jaya putra` |
   | .NET CLR Version | sesuai proyek (.NET 4.8 atau 6.0) |

3. Tambahkan **Website / Application** baru:  
   - **Physical path**: `C:\inetpub\wwwroot\ardiansyah jaya putra`  
   - **Binding**: `http` — Port `8080`  
   - **Gunakan App Pool**: `ardiansyah jaya putra`

4. Set izin folder melalui **Command Prompt (Administrator):**
   ```bash
   icacls "C:\inetpub\wwwroot\ardiasnyah jaya putra" /grant "IIS AppPool\ardiansyah jaya putra":(OI)(CI)M /T
   ```

5. Jalankan website dan akses di browser:  
   👉 [http://localhost:8080/app#/](http://localhost:8090/app#/)

---

## 💾 3. Backup & Restore

| Jenis | Perintah |
|-------|-----------|
| **MongoDB Backup** | `mongodump --db ardiasnyah jaya putra_db -o C:\backup\` |
| **MongoDB Restore** | `mongorestore --db ardiasnyah jaya putra_db C:\backup\ardiasnyah jaya putra_db` |

---

## ✅ 4. Checklist Deploy

- [x] .NET Hosting Bundle terinstal  
- [x] IIS App Pool & Site aktif (port 8080)  
- [x] Connection string MongoDB sudah benar  
- [x] Folder permission diberikan untuk IIS  
- [x] Aplikasi dapat diakses di `http://localhost:8090/app#/`

---

## 🧭 5. Penjelasan Fungsi Tampilan UI Aplikasi

Berikut penjelasan tampilan antarmuka dari aplikasi **ardiansyah jaya putra**, yang terhubung dengan **MongoDB** dan berjalan pada **IIS**.

---

### 🔐 1. Halaman Login
![Login](Framework XPUPB/WEBSAMPLE/mockup/login.png)

> Digunakan untuk mengautentikasi pengguna sebelum masuk ke sistem.  
> Admin wajib login agar dapat mengelola data data pemesanan sepatu,dan pembayaran.

---

### 🏠 2. Dashboard
![Dashboard](mockup/dashboard.png)

> Menampilkan ringkasan informasi perpustakaan seperti pembayaran, dan data pemesanan.  
> Dari sini admin dapat menavigasi ke menu utama lainnya.

---

### 📚 3. Data pemesanan sepatu
![Data Buku](mockup/databuku.png)

> Berisi daftar pemesanan id,nomer pesanan tanggal pesanan merek sepatu,harga sepatu,dll.  

---

### 👥 4. data pembayaran
![Data Karyawan](mockup/datakaryawan.png)
  
> Saat ini menu ini masih **kosong**, karena belum selesai pada sisi backend.

---

## 🔄 5. Alur Sistem Pustaka Raya

1. **Login** → Akses awal pengguna.  
2. **Dashboard** → Navigasi utama sistem.  
3. **Menampilkan Daftar Sepatu** → Pendataan koleksi sepatu.  
4. **Data Pemesanan Sepatu** → Pelanggan memilih sepatu → menambahkan ke keranjang.  
5. **Pembayaran** → Admin memverifikasi status pembayaran.  


---

## 👥 6. Skema Tim Pengembang

| Nama | Peran | Tanggung Jawab |
|------|-------|----------------|
| **ferly ardiasnyah** | Full Stack Developer | Analisis sistem, desain UI, pembuatan backend, konfigurasi IIS, dan pengujian sistem. |

---

## 🧩 7. Mockup Project

| Halaman | Preview |
|----------|----------|
| Dashboard | ![Dashboard](mockup/dashboard.png) |
| Data pemesann sepatu | ![Data Buku](mockup/databuku.png) |
| Data pembayaran| ![Data Karyawan](mockup/datakaryawan.png) |

---

## 📌 8. Status Proyek Saat Ini

- ✅ Login dan Dashboard sudah berfungsi.  
- ⚠️ Menu **pesan**, **payment**, dan masih dalam tahap perbaikan.  
- 🔧 Proses debugging & pengujian web service sedang dilakukan.  

---

## 🏁 9. Kesimpulan

Sistem **ardiansyah jaya putra** merupakan aplikasi berbasis web yang dirancang untuk mengelola data toko sepatu secara digital.  
Dengan dukungan **IIS**, **MongoDB**, dan **.NET**, sistem ini diharapkan dapat  mempermudah proses penjualan dan pengelolaan data secara digital
Proyek ini menjadi langkah awal menuju digitalisasi layanan yang cepat

---

© 2025 — *Dikembangkan oleh ferly Ardiansyah*
