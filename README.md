# TMAM Android Project

Starter project Android untuk mengelola 20 profil akun dan menyimpan konfigurasi proxy.

## Fitur yang tersedia
- Membuat 20 slot akun secara otomatis saat database kosong.
- Menyimpan konfigurasi proxy HTTP, HTTPS, dan SOCKS5.
- Tes TCP ke host/port proxy.
- Database lokal Room.
- Fondasi enkripsi AES-GCM menggunakan Android Keystore.

## Batasan penting
- Ini adalah pengelola profil dan konfigurasi, bukan aplikasi tunnel VPN.
- Tombol Tes TCP hanya memeriksa keterjangkauan host/port.
- Aplikasi ini belum mengarahkan trafik TikTok melalui proxy.
- HTTPS pada pilihan jenis konfigurasi adalah label konfigurasi; implementasi TLS ke endpoint proxy belum disediakan.
- SOCKS5 dengan autentikasi username/password belum diimplementasikan.
- Mode API otomatis dan backup belum diaktifkan pada starter ini.
- Tidak ada penyimpanan password TikTok.

## Yang baru di 1.1.0
- Edit username & catatan tiap akun (ketuk kartu akun), pilih proxy per akun.
- Cari akun, edit proxy, konfirmasi hapus, validasi port, latensi pada Tes TCP.
- Mode gelap, ikon aplikasi, migrasi database 1 → 2 (data lama aman).
- Workflow GitHub Actions untuk membangun APK otomatis.

## Build APK tanpa Android Studio (GitHub Actions)
1. Buat repositori GitHub baru, unggah seluruh isi folder proyek ini.
2. Buka tab **Actions** > **Build APK** > tunggu hijau.
3. Unduh artifact **TMAM-debug-apk**, ekstrak, pasang `app-debug.apk` di HP.

## Build APK (Android Studio)
1. Instal Android Studio versi stabil yang mendukung Android Gradle Plugin 8.7.3.
2. Instal JDK 17 dan Android SDK Platform 35 melalui SDK Manager.
3. Buka folder TMAM sebagai proyek Android Studio.
4. Tunggu Gradle Sync selesai.
5. Pilih Build > Build Bundle(s) / APK(s) > Build APK(s).
6. APK debug biasanya muncul di `app/build/outputs/apk/debug/app-debug.apk`.
7. Pindahkan APK ke HP Android 12 dan instal. Jika diminta, izinkan instalasi dari sumber tersebut.

## Uji perangkat
Uji di Sharp Aquos Sense4 Plus Android 12:
- Aplikasi terbuka.
- 20 slot tampil.
- Tambah konfigurasi proxy.
- Tes TCP untuk host/port yang memang Anda miliki.
- Tutup dan buka aplikasi kembali; data harus tetap tersimpan.

## Versi
1.1.0 - edit akun, proxy per akun, mode gelap, ikon, CI.
1.0.0 - starter source project.
