# 🏡 Nidejia Backend API

Nidejia adalah platform penyewaan rumah/kos-kosan (kost) eksklusif. Repositori ini berisi sistem *backend* dari Nidejia, menyediakan API tangguh yang mengurus segala sesuatu mulai dari pendaftaran pengguna (otentikasi), sistem reservasi (transaksi), hingga pengelolaan properti (*listing*).

Dibangun menggunakan kerangka kerja PHP terpopuler, Laravel 11, aplikasi ini dioptimalkan untuk skalabilitas, keamanan, dan *developer experience* yang luar biasa.

## 🚀 Fitur Utama
- **Otentikasi Aman:** Menggunakan `Laravel Sanctum` untuk pengamanan otentikasi berbasis *Token* (SPA/API Endpoint) yang super ringan namun kokoh.
- **Manajemen Properti (Listing):** Mendukung manajemen data rumah/kos secara detail (harga, deskripsi, hingga ketersediaan WiFi).
- **Sistem Transaksi Anti-Bentrokan:** Fitur validasi cerdas memastikan tanggal reservasi yang dimasukkan penyewa tidak akan pernah tumpang tindih dengan penyewa lainnya jika kapasitas kamar (*max_person*) sudah penuh.
- **Relasi Database Handal:** Skema database dirancang elegan dengan fitur *Soft Deletes* bawaan.

## 🛠️ Stack Teknologi
- **Framework:** Laravel 11 (PHP 8.2+)
- **Database:** MySQL / PostgreSQL
- **Otentikasi API:** Laravel Sanctum

## 💻 Cara Instalasi

1. Clone repositori ini:
   ```bash
   git clone git@github.com:YoryZiar/nidejia-backend.git
   ```
2. Instal dependensi dan atur env:
   ```bash
   composer install
   cp .env.example .env
   php artisan key:generate
   ```
3. Migrasi database dan jalankan server:
   ```bash
   php artisan migrate --seed
   php artisan serve
   ```

## 🛡️ Keamanan
Kami menanggapi keamanan dengan sangat serius. Pembaruan terakhir telah menutup celah kebocoran IDOR dan Logic Flaw pada sistem penyewaan. Silakan cek file CHANGELOG.md untuk rincian pembaruan.
