# LINNMS — Network Management System Landing Page

Landing page khusus **LINNMS** dalam folder mandiri `linnms-landingpage-tamplat/` di repository `RamonVeredic/LandingPage:main`. Template ini berdampingan dengan `Tech-Netnms/` dan tidak mengubah template pertama.

## Konsep

**Halaman depan memperkenalkan LINNMS sebagai produk Network Management System**, dengan ringkasan pemantauan perangkat, OLT/ONU dan SNMP, visual ringkasan jaringan konseptual, manfaat operasional, dan tautan ke instalasi. Halaman teknis dipisahkan menjadi panduan:

- `index.html` — pengenalan LINNMS, kemampuan utama, dan tautan bantuan.
- `about.html` — identitas produk, sasaran pengguna dan konteks jaringan.
- `docs.html` — instalasi Docker Compose / CasaOS, registry, volume, verifikasi, pembaruan.
- `oid.html` — referensi OID standar MIB-II / IF-MIB serta cabang ZTE / HIOSO, tabel pencarian dan perintah SNMP.
- `troubleshooting.html` — pemeriksaan masalah GHCR, Docker, database, HTTP, SNMP dan OID.

Desain responsive dark navy dengan aksen **hijau → cyan → biru** mengikuti **logo LINNMS resmi**, bukan logo generik. Aset `assets/linnms-logo.png` dan `favicon.ico` bersumber dari `RamonVeredic/icon` pada `LINNMS/LINNMS_icon_cropped.png` dan `LINNMS/LINNMS_icon.ico`. Sub-brand konsisten: **NETWORK MANAGEMENT SYSTEM**.

Mockup ringkasan jaringan pada beranda adalah ilustrasi konsep (bukan data perangkat asli atau klaim performa). Tidak ada logo atau foto stok.

## Cara melihat

Buka `index.html` di browser. Bisa juga jalankan server statis:

```bash
cd linnms-landingpage-tamplat
python3 -m http.server 8000
```

Lalu buka `http://localhost:8000`.

Tidak membutuhkan bundler, backend, atau dependensi npm. Google Fonts opsional dengan fallback sistem. File CSS dan JS bersifat mandiri.

## Konfigurasi dan keamanan

Nama image rujukan: `ghcr.io/ramonveredic/linnms`. Hanya gunakan tag yang sudah tersedia. Contoh deployment mengacu pada `RamonVeredic/LINNMS/deploy/`; periksa kredensial database dan batas akses sebelum dipakai.

OID enterprise ZTE `1.3.6.1.4.1.3902` dan HIOSO `1.3.6.1.4.1.25355` adalah contoh cabang dari driver `LINNMS-Staging`, bukan jaminan kompatibilitas semua model. Sesuaikan credential dan IP pada contoh perintah SNMP. Portal sengaja tidak menjabarkan source code dan implementasi internal LINNMS.
