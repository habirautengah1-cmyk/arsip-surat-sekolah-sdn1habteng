# 📁 ArsipSekolah - Sistem Informasi Kearsipan Digital

Sistem manajemen arsip surat masuk dan keluar berbasis web untuk sekolah/instansi, 
dibangun dengan Google Apps Script dan Google Sheets sebagai backend.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Platform](https://img.shields.io/badge/platform-Google%20Apps%20Script-green)
![License](https://img.shields.io/badge/license-MIT-yellow)

## ✨ Fitur Utama

- **Multi-User Role**: Admin, Kepala Sekolah, Guru
- **Manajemen Surat**: Input surat masuk & keluar dengan upload file PDF/Gambar
- **Sistem Disposisi**: Kepala Sekolah dapat memberikan disposisi pada surat masuk
- **Dashboard Statistik**: Monitoring jumlah surat dan status disposisi
- **Responsive Design**: Tampilan optimal di desktop maupun mobile
- **Role-Based Access Control**: Menu administrator tersembunyi untuk user biasa

## 🚀 Cara Deploy

### Prasyarat
- Akun Google (Gmail/Google Workspace)
- Google Chrome Browser
- Extension: [ clasp ](https://github.com/google/clasp) (opsional, untuk deployment via CLI)

### Metode 1: Deploy Manual (Untuk Pemula)

1. **Buat Google Spreadsheet baru**
   - Buka [sheets.google.com](https://sheets.google.com)
   - Buat spreadsheet kosong, beri nama "ArsipSekolah"

2. **Buka Apps Script**
   - Klik **Extensions &gt; Apps Script**
   - Hapus semua kode default (file `Code.gs`)

3. **Copy Kode**
   - Buat file baru dengan nama `Code.gs`, paste kode dari `src/Code.gs`
   - Buat file baru dengan nama `Index.html`, paste kode dari `src/Index.html`
   - Ganti `FOLDER_ID` di `Code.gs` dengan ID Folder Google Drive Anda

4. **Setup Awal**
   - Pilih fungsi `setupAwal` di dropdown, klik **Run**
   - Izinkan permission yang diminta

5. **Deploy Web App**
   - Klik **Deploy &gt; New deployment**
   - Pilih **Type: Web app**
   - **Execute as**: Me
   - **Who has access**: Anyone (atau sesuai kebutuhan)
   - Klik **Deploy**, salin URLnya

### Metode 2: Deploy dengan Clasp (Rekomended)

```bash
# Install clasp globally
npm install -g @google/clasp

# Login ke Google
clasp login

# Clone project ini (jika sudah ada di GitHub)
git clone https://github.com/username/arsip-sekolah.git
cd arsip-sekolah

# Edit .clasp.json, masukkan Script ID Anda
# Script ID bisa dilihat di URL Apps Script: https://script.google.com/d/{SCRIPT_ID}/edit

# Push ke Apps Script
clasp push

# Deploy
clasp deploy