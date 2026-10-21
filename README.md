# Aplikasi Iuran RT 01 — Build APK melalui GitHub

Proyek ini membungkus file HTML aplikasi Iuran RT 01 menjadi aplikasi Android menggunakan Capacitor dan GitHub Actions.

## Isi proyek
- `www/index.html` — file HTML aplikasi asli, dipertahankan.
- `icon-iuran-rt01.png` — gambar ikon asli yang dikirim.
- `resources/icon.png` — ikon 1024×1024 yang digunakan saat membuat ikon launcher Android.
- `.github/workflows/build-apk.yml` — alur otomatis untuk membuat APK debug.
- `capacitor.config.ts` — nama dan ID aplikasi Android.

## Cara membuat APK melalui GitHub
1. Masuk ke GitHub dan buat repository baru, misalnya `iuran-rt01-apk`.
2. Unggah **isi folder proyek ini** ke repository (file harus berada di root repository; jangan hanya mengunggah file ZIP).
3. Pastikan branch bernama `main`.
4. Buka tab **Actions**. Jika diminta, izinkan Actions untuk repository.
5. Pilih workflow **Build APK Iuran RT 01**, lalu klik **Run workflow**. Workflow juga berjalan otomatis saat ada push ke `main`.
6. Setelah selesai dengan status hijau, buka hasil run workflow, bagian **Artifacts**, lalu unduh `Iuran-RT-01-APK`.
7. Ekstrak ZIP artifact tersebut. File di dalamnya bernama `app-debug.apk`; salin ke HP Android dan instal. Jika Android meminta izin, izinkan instalasi aplikasi dari sumber tersebut.

## Ikon APK
Workflow menggunakan `resources/icon.png` untuk menghasilkan resource ikon Android melalui Capacitor Assets sebelum APK dibangun. Ikon aplikasi di layar utama Android akan memakai gambar Iuran RT 01 yang dikirim.

## Catatan Firebase
HTML sumber tetap memakai konfigurasi Firebase yang sudah ada di file. Untuk login dan sinkronisasi, HP harus memiliki internet dan domain/config/rules Firebase harus tetap benar. APK ini membungkus HTML; bukan migrasi database atau perubahan Firebase.

## Batasan
- APK yang dibuat GitHub Actions adalah **debug APK**, bukan APK rilis yang ditandatangani untuk distribusi resmi.
- Tidak perlu memasukkan password atau kunci signing ke repository untuk debug APK.
