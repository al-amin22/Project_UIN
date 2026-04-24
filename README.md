# Project UIN

Project UIN adalah aplikasi pembelajaran dan evaluasi berbasis Laravel 7 yang menyediakan fitur admin, guru, dan siswa untuk mengelola materi, latihan, kuis, forum, e-book, dan profil pengguna.

## Ringkasan

Sistem ini dirancang sebagai platform pembelajaran digital yang mendukung aktivitas guru dan siswa secara terstruktur. Admin dapat mengelola akun, guru dapat membuat materi dan latihan, serta siswa dapat mengerjakan latihan dan kuis secara daring.

## Fitur Utama

- login berbasis role untuk admin, guru, dan siswa
- dashboard berbeda untuk setiap peran
- manajemen akun guru dan siswa oleh admin
- pengelolaan profil pengguna
- materi pembelajaran dan petunjuk belajar
- KD dan tujuan pembelajaran
- latihan soal pilihan ganda
- kuis daring untuk siswa
- forum diskusi
- pengelolaan e-book
- pengelolaan materi oleh guru

## Teknologi

- Laravel 7
- PHP 7.2.5+
- Eloquent ORM
- Laravel UI
- realrashid/sweet-alert

## Struktur Modul

- HomeController: dashboard utama berdasarkan role dan logout
- FrontEnd\HomeController: halaman publik seperti beranda, tentang, dan kontak
- Admin\DashboardController: profil admin, data guru, dan data siswa
- Guru\DashboardController: profil guru
- Guru\MateriController: materi pembelajaran
- Guru\LatihanController: latihan siswa
- Guru\QuizController: kuis
- Guru\ForumController: forum diskusi
- Guru\EbookController: e-book
- Guru\PetunjukController: petunjuk belajar
- Guru\KDTujuanController: KD dan tujuan
- Siswa\DashboardController: profil siswa
- Siswa\QuizController: pengerjaan kuis
- Siswa\LatihanController: pengerjaan latihan

## Rute Penting

- /: halaman beranda publik
- /tentang: halaman tentang
- /kontak: halaman hubungi kami
- /home: dashboard sesuai role
- /admin/*: area admin
- /guru/*: area guru
- /siswa/*: area siswa
- /latihan: latihan soal
- /quiz/*: kuis
- /forum: forum diskusi
- /materi: materi pembelajaran
- /e-book: koleksi e-book

## Cara Menjalankan

1. Salin .env.example menjadi .env
2. Sesuaikan konfigurasi database
3. Jalankan composer install
4. Jalankan php artisan key:generate
5. Jalankan php artisan migrate
6. Jalankan php artisan serve

## Dokumentasi Tambahan

- [Project Overview](docs/PROJECT_OVERVIEW.md)
- [User Guide](docs/USER_GUIDE.md)

## Catatan Teknis

- sistem menggunakan role 0 untuk admin, 1 untuk guru, dan 2 untuk siswa
- latihan dan kuis disajikan satu per satu dengan pagination
- jawaban siswa disimpan secara bertahap agar proses lebih ringan
- materi dan e-book dapat dikelola langsung oleh guru
