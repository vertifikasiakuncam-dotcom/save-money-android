# SAVE MONEY — Android prototype 0.1.0

Aplikasi Android prototipe untuk mencatat tabungan keluarga. Dibangun sebagai Android WebView yang memuat aset HTML lokal; tidak membutuhkan izin internet.

## Fitur tahap pertama
- Saldo dari catatan uang masuk dan keluar
- Target tabungan dan alokasi catatan ke target
- Riwayat transaksi
- Ekspor/impor cadangan JSON
- Halaman QRIS sebagai placeholder, bukan QRIS pembayaran nyata

## Penting
Data saat ini disimpan pada localStorage di perangkat dan tidak disinkronkan. Saldo adalah catatan manual, bukan uang elektronik atau saldo bank. Jangan gunakan untuk menyimpan uang sungguhan, PIN, OTP, atau informasi bank. QRIS nyata memerlukan mitra resmi, API backend, verifikasi webhook, rekonsiliasi, dan persetujuan kepatuhan yang sesuai.

## Cara mendapatkan APK gratis melalui GitHub Actions
1. Buat repository GitHub baru bernama `save-money-android`.
2. Unggah semua isi folder proyek ini ke root repository, termasuk folder `.github`.
3. Buka tab **Actions** dan pilih **Build SAVE MONEY APK**.
4. Tekan **Run workflow** (atau tunggu workflow berjalan setelah push).
5. Setelah selesai, buka hasil workflow dan unduh artifact **save-money-debug-apk**.
6. Ekstrak ZIP artifact, lalu pindahkan `app-debug.apk` ke HP Android dan instal. Android mungkin meminta izin untuk memasang aplikasi dari sumber tersebut.

## Build lokal
Memerlukan JDK 17 dan Gradle 8.9 serta Android SDK platform 35. Jalankan `gradle assembleDebug` dari root proyek.

## Struktur
- `app/src/main/java/.../MainActivity.kt`: Android WebView activity
- `app/src/main/assets/index.html`: UI dan fungsi prototipe
- `.github/workflows/build-apk.yml`: build APK otomatis
