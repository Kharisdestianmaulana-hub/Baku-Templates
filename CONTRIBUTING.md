# Panduan Kontribusi Berkas Templat Baku PDF

Terima kasih atas ketertarikan Anda untuk menyumbangkan format templat kampus atau institusi Anda ke ekosistem **Baku PDF**!

---

## 🛠 Langkah-langkah Pengajuan Templat Baru

### 1. Buat Format di Aplikasi Baku PDF
1. Buka aplikasi desktop **Baku PDF**.
2. Atur tata letak dokumen sesuai buku pedoman resmi kampus Anda (ukuran kertas, margin, jenis font, nomor halaman Romawi/Arab, sampul judul, lembar pengesahan, dan struktur bab).
3. Klik menu **File** &rarr; **Simpan Sebagai Templat**, atau simpan naskah lalu ambil berkas `.baku`-nya dari folder `Baku Workspace/Templates`.

### 2. Fork & Clone Repositori
1. Klik tombol **Fork** di pojok kanan atas repositori [Kharisdestianmaulana-hub/Baku-Templates](https://github.com/Kharisdestianmaulana-hub/Baku-Templates).
2. Clone hasil fork ke komputer lokal Anda:
   ```bash
   git clone https://github.com/<username-anda>/Baku-Templates.git
   cd Baku-Templates
   ```
3. Buat branch baru:
   ```bash
   git checkout -b template/skripsi-<nama-kampus>
   ```

### 3. Tambahkan Berkas .baku & Daftarkan di registry.json
1. Salin berkas `.baku` Anda ke dalam direktori `templates/`:
   ```bash
   cp ~/Downloads/Skripsi_Format_Kampus.baku templates/Skripsi_<Nama_Kampus>.baku
   ```
2. Buka berkas `registry.json`, lalu tambahkan entri baru di bagian bawah array:
   ```json
   {
     "id": "skripsi-<slug-kampus>",
     "title": "Skripsi <Nama Kampus Lengkap>",
     "campus": "<Nama Kampus / Institusi>",
     "category": "akademik",
     "author": "@username_github",
     "isOfficial": false,
     "fileName": "Skripsi_<Nama_Kampus>.baku",
     "paperSize": "A4",
     "marginSummary": "4-4-3-3 cm",
     "fontSummary": "Times New Roman, 12pt, Spasi 1.5",
     "description": "Format skripsi Program Sarjana (S1) sesuai pedoman akademik resmi tahun 2025/2026.",
     "downloadUrl": "https://raw.githubusercontent.com/Kharisdestianmaulana-hub/Baku-Templates/main/templates/Skripsi_<Nama_Kampus>.baku",
     "lastUpdated": "2026-10-21"
   }
   ```

### 4. Kirimkan Pull Request (PR)
1. Commit perubahan Anda:
   ```bash
   git add templates/ registry.json
   git commit -m "feat(template): tambahkan templat skripsi <Nama Kampus>"
   git push origin template/skripsi-<nama-kampus>
   ```
2. Buka GitHub, lalu buat **Pull Request** ke branch `main` repositori upstream dengan format judul:
   `[New Template]: Skripsi <Nama Kampus> by @username`
3. Tim kurator akan memeriksa struktur JSON berkas `.baku` Anda. Jika sudah sesuai standar, PR akan di-merge dan templat otomatis tayang di web [bakupdf.tech/templates](https://bakupdf.tech/templates)!

---

## 📋 Syarat & Ketentuan Format .baku
- **Integritas Berkas**: Berkas `.baku` harus berupa JSON valid yang diekspor langsung dari aplikasi Baku PDF.
- **Bebas Data Sensitif**: Pastikan tidak ada data pribadi rahasia (seperti NIK, nomor telepon pribadi, atau informasi rahasia kampus) di dalam contoh teks naskah. Gunakan nama contoh fiktif (misal: *Nama Mahasiswa*, *NIM: 12345678*).
- **Lisensi**: Seluruh templat yang diajukan bersedia dilisensikan di bawah lisensi terbuka MIT License agar bermanfaat bagi sesama mahasiswa.
