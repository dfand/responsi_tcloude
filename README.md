# responsi_tcloude
# Website Data Diri

Website ini terdiri dari dua halaman: halaman utama dan halaman profil. Masing-masing halaman di-hosting di container terpisah menggunakan Docker.

## Struktur Direktori


## Langkah-langkah Menjalankan Website di Killercoda Ubuntu Playground

### 1. Persiapan Direktori dan File

#### Buat Direktori

```bash
mkdir website-utama
mkdir website-profil

#### Buat File index.html di website-utama
#### Buat file index.html di dalam direktori website-utama dengan konten berikut:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Halaman Utama</title>
</head>
<body>
    <h1>Halaman Utama</h1>
    <p>Nama Lengkap: Dzikri Fandi Setiowibowo</p>
    <p>NIM: 215610053</p>
    <p>Program Studi: Sistem Informasi</p>
    <p>Hobi: Bulutangkis</p>
    <a href="/profil">Profil Saya</a>
</body>
</html>
