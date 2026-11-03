# CoreStay Finance

Aplikasi web statis (HTML, CSS, JavaScript tanpa build): Dashboard, Invoice dan piutang, Utang dan pembayaran, Kas dan bank, Laporan.

## Isi
- `index.html`: aplikasi Finance
- `config.js`: isi `executiveUrl` dengan alamat aplikasi Executive bila ingin muncul tautan di menu (boleh dikosongkan)
- `assets/logo.png`: logo CoreStay Advisory

## Menayangkan di GitHub Pages
1. Buat repositori baru, misalnya `corestay-finance`.
2. Unggah semua isi folder ini (termasuk folder `assets`) ke cabang `main`.
3. Settings, Pages, Deploy from a branch, cabang `main`, folder root, Save.
4. Alamat: `https://NAMA-ANDA.github.io/corestay-finance/`.

## Catatan
- Data tersimpan di browser (localStorage) per perangkat. Belum ada login atau database bersama.
- Aplikasi Executive hanya bisa membaca data Finance bila kedua aplikasi berada di akun GitHub yang sama (alamat `NAMA-ANDA.github.io`).
- Isi awal adalah data contoh. Jangan memasukkan data keuangan atau pribadi yang nyata di versi ini.
