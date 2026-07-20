# Panduan Deployment ke Koyeb

Proyek ini telah dikonfigurasi agar mudah di-deploy ke Koyeb menggunakan Docker.

## Persiapan
1. Pastikan Anda memiliki akun di [Koyeb](https://www.koyeb.com/).
2. Push seluruh folder ini ke repository GitHub Anda.

## Langkah Deployment
1. Di Dashboard Koyeb, klik **Create Service**.
2. Pilih **GitHub** sebagai source.
3. Pilih repository Anda.
4. Di bagian **Build and Deployment Settings**:
   - Koyeb akan mendeteksi `Dockerfile` secara otomatis di root direktori.
5. Di bagian **Environment Variables**, tambahkan:
   - `PORT`: `8080`
   - `FIREBASE_DATABASE_URL`: Isi dengan URL Firebase Realtime Database Anda.
   - `FIREBASE_SERVICE_ACCOUNT`: Isi dengan **seluruh isi** dari file `serviceAccountKey.json` (format JSON). Ini penting karena file asli sudah di-ignore oleh Docker demi keamanan.

## Keamanan
- File `serviceAccountKey.json` telah ditambahkan ke `.dockerignore` agar tidak ter-copy ke dalam image Docker.
- Gunakan Environment Variable di Koyeb untuk menjaga rahasia (secrets).
