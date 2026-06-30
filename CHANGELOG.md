# Changelog

Semua perubahan besar pada proyek nidejia-backend ini akan didokumentasikan di file ini.

## [Unreleased]
### Fixed / Security Patches
- **IDOR (Insecure Direct Object Reference)**: Memperbaiki celah di `TransactionController` dengan menggunakan `findOrFail()` alih-alih `find()`. Aplikasi sekarang mengembalikan error 404 Model Not Found dengan tepat jika `listing_id` yang tidak valid dimasukkan.
- **Logic Flaw (Pengecekan Ketersediaan)**: Mengubah logika pengecekan slot dari menggunakan `whereNot('status', 'canceled')` (yang rentan terhadap status mati seperti *expired* atau *failed*) menjadi `whereIn('status', ['waiting', 'approved'])` yang lebih spesifik.
- **Over-fetching (Kebocoran Data Relasi)**: Memperbaiki cara pemanggilan relasi di `TransactionController`. Mengganti pemanggilan dinamis `$transaction->Listing` dengan *eager loading* `$transaction->load('listing')`.
