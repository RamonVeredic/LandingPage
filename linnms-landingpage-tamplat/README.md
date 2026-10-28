# LINNMS — Network Management System Landing Page

Landing page khusus **LINNMS** dalam folder mandiri `linnms-landingpage-tamplat/` di repository `RamonVeredic/LandingPage:main`. Template ini berdampingan dengan `Tech-Netnms/` dan tidak mengubah template pertama.

## Struktur situs

- `index.html` — landing page produk: hero, contoh dashboard LINNMS, fitur utama, profil singkat dan CTA dokumentasi.
- `about.html` — profil produk, tujuan, dan sasaran pengguna LINNMS.
- `docs.html` — indeks dokumentasi.
- `instalasi.html` — panduan instalasi LINNMS Production (Docker Compose / CasaOS).
- `oid.html` — referensi OID dan SNMP yang dapat digunakan dan dibagikan oleh pengguna umum, **bagian dari dokumentasi**, bukan produk.
- `troubleshooting.html` — masalah saat memakai aplikasi LINNMS (akun, OLT/ONU, sinkronisasi, dan SNMP), bukan kegagalan GitHub atau CI.

Navigasi utama: **Beranda · Fitur · Dokumentasi · Tentang**. Fitur mengarah ke bagian produk pada beranda. Instalasi, OID, dan troubleshooting diakses dari pusat dokumentasi dan tetap memiliki tautan langsung.

Desain responsive dark navy dengan aksen **hijau → cyan → biru** mengikuti **logo LINNMS resmi**, bukan logo generik. Aset `assets/linnms-logo.png` dan `favicon.ico` bersumber dari `RamonVeredic/icon` pada `LINNMS/LINNMS_icon_cropped.png` dan `LINNMS/LINNMS_icon.ico`. Sub-brand konsisten: **NETWORK MANAGEMENT SYSTEM**.

Mockup ringkasan jaringan pada beranda adalah ilustrasi konsep (bukan data perangkat asli atau klaim performa). Tidak ada logo atau foto stok.

## Cara melihat

Buka `index.html` di browser. Bisa juga jalankan server statis:

```bash
cd linnms-landingpage-tamplat
python3 -m http.server 8000
```

Lalu buka `http://localhost:8000`.

Tidak membutuhkan bundler, backend, atau dependensi npm. Google Fonts opsional dengan fallback sistem. Semua halaman memuat **CSS dan JavaScript LINNMS melalui jsDelivr CDN** dari repository GitHub publik ini (`@main`). File `styles.css` dan `script.js` **tetap tersedia di repository sebagai sumber yang diedit**, bukan dipindahkan atau dihapus. Bootstrap Icons 1.13.1 dan Google Fonts juga melalui CDN. Tidak memerlukan bundler atau npm. Internet diperlukan untuk menampilkan CSS/JS dan ikon; halaman mungkin tidak tampil atau berfungsi penuh jika CDN tidak dapat diakses.

## Konfigurasi dan keamanan

Nama image rujukan: `ghcr.io/ramonveredic/linnms`. Hanya gunakan tag yang sudah tersedia. Contoh deployment mengacu pada `RamonVeredic/LINNMS/deploy/`; periksa kredensial database dan batas akses sebelum dipakai.

OID enterprise ZTE `1.3.6.1.4.1.3902` dan HIOSO `1.3.6.1.4.1.25355` adalah contoh cabang dari driver `LINNMS-Staging`, bukan jaminan kompatibilitas semua model. Sesuaikan credential dan IP pada contoh perintah SNMP. Portal sengaja tidak menjabarkan source code dan implementasi internal LINNMS.

## Penyesuaian tampilan

Hero beranda menggunakan tipografi dan spacing yang konsisten, dua CTA berukuran tetap, dan contoh dashboard ringkas dengan hanya dua baris perangkat. Preview merupakan data ilustrasi, bukan live monitor. Navigasi desktop memakai area klik berukuran tetap, hover, active, dan focus-visible; mobile tetap memakai menu responsif. CSS khusus tampilan tetap ada di GitHub, namun **diunduh browser dari CDN**. Tombol beranda dibuat lebih ringkas (42px desktop dan 44px mobile), tombol navigasi 38px, dan CTA header 40px.

## CDN dan pembaruan tampilan

Aset LINNMS dimuat dari:

- CSS: `https://cdn.jsdelivr.net/gh/RamonVeredic/LandingPage@main/linnms-landingpage-tamplat/styles.css`
- JS: `https://cdn.jsdelivr.net/gh/RamonVeredic/LandingPage@main/linnms-landingpage-tamplat/script.js`

**Penting:** jsDelivr meng-cache URL berbasis branch seperti `@main` hingga sekitar **12 jam**. Perubahan CSS/JS pada pull request **belum tampil lewat URL CDN tersebut** sebelum di-merge ke `main`. Setelah merge, cache juga dapat menampilkan versi sebelumnya untuk sementara. Untuk pengecekan perubahan seketika, tes memakai link `styles.css` dan `script.js` lokal, atau gunakan URL CDN berbasis commit baru. Mengubah HTML menjadi CDN tidak mengganti tema atau mengharuskan JavaScript framework tambahan.
