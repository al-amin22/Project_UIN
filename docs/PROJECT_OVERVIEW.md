# Project Overview

## Gambaran Umum

Project UIN adalah platform pembelajaran berbasis web yang membantu pengelolaan aktivitas akademik sederhana seperti materi, latihan, kuis, forum, dan e-book. Aplikasi ini membagi akses berdasarkan role agar alur kerja lebih teratur.

## Tujuan Sistem

- menyediakan portal belajar untuk guru dan siswa
- memudahkan admin mengelola akun pengguna
- menyediakan latihan dan kuis interaktif
- mendukung diskusi pembelajaran melalui forum
- mengorganisasi materi dan e-book dalam satu sistem

## Arsitektur Aplikasi

Proyek ini menggunakan pola MVC:

- model menyimpan data pengguna, latihan, kuis, forum, dan e-book
- controller menangani logika bisnis dan navigasi halaman
- view menampilkan halaman publik dan area role-based

## Komponen Utama

### 1. Halaman Publik

`FrontEnd\HomeController` menyediakan:

- beranda
- halaman tentang
- halaman kontak

### 2. Autentikasi dan Dashboard

`HomeController` menangani:

- redirect dashboard berdasarkan role
- logout pengguna

Role yang digunakan:

- 0 = admin
- 1 = guru
- 2 = siswa

### 3. Admin

`Admin\DashboardController` digunakan untuk:

- melihat dashboard admin
- mengelola profil admin
- menambah data guru
- menambah data siswa
- melihat daftar guru dan siswa

### 4. Guru

`Guru\DashboardController` menangani profil guru.

`Guru\MateriController` mengelola materi pembelajaran.

`Guru\LatihanController` mengelola latihan siswa:

- membuat latihan
- melihat hasil latihan siswa
- menonaktifkan latihan

`Guru\QuizController` mengelola kuis:

- menambah soal kuis
- mengubah soal kuis
- menghapus soal kuis

`Guru\ForumController` menangani forum diskusi.

`Guru\EbookController` mengelola e-book pembelajaran.

`Guru\PetunjukController` dan `Guru\KDTujuanController` mengelola petunjuk belajar dan KD/tujuan pembelajaran.

### 5. Siswa

`Siswa\DashboardController` menangani profil siswa.

`Siswa\QuizController` menangani pengerjaan kuis siswa.

`Siswa\LatihanController` menangani pengerjaan latihan siswa.

## Model Data

Beberapa model inti yang digunakan:

- `User`
- `Guru`
- `Siswa`
- `Latihan`
- `LatihanSiswa`
- `LatihanJawab`
- `Quiz`
- `QuizSiswa`
- `QuizJawab`
- `Pilgan`
- `Forum`
- `ForumJawab`
- `Ebook`
- `Materi`
- `Petunjuk`
- `KDTujuan`

## Alur Penggunaan Sistem

1. Admin membuat akun guru dan siswa.
2. Guru login dan mengelola profil, materi, latihan, kuis, forum, dan e-book.
3. Siswa login dan mengerjakan latihan atau kuis yang tersedia.
4. Sistem menyimpan jawaban bertahap.
5. Guru dapat melihat hasil latihan siswa.

## Fitur Pembelajaran

### Latihan

Latihan digunakan untuk mengasah pemahaman siswa melalui soal pilihan ganda.

### Kuis

Kuis digunakan sebagai evaluasi interaktif dengan navigasi soal per halaman.

### Forum

Forum mendukung diskusi antara guru dan siswa.

### E-Book dan Materi

Guru dapat menambahkan materi dan e-book untuk mendukung pembelajaran.

## Keunggulan Implementasi

- struktur role sederhana dan mudah dipahami
- mendukung aktivitas belajar dan evaluasi dalam satu aplikasi
- jawaban siswa disimpan secara bertahap
- forum dan e-book membantu pembelajaran lebih lengkap
