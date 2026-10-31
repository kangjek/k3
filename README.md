# Pasang di GitHub Pages (5 langkah)

Halaman depan ada di GitHub Pages, data tetap di Google Sheet lewat Apps Script.
Kamera QR langsung pasti diizinkan karena halaman tidak lagi di dalam iframe Google.

1. **Perbarui Apps Script.** Tempel `Code.gs` yang baru (ada tambahan `doPost`), lalu
   Deploy > Manage deployments > edit > Version: New version > Deploy.
   Pengaturan tetap: Execute as **Me**, Who has access **Anyone**.
2. **Buat repository GitHub.** github.com > New repository, nama misalnya `k3`, pilih **Public**
   (Pages gratis butuh repo publik). Data TIDAK ada di repo, hanya halaman dan alamat API.
3. **Upload `index.html` dan `config.js`** ke root repo (Add file > Upload files > Commit).
4. **Aktifkan Pages.** Settings > Pages > Source: *Deploy from a branch* > Branch `main` / folder `/ (root)` > Save.
   Tunggu 1-2 menit. Alamatnya: `https://NAMAANDA.github.io/k3/`
5. **Isi dua alamat:**
   - `config.js` di GitHub (ikon pensil): ganti `ISI_DI_SINI` agar `K3_API` berisi alamat `/exec` Apps Script.
   - Google Sheet, sheet `Config`, sel `Base_URL`: isi alamat Pages di atas **sebelum** membuka `/exec`.
     (Jika `/exec` sudah terlanjur dibuka dan Base_URL terisi `/exec`, timpa saja dengan alamat Pages.)
     Setelah itu cetak ulang QR dari Admin > Alat dan QR.

Uji: buka alamat Pages di HP > masuk NIK > tab Scan > kamera menyala.

Catatan
- Memperbarui halaman: upload `index.html` baru (menimpa), lalu muat ulang dengan tarik-turun beberapa kali.
- Karena repo publik dan login hanya NIK, pasang PIN untuk karyawan (menu K3 > Atur PIN karyawan).
- QR lama yang berisi alamat `/exec` tetap jalan (versi Apps Script tidak dihapus), tapi kamera langsung hanya di versi Pages.
