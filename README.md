# Shalat Quest: cara membuat APK

Folder ini sudah berisi aplikasi (www/), ikon dari logo aplikasi (resources/ dan www/icon-*.png), dan konfigurasi Capacitor.
Ikon APK, ikon aplikasi terinstal, dan logo di dalam aplikasi memakai desain yang sama (mihrab, bulan sabit, bintang, latar tosca).

## Syarat
Node.js 18+, JDK 17, dan Android Studio (untuk Android SDK).

## Langkah
```
npm install
npx cap add android
npx @capacitor/assets generate --android --assetPath resources
npx cap sync android
cd android
./gradlew assembleDebug
```
APK ada di `android/app/build/outputs/apk/debug/app-debug.apk`.

Untuk rilis: buka folder `android` di Android Studio, lalu pilih Build > Generate Signed Bundle / APK.

## Catatan
- Font Arab (Amiri) dimuat dari Google Fonts. Tanpa internet, aplikasi memakai font Arab bawaan HP. Agar font ikut offline, unduh Amiri dan letakkan di www/ lalu tambahkan @font-face.
- Progres belajar tersimpan di penyimpanan lokal aplikasi.

## Cara termudah: lewat GitHub (tanpa memasang apa pun)
1. Buat repository baru di GitHub, lalu unggah seluruh isi folder ini (termasuk folder `.github`).
2. Buka tab **Actions**, pilih **Build APK**, lalu **Run workflow**. Tunggu sekitar 5-10 menit.
3. Buka hasil run yang selesai, lalu unduh **shalat-quest-apk** di bagian Artifacts. Di dalamnya ada `app-debug.apk`.
4. Kirim APK ke HP dan pasang (izinkan pemasangan dari sumber tidak dikenal).
