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
```

#### Buat File index.html di website-utama
#### Buat file index.html di dalam direktori website-utama dengan konten berikut:
```bash
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
    <a href="https://63981dca-ca6b-462a-adf7-a18649b3fd9e-10-244-5-47-8081.spch.r.killercoda.com/">Profil Saya</a>
</body>
</html>
```

#### Upload Foto Profil di website-profil
Simpan foto profil dengan nama foto.jpg di dalam direktori website-profil.

#### Buat File index.html di website-profil
Buat file index.html di dalam direktori website-profil dengan program berikut:
```bash
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Halaman Profil</title>
</head>
<body>
    <h1>Profil</h1>
    <img src="foto.jpg" alt="Foto Profil" style="width:200px;height:200px;">
</body>
</html>
```

#### Buat Docker Network
Buat jaringan Docker dengan nama my-dzikri-fandi-setiowibowo-network:
```bash
docker network create my-dzikri-fandi-setiowibowo-network
```

#### Dockerfile dan Image
Dockerfile untuk Website-Utama dan website-profile
Buat file Dockerfile di dalam direktori website-utama dengan konten berikut:
```bash
FROM nginx:latest
COPY . /usr/share/nginx/html
EXPOSE 80
```
#### Build Image
Build Image untuk Website Utama
Masuk ke direktori website-utama dan jalankan perintah berikut:
```bash
cd website-utama
docker build -t website-utama .
```
Build Image untuk Website Profil
Masuk ke direktori website-profil dan jalankan perintah berikut:
```bash
cd website-profil
docker build -t website-profil .
```

#### Menjalankan Container
Jalankan Container Website Utama
```bash
docker run -d --name website-utama --network my-dzikri-fandi-setiowibowo-network -p 8080:80 website-utama
```
Jalankan Container Website Profil
```bash
docker run -d --name website-profil --network my-dzikri-fandi-setiowibowo-network -p 8081:80 website-profil

