# Build APK TANPA Android Studio (pakai GitHub, gratis)

Ini paling gampang buat lu: upload project ke GitHub, GitHub yang compile-in
otomatis di server-nya, lu tinggal download APK jadi. Ga perlu instal apa-apa.

## Langkah-langkah

1. **Bikin akun GitHub** (kalau belum punya) di github.com — gratis.

2. **Bikin repo baru**:
   - Klik tombol "+" pojok kanan atas → "New repository"
   - Kasih nama bebas, misal `xmxbats-music-app`
   - Pilih **Private** (biar ga kelihatan orang lain)
   - Klik "Create repository"

3. **Upload semua isi folder ini** (isi folder `xmxbats-android-app`, BUKAN
   folder zip-nya) ke repo tadi:
   - Di halaman repo, klik "uploading an existing file" (atau Add file →
     Upload files)
   - Drag & drop SEMUA isi folder `xmxbats-android-app` (folder `android/`,
     folder `.github/`, folder `web-patch/`, `README.md`) ke situ
   - Kalau GitHub nolak folder `.github` waktu drag manual, upload lewat
     GitHub Desktop app (gratis, tinggal instal, drag folder, klik
     "Publish") — ini lebih gampang buat banyak file sekaligus.
   - Klik "Commit changes"

4. **Tunggu buildnya jalan otomatis**:
   - Klik tab **Actions** di repo lu
   - Bakal ada run namanya "Build APK" lagi jalan (ikon kuning = proses,
     ijo = selesai) — biasanya 3-5 menit

5. **Download APK-nya**:
   - Klik run yang udah selesai (ijo ✅)
   - Scroll ke bawah ke bagian **Artifacts**
   - Klik `xmxbats-music-debug-apk` → otomatis download file .zip berisi
     `app-debug.apk`
   - Extract, pindahin ke HP, install (mungkin perlu izinin "install dari
     sumber tidak dikenal" di HP lu)

## Catatan

- APK ini hasil build **debug** (auto-signed pakai debug key bawaan
  Android), jadi langsung bisa diinstall & ditest — cukup buat pemakaian
  pribadi.
- Kalau nanti mau publish ke Play Store, itu butuh build **release** yang
  di-sign pakai keystore sendiri (beda langkah, bilang aja kalau udah
  sampai situ, gw bantuin bikinin workflow buat itu juga).
- Jangan lupa langkah dari `README.md` sebelumnya (edit `BASE_URL` di
  `MainActivity.kt`, terapin `web-patch/`) SEBELUM upload ke GitHub, biar
  hasil build-nya udah bener.

## Alternatif lain (kalau mau yang interaktif, bukan cuma auto-build)

**Firebase Studio** (studio.firebase.google.com, gratis, dari Google) —
ini kayak Android Studio tapi jalan di browser, ga perlu instal apa-apa,
ada emulator Android juga langsung di browser. Cocok kalau lu mau
edit-edit kode atau test app-nya interaktif, bukan cuma sekali build.
