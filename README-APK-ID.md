# KYZ AI Android APK melalui GitHub Actions

## Isi paket
- `android/`: source project Android berbasis WebView.
- `.github/workflows/android-apk.yml`: workflow untuk build APK otomatis.

## Penting sebelum APK dipakai
APK ini membungkus website KYZ AI yang di-host online. Setelah website/backend KYZ AI berhasil di-deploy, buka:
`android/app/src/main/java/com/kyz/ai/MainActivity.java`
Lalu ganti:
`https://YOUR-APP.onrender.com/`
dengan URL HTTPS Render milik Anda. Ganti juga host `YOUR-APP.onrender.com` di `shouldOverrideUrlLoading` dengan host aplikasi Anda, atau ubah kondisi tersebut agar cocok dengan domain Anda. Commit perubahan itu agar workflow berjalan ulang.

## Tambahkan ke repositori GitHub yang sudah ada
Unggah folder `android` dan folder `.github/workflows` ke root repositori `kyz-ai`. Jangan mengganti atau menghapus file website yang sudah ada.

## Build APK
1. Buka tab **Actions** pada repositori GitHub.
2. Pilih workflow **Build KYZ AI APK**.
3. Klik **Run workflow** → **Run workflow**.
4. Tunggu sampai job berstatus hijau.
5. Buka hasil run dan unduh artifact **KYZ-AI-debug-APK**.
6. Ekstrak ZIP artifact; file `app-debug.apk` ada di dalamnya.
7. Kirim APK ke HP Android, buka file tersebut, dan izinkan pemasangan dari sumber itu jika Android meminta.

APK debug ini untuk uji coba pribadi. Untuk distribusi publik, buat signing/release build dengan kunci penandatanganan yang disimpan sebagai GitHub Secrets. Jangan menyimpan API key AI di source code Android. Backend AI perlu di-host dan API key disimpan sebagai secret pada layanan hosting.
